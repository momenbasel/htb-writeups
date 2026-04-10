---
layout: default
title: Fortresses
nav_order: 8
description: "HTB Fortress challenge walkthroughs"
permalink: /fortresses/
---

# HackTheBox Fortresses - Complete Reference

> Fortresses are like normal machines but on steroids - single hosts with multiple flags requiring diverse exploitation techniques. Created by partner companies to showcase real-world attack vectors.

---

## 1. Jet Fortress

**IP:** 10.13.37.10 | **Flags:** 11 | **Created by:** Jet (company)

### Overview
The first fortress released on HTB. A multi-flag challenge requiring exploitation of various services on a single host, progressively harder flags.

### Key Techniques
- Service enumeration across multiple ports
- Web application exploitation
- Privilege escalation chains
- Multi-stage exploitation on a single host
- Each flag requires a different attack vector

### Writeup Resources
- [Jet Fortress Writeup - ikonw](https://ik0nw.github.io/2020/09/21/HTB-fortress-Jet/)
- [KryptSec Wiki](https://kwiki.kryptsec.com/books/jet-fortress-072)
- [HTB Forum Discussion](https://forum.hackthebox.com/t/jet-fortress/550)

---

## 2. Akerva Fortress

**IP:** 10.13.37.11 | **Flags:** 8 | **Created by:** Akerva (security company)

### Overview
An advanced multi-stage challenge created by the French cybersecurity company Akerva. Features a WordPress-based site ("Root of the Universe") as the initial attack surface.

### Key Techniques
- WordPress enumeration and exploitation
- SNMP enumeration
- Web application vulnerability chaining
- Credential discovery and reuse
- Multi-stage privilege escalation

### Writeup Resources
- [AKERVA GitHub Writeup](https://github.com/Alwil17/AKERVA)
- [Akerva Fortress - jerome](https://htb-writeup.jerome.co.in/p/akerva-fortress-hackthebox)
- [Akerva Writeup - ikonw](https://ik0nw.github.io/2020/09/19/HTB-fortress-akerva/)
- [Akerva - f3v3r](https://f3v3r.in/htb/fortess/akerva/)
- [HTB Forum Discussion](https://forum.hackthebox.com/t/fortress-akerva/2777)

---

## 3. Context Fortress

**IP:** 10.13.37.12 | **Flags:** 7 | **Created by:** Context (part of Accenture Security)

### Overview
Created by Context, an Accenture Security company. Multi-flag challenge testing web exploitation, infrastructure hacking, and application security skills.

### Key Techniques
- Web application security testing
- Infrastructure enumeration
- Application-level exploitation
- Progressive difficulty escalation

### Writeup Resources
- [HTB Forum Discussion](https://forum.hackthebox.com/t/fortress-context/3376)
- [zweilosec GitBook](https://zweilosec.gitbook.io/htb-writeups/fortress/fortress)

---

## 4. Synacktiv Fortress (Dojo)

**IP:** Varies | **Created by:** Synacktiv

### Overview
The fourth company-created fortress on HTB. Created by Synacktiv, a well-known French offensive security firm. Combines infrastructure hacking, web exploitation, and AppSec exploitation techniques with unique and interesting vectors.

### Key Techniques
- Symfony framework exploitation (security profiler access)
- PHP application analysis
- Subdomain enumeration (wfuzz)
- Infrastructure hacking
- Web exploitation (OWASP-style vulnerabilities)
- Application security (AppSec) exploitation
- Unique and creative attack vectors

### Writeup Resources
- [Official HTB Blog Post](https://www.hackthebox.com/blog/synacktiv-fortress)
- [Synacktiv Fortress - Mane's Blog](https://manesec.github.io/2024/03/27/htb-fortresses/Synacktiv/)
- [HTB Forum Discussion](https://forum.hackthebox.com/t/synacktive-fortress/4300)

---

## 5. AWS Fortress

**Created by:** Amazon Web Services | **Flags:** Multiple

### Overview
Created by Amazon Web Services to showcase cloud security concepts. Features realistic techniques ranging from web exploitation to cloud privilege escalations for services used by thousands of businesses. Available to Hacker rank and above.

### Key Techniques
| Category | Specific Techniques |
|----------|-------------------|
| Web | OWASP Top 10 exploitation |
| Cloud Enumeration | AWS API enumeration, service discovery |
| IAM | IAM misconfiguration exploitation |
| Lambda | AWS Lambda function exploitation |
| DynamoDB | Database enumeration and exploitation |
| SQS | Simple Queue Service abuse |
| S3 | Bucket enumeration, policy misconfiguration |
| Binary Analysis | Reversing binaries with Ghidra/IDA for embedded credentials |

### Required Skills
- Intermediate understanding of AWS services (IAM, Lambda, DynamoDB, SQS)
- Strong understanding of OWASP Top 10
- AWS CLI proficiency (`aws sts get-caller-identity`, `aws s3api`, `aws lambda invoke`)
- Python scripting
- Binary reversing basics

### Writeup Resources
- [Official HTB Blog Post](https://www.hackthebox.com/blog/amazon-web-services-fortress)
- [AWS Fortress Review - Sneh Bavarva](https://snehbavarva.medium.com/aws-fortress-hack-the-box-review-6fd752e502e8)
- [AWS Fortress Review - snehbavarva.com](https://www.snehbavarva.com/blog/aws-fortress-review/)
- [HTB Forum Discussion](https://forum.hackthebox.com/t/fortress-aws/261366)

---

## 6. Faraday Fortress

**Flags:** 7 | **Points:** 110 | **Created by:** Faraday

### Overview
Created by Faraday (the security platform company). Available to Hacker rank and above. Tests various offensive security skills across multiple flag captures.

### Writeup Resources
- [Official HTB Blog Post](https://www.hackthebox.com/blog/faraday-fortress)
- [Faraday Fortress - Mane's Blog](https://manesec.github.io/2024/03/21/htb-fortresses/Faraday/)
- [HTB Forum Discussion](https://forum.hackthebox.com/t/faraday-fotress-discussion/246915)

---

## Fortress Summary

| Fortress | Creator | Flags | Primary Focus |
|----------|---------|-------|---------------|
| Jet | Jet | 11 | Multi-service exploitation |
| Akerva | Akerva | 8 | WordPress, SNMP, web chains |
| Context | Context/Accenture | 7 | Web + infrastructure |
| Synacktiv | Synacktiv | Multiple | Symfony, AppSec, infrastructure |
| AWS | Amazon Web Services | Multiple | Cloud security, IAM, Lambda, S3 |
| Faraday | Faraday | 7 | General offensive security |

**Note:** Fortresses require Hacker rank or above to access on HTB.
