---
layout: default
title: Cert Prep
parent: Resources
nav_order: 3
description: "OSCP, CPTS, CRTO, CRTE, eWPT certification preparation with HTB"
permalink: /resources/cert-prep/
---

# Certification Preparation with HTB

Map your HTB journey to professional security certifications.

## Certification Paths

### OSCP (Offensive Security Certified Professional)

The gold standard for penetration testing. Focus on manual exploitation, no automated tools.

**Recommended Easy Machines:**
| Machine | OS | Key Skills |
|---------|-----|-----------|
| Lame | Linux | Samba RCE (CVE-2007-2447) |
| Legacy | Windows | MS08-067, MS17-010 |
| Blue | Windows | EternalBlue (MS17-010) |
| Devel | Windows | FTP + ASPX webshell, Kernel exploit |
| Optimum | Windows | HFS RCE, MS16-098 |
| Shocker | Linux | Shellshock (CVE-2014-6271) |
| Nibbles | Linux | CMS file upload, sudo abuse |
| Bashed | Linux | PHP webshell, cron abuse |
| Valentine | Linux | Heartbleed, tmux session hijack |
| Arctic | Windows | ColdFusion RCE, JuicyPotato |
| Grandpa | Windows | IIS WebDAV, Token Impersonation |
| Jerry | Windows | Tomcat default creds, WAR deploy |
| Active | Windows | GPP cPassword, Kerberoasting |
| Forest | Windows | AS-REP Roasting, DCSync |
| Sauna | Windows | AS-REP Roasting, WinRM |
| Buff | Windows | Gym Management RCE, CloudMe BOF |
| Love | Windows | SSRF, AlwaysInstallElevated |
| Cap | Linux | PCAP analysis, capability abuse |
| Knife | Linux | PHP 8.1 backdoor, GTFOBins |

**Recommended Medium Machines:**
| Machine | OS | Key Skills |
|---------|-----|-----------|
| Cronos | Linux | DNS zone transfer, SQLi, cron |
| SolidState | Linux | Apache James RCE, cron privesc |
| Poison | Linux | LFI, VNC tunneling |
| Bastard | Windows | Drupal RCE, JuicyPotato |
| Bounty | Windows | IIS upload bypass, JuicyPotato |
| Jeeves | Windows | Jenkins Script Console, KeePass |
| Conceal | Windows | IPSec VPN, SNMP, JuicyPotato |
| DevOops | Linux | XXE, Git secrets |
| Irked | Linux | UnrealIRCd backdoor, stego |

---

### CPTS (HTB Certified Penetration Testing Specialist)

HTB's own penetration testing certification. Aligned with HTB Academy modules.

**Recommended Machines:**
| Machine | OS | Key Skills |
|---------|-----|-----------|
| Active | Windows | GPP abuse, Kerberoasting |
| Forest | Windows | AS-REP Roasting, DCSync |
| Cascade | Windows | LDAP enumeration, .NET reversing |
| Monteverde | Windows | Azure AD, password spraying |
| Resolute | Windows | DNS admin DLL injection |
| Blackfield | Windows | AS-REP, backup operators privesc |
| Intelligence | Windows | DNS records, GMSA, constrained delegation |
| StreamIO | Windows | SQLi, MSSQL, LAPS |
| Escape | Windows | MSSQL, ADCS ESC1 |
| Vintage | Windows | Pure AD exploitation chain |
| Certificate | Windows | ADCS certificate abuse |

**Recommended ProLabs:** Dante, Offshore

---

### CRTO (Certified Red Team Operator)

Red team operations with Cobalt Strike methodology.

**Recommended Machines:**
| Machine | OS | Key Skills |
|---------|-----|-----------|
| Reel | Windows | Phishing, AppLocker bypass, AD |
| Mantis | Windows | Kerberos MS14-068, AD |
| Sizzle | Windows | ADCS, Kerberos, CLM bypass |
| Multimaster | Windows | SQLi, DLL injection, AD |
| APT | Windows | IPv6, RPC, domain recon |

**Recommended ProLabs:** RastaLabs, Zephyr

---

### CRTE (Certified Red Team Expert)

Advanced Active Directory attacks and defenses.

**Recommended Machines:**
| Machine | OS | Key Skills |
|---------|-----|-----------|
| Blackfield | Windows | AS-REP, backup operators |
| Multimaster | Windows | Complex AD chain |
| Object | Windows | AD ACL abuse, GenericWrite |
| Cerberus | Windows | ADCS, cross-domain trusts |
| Rebound | Windows | Advanced Kerberos, RBCD |

**Recommended ProLabs:** Cybernetics, APTLabs

---

### eWPT (eLearnSecurity Web Application Penetration Tester)

Focused on web application security.

**Recommended Challenges (Web category):**
- All Easy/Medium web challenges
- Focus on: SQLi, XSS, SSTI, SSRF, Deserialization

**Recommended Machines:**
| Machine | OS | Key Skills |
|---------|-----|-----------|
| Talkative | Linux | Rocket.Chat exploit, Docker escape |
| Forgot | Linux | Redis cache poisoning, password reset |
| Bagel | Linux | .NET WebSocket, deserialization |
| Sandworm | Linux | SSTI in GPG, Firejail escape |
| Clicker | Linux | NFS, PHP SQLi, LFI chain |

---

## Learning Path Summary

| Level | Cert | HTB Focus | Timeline |
|-------|------|-----------|----------|
| Beginner | OSCP | Easy/Medium machines, Dante ProLab | 3-6 months |
| Intermediate | CPTS | Medium/Hard machines, Offshore ProLab | 4-8 months |
| Advanced | CRTO | Hard machines, RastaLabs/Zephyr | 2-4 months |
| Expert | CRTE | Insane machines, Cybernetics/APTLabs | 3-6 months |
| Web Specialist | eWPT | Web challenges, web-focused machines | 2-4 months |
