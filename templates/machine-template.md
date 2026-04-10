# Machine Name

![Machine Badge](https://img.shields.io/badge/Machine-Name-blue)
![OS](https://img.shields.io/badge/OS-Linux-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)

| Property | Value |
|----------|-------|
| **OS** | Linux / Windows |
| **Difficulty** | Easy / Medium / Hard / Insane |
| **Release Date** | YYYY-MM-DD |
| **Retire Date** | YYYY-MM-DD |
| **IP** | 10.10.10.X |
| **Techniques** | technique-1, technique-2 |
| **Tags** | #web #privesc #linux |

---

## Summary

Brief 2-3 sentence overview of the machine and attack path.

---

## Enumeration

### Nmap Scan

```bash
nmap -sC -sV -oA nmap/machine 10.10.10.X
```

```
# Paste nmap output here
```

### Service Enumeration

Detail findings from each open port/service.

---

## Foothold

How you gained initial access to the machine.

### Vulnerability

Description of the vulnerability exploited.

### Exploitation

Step-by-step exploitation with commands.

```bash
# Commands used
```

---

## User Flag

### Lateral Movement (if applicable)

Steps to move from initial foothold to user access.

### Flag

```
user.txt: ********************************
```

---

## Privilege Escalation

### Enumeration

What you found that leads to root/admin.

### Exploitation

Step-by-step privilege escalation.

```bash
# Commands used
```

### Root Flag

```
root.txt: ********************************
```

---

## Lessons Learned

- Key takeaway 1
- Key takeaway 2
- Key takeaway 3

---

## References

- [Reference 1](url)
- [Reference 2](url)
