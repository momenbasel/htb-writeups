# How to Approach Any HTB Machine

A systematic methodology for tackling Hack The Box machines efficiently.

## Phase 1: Reconnaissance (10-20 min)

### Port Scanning

```bash
# Quick scan
rustscan -a 10.10.10.X -- -sC -sV -oA nmap/initial

# Full port scan
nmap -p- --min-rate 10000 -oA nmap/allports 10.10.10.X

# Detailed scan on found ports
nmap -p 22,80,443 -sC -sV -oA nmap/detailed 10.10.10.X

# UDP scan (top 20)
sudo nmap -sU --top-ports 20 -oA nmap/udp 10.10.10.X
```

### Service Enumeration

For each open port, enumerate the service:

| Port | Service | First Steps |
|------|---------|-------------|
| 21 | FTP | Check anonymous login, version exploits |
| 22 | SSH | Note version, try creds later |
| 25 | SMTP | User enumeration (VRFY/EXPN) |
| 53 | DNS | Zone transfer, subdomain enum |
| 80/443 | HTTP/S | Whatweb, gobuster, check source |
| 88 | Kerberos | It's Active Directory |
| 110/143 | POP3/IMAP | Try default creds |
| 135 | MSRPC | rpcclient, enum4linux |
| 139/445 | SMB | Shares, null session, version |
| 389/636 | LDAP | Anonymous bind, enum users |
| 1433 | MSSQL | Default creds, xp_cmdshell |
| 3306 | MySQL | Default creds, UDF |
| 3389 | RDP | Try creds, BlueKeep if old |
| 5432 | PostgreSQL | Default creds, COPY TO |
| 5985 | WinRM | Evil-WinRM with creds |
| 6379 | Redis | No auth? Write SSH key/webshell |
| 8080 | HTTP Alt | Same as HTTP |
| 27017 | MongoDB | No auth? Dump databases |

## Phase 2: Enumeration Deep Dive (20-40 min)

### Web Services

```bash
# 1. Technology fingerprint
whatweb http://10.10.10.X

# 2. Directory enumeration
gobuster dir -u http://10.10.10.X -w /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt -t 50

# 3. Check for subdomains/vhosts
gobuster vhost -u http://domain.htb -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt --append-domain

# 4. Manual browsing
# - View page source
# - Check /robots.txt, /sitemap.xml
# - Look at cookies, headers
# - Check for comments in source
# - Try default credentials on login pages

# 5. If CMS detected
# WordPress: wpscan --url http://domain.htb -e ap,at,u
# Joomla: joomscan -u http://domain.htb
# Drupal: droopescan scan drupal -u http://domain.htb
```

### SMB

```bash
nxc smb 10.10.10.X -u '' -p '' --shares
nxc smb 10.10.10.X -u 'guest' -p '' --shares
smbclient -N -L //10.10.10.X
```

### Active Directory (if ports 88/389/445)

```bash
# Null session user enum
nxc smb 10.10.10.X -u '' -p '' --rid-brute
# Kerbrute user enum
kerbrute userenum -d domain.htb --dc 10.10.10.X users.txt
# AS-REP Roasting (if you have usernames)
impacket-GetNPUsers domain.htb/ -usersfile users.txt -format hashcat
```

## Phase 3: Exploitation / Foothold

### Approach Order

1. **Known CVE** - searchsploit, Google the exact version
2. **Default/weak credentials** - admin:admin, admin:password
3. **Injection** - SQLi, command injection, SSTI in input fields
4. **File upload** - Try to upload a shell
5. **LFI/SSRF** - Read files, access internal services
6. **Custom exploitation** - Unique to the application

### Getting a Shell

```bash
# Set up listener
rlwrap nc -lvnp 4444

# Execute reverse shell via the vulnerability
# See: reverse-shells.md

# Upgrade to interactive shell immediately
python3 -c 'import pty; pty.spawn("/bin/bash")'
# Ctrl+Z
stty raw -echo; fg
export TERM=xterm
```

## Phase 4: Post-Exploitation

### Stabilize Shell

```bash
# Check who you are
id
whoami
hostname
ip a
```

### Grab User Flag

```bash
# Linux
find / -name user.txt 2>/dev/null
cat /home/*/user.txt

# Windows
dir /s /b C:\Users\*\Desktop\user.txt
type C:\Users\username\Desktop\user.txt
```

## Phase 5: Privilege Escalation

### Linux Checklist

1. `sudo -l` - Check sudo permissions
2. `find / -perm -4000 2>/dev/null` - SUID binaries
3. `getcap -r / 2>/dev/null` - Capabilities
4. Check cron jobs
5. Check internal services
6. Check writable files/directories
7. Kernel exploits (last resort)
8. Run LinPEAS

### Windows Checklist

1. `whoami /priv` - Check privileges
2. `cmdkey /list` - Stored credentials
3. Check services for misconfigurations
4. Check scheduled tasks
5. Check registry for passwords
6. Check installed software versions
7. Run WinPEAS

### Grab Root Flag

```bash
# Linux
cat /root/root.txt

# Windows
type C:\Users\Administrator\Desktop\root.txt
```

## General Tips

- **Add machine hostname to /etc/hosts**: `echo "10.10.10.X domain.htb" | sudo tee -a /etc/hosts`
- **Take notes as you go**: Document every finding, every command
- **Try the simple things first**: Default creds, obvious vulnerabilities
- **Read error messages carefully**: They often hint at the vulnerability
- **Check everything manually**: Don't rely solely on automated tools
- **Google exact version numbers**: "Apache 2.4.49 exploit" often finds CVEs
- **Enumerate thoroughly before exploiting**: Missing a service can waste hours
- **Check source code**: Comments, hidden fields, JavaScript files
- **Look at the machine name**: It often hints at the technology or technique
- **Don't rabbit-hole**: If stuck for 30+ minutes, step back and enumerate more
