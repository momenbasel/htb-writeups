---
layout: default
title: "OSINT"
parent: Challenges
nav_order: 8
permalink: /challenges/osint/
---

# OSINT Challenges

Writeups for HTB Open Source Intelligence challenges.

## Challenge Index

| Challenge | Difficulty | Techniques | Key Takeaway |
|-----------|-----------|------------|--------------|
| [Money Flowz](money-flowz/) | Very Easy | Cryptocurrency, Blockchain Explorer | Tracing crypto transactions |
| [Easy Phish](easy-phish/) | Very Easy | DNS, SPF/DMARC | Email authentication records |
| [Infiltrator](infiltrator/) | Easy | LinkedIn, Social Engineering | Corporate intelligence gathering |
| [ID Exposed](id-exposed/) | Easy | Metadata, Image Analysis | EXIF data extraction |
| [KafkaConnect](kafka-connect/) | Easy | Git History, Secrets | Finding secrets in public repos |
| [Veni, vidi, vici](veni/) | Medium | Geolocation, Google Earth | Image-based geolocation |
| [Way Back](way-back/) | Medium | Wayback Machine, Web Archives | Finding historical website content |
| [Digital Ghost](digital-ghost/) | Hard | Multi-Source OSINT | Correlating data across platforms |

## Techniques

### DNS/Email
```bash
# DNS records
dig domain.htb ANY
dig domain.htb TXT
dig domain.htb MX

# SPF/DMARC
dig domain.htb TXT | grep spf
dig _dmarc.domain.htb TXT

# WHOIS
whois domain.htb
```

### Image Analysis
```bash
# EXIF data
exiftool image.jpg

# Reverse image search
# Google Images, TinEye, Yandex

# Geolocation from images
# Google Maps, Google Earth, GeoGuessr techniques
```

### Social Media
- LinkedIn - Company employees, roles, tech stack
- GitHub - Code repos, commit history, secrets
- Twitter/X - Company updates, employee posts

### Web Archives
- Wayback Machine (web.archive.org)
- Google Cache
- Archive.today

## Tools

| Tool | Purpose |
|------|---------|
| Maltego | Link analysis and visualization |
| theHarvester | Email, subdomain, name collection |
| Sherlock | Username search across platforms |
| SpiderFoot | Automated OSINT collection |
| exiftool | Image metadata extraction |
| Shodan | Internet device search |
| Censys | Internet-wide scanning data |
| OSINT Framework | Collection of OSINT tools |
