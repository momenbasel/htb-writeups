# Note-Taking Template for HTB Machines

Structured template for documenting your HTB machine progress.

## Template

```markdown
# [Machine Name] - [OS] - [Difficulty]

## Target: 10.10.10.X

## Recon

### Nmap
[Paste full nmap output]

### Open Ports Summary
| Port | Service | Version |
|------|---------|---------|
| 22   | SSH     | OpenSSH 8.9p1 |
| 80   | HTTP    | Apache 2.4.52 |

### Findings
- [ ] Finding 1
- [ ] Finding 2

## Web (Port 80)

### Technology
- Server: 
- Framework:
- CMS:

### Directory Brute Force
[Paste gobuster output]

### Interesting Endpoints
- /admin - Login page
- /api - API endpoint

### Credentials Found
| Username | Password | Where Found |
|----------|----------|-------------|
| admin    | password | config file |

## Foothold

### Vulnerability
[Description]

### Exploit
[Commands and output]

### Shell Obtained
- User: www-data
- Method: reverse shell via RCE

## User

### Lateral Movement
[How you got from www-data to user]

### User Flag
user.txt: [flag]

## Privilege Escalation

### Enumeration Findings
- sudo -l: [output]
- SUID: [findings]
- Cron: [findings]

### Exploit
[Commands and output]

### Root Flag
root.txt: [flag]

## Loot
- Credentials: 
- SSH keys:
- Hashes:

## Lessons Learned
1. 
2.
3.
```

## Tips

- Copy-paste command output liberally
- Screenshot anything visual (web pages, BloodHound graphs)
- Note dead ends too - helps avoid repeating them
- Track time spent on each phase
- Save any custom scripts you write
