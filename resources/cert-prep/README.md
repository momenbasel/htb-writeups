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

| Machine | OS | Key Skills | Writeup |
|---------|-----|-----------|----------|
| [Lame](https://0xdf.gitlab.io/2020/04/07/htb-lame.html) | Linux | Samba RCE (CVE-2007-2447) | [0xdf](https://0xdf.gitlab.io/2020/04/07/htb-lame.html) |
| [Legacy](https://0xdf.gitlab.io/2019/02/21/htb-legacy.html) | Windows | MS08-067, MS17-010 | [0xdf](https://0xdf.gitlab.io/2019/02/21/htb-legacy.html) |
| [Blue](https://0xdf.gitlab.io/2021/05/11/htb-blue.html) | Windows | EternalBlue (MS17-010) | [0xdf](https://0xdf.gitlab.io/2021/05/11/htb-blue.html) |
| [Devel](https://0xdf.gitlab.io/2019/03/05/htb-devel.html) | Windows | FTP + ASPX webshell, Kernel exploit | [0xdf](https://0xdf.gitlab.io/2019/03/05/htb-devel.html) |
| [Optimum](https://0xdf.gitlab.io/2021/03/17/htb-optimum.html) | Windows | HFS RCE, MS16-098 | [0xdf](https://0xdf.gitlab.io/2021/03/17/htb-optimum.html) |
| [Shocker](https://0xdf.gitlab.io/2021/05/25/htb-shocker.html) | Linux | Shellshock (CVE-2014-6271) | [0xdf](https://0xdf.gitlab.io/2021/05/25/htb-shocker.html) |
| [Nibbles](https://0xdf.gitlab.io/2018/06/30/htb-nibbles.html) | Linux | CMS file upload, sudo abuse | [0xdf](https://0xdf.gitlab.io/2018/06/30/htb-nibbles.html) |
| [Bashed](https://0xdf.gitlab.io/2018/04/29/htb-bashed.html) | Linux | PHP webshell, cron abuse | [0xdf](https://0xdf.gitlab.io/2018/04/29/htb-bashed.html) |
| [Valentine](https://0xdf.gitlab.io/2018/07/28/htb-valentine.html) | Linux | Heartbleed, tmux session hijack | [0xdf](https://0xdf.gitlab.io/2018/07/28/htb-valentine.html) |
| [Arctic](https://0xdf.gitlab.io/2020/05/19/htb-arctic.html) | Windows | ColdFusion RCE, JuicyPotato | [0xdf](https://0xdf.gitlab.io/2020/05/19/htb-arctic.html) |
| [Grandpa](https://0xdf.gitlab.io/2020/05/28/htb-grandpa.html) | Windows | IIS WebDAV, Token Impersonation | [0xdf](https://0xdf.gitlab.io/2020/05/28/htb-grandpa.html) |
| [Jerry](https://0xdf.gitlab.io/2018/11/17/htb-jerry.html) | Windows | Tomcat default creds, WAR deploy | [0xdf](https://0xdf.gitlab.io/2018/11/17/htb-jerry.html) |
| [Active](https://0xdf.gitlab.io/2018/12/08/htb-active.html) | Windows | GPP cPassword, Kerberoasting | [0xdf](https://0xdf.gitlab.io/2018/12/08/htb-active.html) |
| [Forest](https://0xdf.gitlab.io/2020/03/21/htb-forest.html) | Windows | AS-REP Roasting, DCSync | [0xdf](https://0xdf.gitlab.io/2020/03/21/htb-forest.html) |
| [Sauna](https://0xdf.gitlab.io/2020/07/18/htb-sauna.html) | Windows | AS-REP Roasting, WinRM | [0xdf](https://0xdf.gitlab.io/2020/07/18/htb-sauna.html) |
| [Buff](https://0xdf.gitlab.io/2020/11/21/htb-buff.html) | Windows | Gym Management RCE, CloudMe BOF | [0xdf](https://0xdf.gitlab.io/2020/11/21/htb-buff.html) |
| [Love](https://0xdf.gitlab.io/2021/08/07/htb-love.html) | Windows | SSRF, AlwaysInstallElevated | [0xdf](https://0xdf.gitlab.io/2021/08/07/htb-love.html) |
| [Cap](https://0xdf.gitlab.io/2021/10/02/htb-cap.html) | Linux | PCAP analysis, capability abuse | [0xdf](https://0xdf.gitlab.io/2021/10/02/htb-cap.html) |
| [Knife](https://0xdf.gitlab.io/2021/08/28/htb-knife.html) | Linux | PHP 8.1 backdoor, GTFOBins | [0xdf](https://0xdf.gitlab.io/2021/08/28/htb-knife.html) |

**Recommended Medium Machines:**

| Machine | OS | Key Skills | Writeup |
|---------|-----|-----------|----------|
| [Cronos](https://0xdf.gitlab.io/2020/04/14/htb-cronos.html) | Linux | DNS zone transfer, SQLi, cron | [0xdf](https://0xdf.gitlab.io/2020/04/14/htb-cronos.html) |
| [SolidState](https://0xdf.gitlab.io/2020/04/30/htb-solidstate.html) | Linux | Apache James RCE, cron privesc | [0xdf](https://0xdf.gitlab.io/2020/04/30/htb-solidstate.html) |
| [Poison](https://0xdf.gitlab.io/2018/09/08/htb-poison.html) | Linux | LFI, VNC tunneling | [0xdf](https://0xdf.gitlab.io/2018/09/08/htb-poison.html) |
| [Bastard](https://0xdf.gitlab.io/2019/03/12/htb-bastard.html) | Windows | Drupal RCE, JuicyPotato | [0xdf](https://0xdf.gitlab.io/2019/03/12/htb-bastard.html) |
| [Bounty](https://0xdf.gitlab.io/2018/10/27/htb-bounty.html) | Windows | IIS upload bypass, JuicyPotato | [0xdf](https://0xdf.gitlab.io/2018/10/27/htb-bounty.html) |
| [Jeeves](https://0xdf.gitlab.io/2022/04/14/htb-jeeves.html) | Windows | Jenkins Script Console, KeePass | [0xdf](https://0xdf.gitlab.io/2022/04/14/htb-jeeves.html) |
| [Conceal](https://0xdf.gitlab.io/2019/05/18/htb-conceal.html) | Windows | IPSec VPN, SNMP, JuicyPotato | [0xdf](https://0xdf.gitlab.io/2019/05/18/htb-conceal.html) |
| [DevOops](https://0xdf.gitlab.io/2018/10/13/htb-devoops.html) | Linux | XXE, Git secrets | [0xdf](https://0xdf.gitlab.io/2018/10/13/htb-devoops.html) |
| [Irked](https://0xdf.gitlab.io/2019/04/27/htb-irked.html) | Linux | UnrealIRCd backdoor, stego | [0xdf](https://0xdf.gitlab.io/2019/04/27/htb-irked.html) |

---

### CPTS (HTB Certified Penetration Testing Specialist)

HTB's own penetration testing certification. Aligned with HTB Academy modules.

**Recommended Machines:**

| Machine | OS | Key Skills | Writeup |
|---------|-----|-----------|----------|
| [Active](https://0xdf.gitlab.io/2018/12/08/htb-active.html) | Windows | GPP abuse, Kerberoasting | [0xdf](https://0xdf.gitlab.io/2018/12/08/htb-active.html) |
| [Forest](https://0xdf.gitlab.io/2020/03/21/htb-forest.html) | Windows | AS-REP Roasting, DCSync | [0xdf](https://0xdf.gitlab.io/2020/03/21/htb-forest.html) |
| [Cascade](https://0xdf.gitlab.io/2020/07/25/htb-cascade.html) | Windows | LDAP enumeration, .NET reversing | [0xdf](https://0xdf.gitlab.io/2020/07/25/htb-cascade.html) |
| [Monteverde](https://0xdf.gitlab.io/2020/06/13/htb-monteverde.html) | Windows | Azure AD, password spraying | [0xdf](https://0xdf.gitlab.io/2020/06/13/htb-monteverde.html) |
| [Resolute](https://0xdf.gitlab.io/2020/05/30/htb-resolute.html) | Windows | DNS admin DLL injection | [0xdf](https://0xdf.gitlab.io/2020/05/30/htb-resolute.html) |
| [Blackfield](https://0xdf.gitlab.io/2020/10/03/htb-blackfield.html) | Windows | AS-REP, backup operators privesc | [0xdf](https://0xdf.gitlab.io/2020/10/03/htb-blackfield.html) |
| [Intelligence](https://0xdf.gitlab.io/2021/11/27/htb-intelligence.html) | Windows | DNS records, GMSA, constrained delegation | [0xdf](https://0xdf.gitlab.io/2021/11/27/htb-intelligence.html) |
| [StreamIO](https://0xdf.gitlab.io/2022/09/17/htb-streamio.html) | Windows | SQLi, MSSQL, LAPS | [0xdf](https://0xdf.gitlab.io/2022/09/17/htb-streamio.html) |
| [Escape](https://0xdf.gitlab.io/2023/06/17/htb-escape.html) | Windows | MSSQL, ADCS ESC1 | [0xdf](https://0xdf.gitlab.io/2023/06/17/htb-escape.html) |
| [Vintage](https://0xdf.gitlab.io/2025/04/26/htb-vintage.html) | Windows | Pure AD exploitation chain | [0xdf](https://0xdf.gitlab.io/2025/04/26/htb-vintage.html) |
| [Certificate](https://0xdf.gitlab.io/2025/10/04/htb-certificate.html) | Windows | ADCS certificate abuse | [0xdf](https://0xdf.gitlab.io/2025/10/04/htb-certificate.html) |

**Recommended ProLabs:** Dante, Offshore

---

### CRTO (Certified Red Team Operator)

Red team operations with Cobalt Strike methodology.

**Recommended Machines:**

| Machine | OS | Key Skills | Writeup |
|---------|-----|-----------|----------|
| [Reel](https://0xdf.gitlab.io/2018/11/10/htb-reel.html) | Windows | Phishing, AppLocker bypass, AD | [0xdf](https://0xdf.gitlab.io/2018/11/10/htb-reel.html) |
| [Mantis](https://0xdf.gitlab.io/2020/09/03/htb-mantis.html) | Windows | Kerberos MS14-068, AD | [0xdf](https://0xdf.gitlab.io/2020/09/03/htb-mantis.html) |
| [Sizzle](https://0xdf.gitlab.io/2019/06/01/htb-sizzle.html) | Windows | ADCS, Kerberos, CLM bypass | [0xdf](https://0xdf.gitlab.io/2019/06/01/htb-sizzle.html) |
| [Multimaster](https://0xdf.gitlab.io/2020/09/19/htb-multimaster.html) | Windows | SQLi, DLL injection, AD | [0xdf](https://0xdf.gitlab.io/2020/09/19/htb-multimaster.html) |
| [APT](https://0xdf.gitlab.io/2021/04/10/htb-apt.html) | Windows | IPv6, RPC, domain recon | [0xdf](https://0xdf.gitlab.io/2021/04/10/htb-apt.html) |

**Recommended ProLabs:** RastaLabs, Zephyr

---

### CRTE (Certified Red Team Expert)

Advanced Active Directory attacks and defenses.

**Recommended Machines:**

| Machine | OS | Key Skills | Writeup |
|---------|-----|-----------|----------|
| [Blackfield](https://0xdf.gitlab.io/2020/10/03/htb-blackfield.html) | Windows | AS-REP, backup operators | [0xdf](https://0xdf.gitlab.io/2020/10/03/htb-blackfield.html) |
| [Multimaster](https://0xdf.gitlab.io/2020/09/19/htb-multimaster.html) | Windows | Complex AD chain | [0xdf](https://0xdf.gitlab.io/2020/09/19/htb-multimaster.html) |
| [Object](https://0xdf.gitlab.io/2022/02/28/htb-object.html) | Windows | AD ACL abuse, GenericWrite | [0xdf](https://0xdf.gitlab.io/2022/02/28/htb-object.html) |
| [Cerberus](https://0xdf.gitlab.io/2023/07/29/htb-cerberus.html) | Windows | ADCS, cross-domain trusts | [0xdf](https://0xdf.gitlab.io/2023/07/29/htb-cerberus.html) |
| [Rebound](https://0xdf.gitlab.io/2024/03/30/htb-rebound.html) | Windows | Advanced Kerberos, RBCD | [0xdf](https://0xdf.gitlab.io/2024/03/30/htb-rebound.html) |

**Recommended ProLabs:** Cybernetics, APTLabs

---

### eWPT (eLearnSecurity Web Application Penetration Tester)

Focused on web application security.

**Recommended Challenges (Web category):**
- All Easy/Medium web challenges
- Focus on: SQLi, XSS, SSTI, SSRF, Deserialization

**Recommended Machines:**

| Machine | OS | Key Skills | Writeup |
|---------|-----|-----------|----------|
| [Talkative](https://0xdf.gitlab.io/2022/08/27/htb-talkative.html) | Linux | Rocket.Chat exploit, Docker escape | [0xdf](https://0xdf.gitlab.io/2022/08/27/htb-talkative.html) |
| [Forgot](https://0xdf.gitlab.io/2023/03/04/htb-forgot.html) | Linux | Redis cache poisoning, password reset | [0xdf](https://0xdf.gitlab.io/2023/03/04/htb-forgot.html) |
| [Bagel](https://0xdf.gitlab.io/2023/06/03/htb-bagel.html) | Linux | .NET WebSocket, deserialization | [0xdf](https://0xdf.gitlab.io/2023/06/03/htb-bagel.html) |
| [Sandworm](https://0xdf.gitlab.io/2023/11/18/htb-sandworm.html) | Linux | SSTI in GPG, Firejail escape | [0xdf](https://0xdf.gitlab.io/2023/11/18/htb-sandworm.html) |
| [Clicker](https://0xdf.gitlab.io/2024/01/27/htb-clicker.html) | Linux | NFS, PHP SQLi, LFI chain | [0xdf](https://0xdf.gitlab.io/2024/01/27/htb-clicker.html) |

---

## Learning Path Summary

| Level | Cert | HTB Focus | Timeline |
|-------|------|-----------|----------|
| Beginner | OSCP | Easy/Medium machines, Dante ProLab | 3-6 months |
| Intermediate | CPTS | Medium/Hard machines, Offshore ProLab | 4-8 months |
| Advanced | CRTO | Hard machines, RastaLabs/Zephyr | 2-4 months |
| Expert | CRTE | Insane machines, Cybernetics/APTLabs | 3-6 months |
| Web Specialist | eWPT | Web challenges, web-focused machines | 2-4 months |
