# Linux Enumeration Cheatsheet

Post-exploitation enumeration commands for Linux machines on HTB.

## System Information

```bash
# OS and kernel
uname -a
cat /etc/os-release
cat /etc/issue
hostnamectl

# Architecture
arch
uname -m

# Kernel version (for exploit research)
uname -r
cat /proc/version
```

## Users and Groups

```bash
# Current user
id
whoami

# All users
cat /etc/passwd
cat /etc/passwd | grep -v nologin | grep -v false

# Groups
cat /etc/group
groups

# Logged in users
w
who
last

# Sudo privileges
sudo -l

# Password hashes (if readable)
cat /etc/shadow
```

## Network

```bash
# Interfaces
ip a
ifconfig

# Routes
ip route
route -n

# Connections
ss -tulnp
netstat -tulnp

# ARP table
arp -a
ip neigh

# DNS
cat /etc/resolv.conf
cat /etc/hosts

# Firewall rules
iptables -L -n -v
```

## Processes and Services

```bash
# Running processes
ps aux
ps -ef

# Process tree
ps auxf
pstree

# Services
systemctl list-units --type=service --state=running
service --status-all

# Cron jobs
crontab -l
ls -la /etc/cron*
cat /etc/crontab
ls -la /var/spool/cron/crontabs/

# Timers
systemctl list-timers
```

## SUID/SGID/Capabilities

```bash
# SUID binaries
find / -perm -4000 -type f 2>/dev/null

# SGID binaries
find / -perm -2000 -type f 2>/dev/null

# Both
find / -perm -6000 -type f 2>/dev/null

# Capabilities
getcap -r / 2>/dev/null

# Writable files
find / -writable -type f 2>/dev/null | grep -v proc
```

## File System

```bash
# Mounted filesystems
mount
df -h
cat /etc/fstab

# Find interesting files
find / -name "*.conf" -type f 2>/dev/null
find / -name "*.config" -type f 2>/dev/null
find / -name "*.db" -type f 2>/dev/null
find / -name "*.sqlite" -type f 2>/dev/null
find / -name "*.bak" -type f 2>/dev/null
find / -name "*.old" -type f 2>/dev/null
find / -name "*.log" -type f 2>/dev/null
find / -name "id_rsa" -type f 2>/dev/null
find / -name "*.key" -type f 2>/dev/null
find / -name "*.pem" -type f 2>/dev/null
find / -name ".env" -type f 2>/dev/null

# Recently modified files
find / -mmin -10 -type f 2>/dev/null

# Writable directories
find / -writable -type d 2>/dev/null
```

## Interesting Locations

```bash
# Home directories
ls -la /home/
ls -la /root/

# SSH keys
ls -la ~/.ssh/
cat ~/.ssh/authorized_keys
cat ~/.ssh/id_rsa

# History files
cat ~/.bash_history
cat ~/.zsh_history
cat ~/.mysql_history
cat ~/.psql_history

# Config files
cat /etc/apache2/sites-enabled/*
cat /etc/nginx/sites-enabled/*
cat /opt/*/config*
cat /var/www/html/*.php

# Database configs
grep -ri "password" /var/www/ 2>/dev/null
grep -ri "DB_PASS" /var/www/ 2>/dev/null
```

## Docker/Container Check

```bash
# Am I in a container?
cat /proc/1/cgroup
ls -la /.dockerenv
hostname

# Docker socket
ls -la /var/run/docker.sock

# Docker commands (if available)
docker images
docker ps -a
```

## Automated Tools

```bash
# LinPEAS
curl -L https://github.com/peass-ng/PEASS-ng/releases/latest/download/linpeas.sh | sh

# LinEnum
./LinEnum.sh -t

# linux-exploit-suggester
./linux-exploit-suggester.sh

# pspy (process monitoring without root)
./pspy64
```
