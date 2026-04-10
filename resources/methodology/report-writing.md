# Pentest Report Writing Guide

How to turn your HTB machine notes into a professional-looking writeup.

## Structure

A good writeup follows this structure:

1. **Machine Info** - Name, OS, difficulty, IP, techniques
2. **Summary** - 2-3 sentences covering the full attack path
3. **Enumeration** - What you found and how
4. **Foothold** - How you got initial access
5. **User** - How you escalated to user (if different from foothold)
6. **Root** - How you escalated to root/admin
7. **Lessons Learned** - What this machine teaches

## Writing Tips

### Be Specific
Bad: "I found an SQL injection vulnerability"
Good: "The `id` parameter in `/api/users?id=1` is vulnerable to UNION-based SQL injection"

### Show Your Work
Always include:
- The exact command you ran
- The relevant output (trimmed if verbose)
- Why you chose that approach

### Explain the "Why"
Bad: "I ran LinPEAS"
Good: "After gaining a shell as www-data, I ran LinPEAS to enumerate privilege escalation vectors. It identified a SUID binary `/usr/local/bin/backup` that executes `tar` without a full path"

### Screenshots
Use screenshots for:
- Web application findings
- BloodHound graphs
- Key moments (getting shell, reading flag)
- Complex visual output

### Code Blocks
Use syntax-highlighted code blocks for all commands and output:

````markdown
```bash
nmap -sC -sV -oA nmap/initial 10.10.10.X
```

```
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 8.9p1
80/tcp open  http    Apache 2.4.52
```
````

## Formatting Checklist

- [ ] Machine info table at the top
- [ ] Clear section headers
- [ ] All commands in code blocks
- [ ] Output trimmed to relevant portions
- [ ] Screenshots where helpful
- [ ] Explanation of each step
- [ ] Lessons learned section
- [ ] References to tools/CVEs used
