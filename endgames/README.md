---
layout: default
title: Endgames
nav_order: 7
description: "HTB Endgame scenario walkthroughs"
permalink: /endgames/
---

# HackTheBox Endgames - Complete Walkthroughs

> Multi-machine, multi-stage scenarios simulating real penetration testing engagements. Each endgame contains multiple flags across an interconnected network.

---

## 1. P.O.O. (Professional Offensive Operations)

**Difficulty:** Easy-Medium | **Hosts:** 2 Windows | **Flags:** 5

### Overview
The first Endgame released by HTB. Two Windows hosts presented behind a single public-facing IP. Focuses on web enumeration, MSSQL exploitation, and linked server abuse.

### Attack Chain
1. **Recon:** Discover DS_STORE files and IIS short filenames (8.3 naming) to enumerate hidden paths
2. **Credential Discovery:** Find MSSQL database connection string through tricky file enumeration
3. **MSSQL Exploitation:** Connect to MSSQL instance with discovered credentials
4. **Linked Server Abuse:** Exploit trust relationships between MSSQL linked servers to escalate access
5. **Code Execution:** Abuse linked server trust to achieve command execution on the second host

### Key Techniques
- DS_STORE file enumeration
- IIS 8.3 short filename brute-forcing
- MSSQL enumeration (roles, grants, proxy accounts)
- MSSQL linked server exploitation
- Trust abuse between database servers

### Writeup Resources
- [0xdf Writeup](https://0xdf.gitlab.io/2020/06/08/endgame-poo.html)
- [snowscan Writeup](https://snowscan.io/htb-writeup-poo/)
- [saihatnetsec Walkthrough](https://saihatnetsec.blogspot.com/2021/03/hackthebox-endgame-poo-walkthrough.html)
- [HackYourMom Walkthrough](https://hackyourmom.com/en/osvita/samonavchannya/ctf-ta-rajtapy/yak-projty-laboratoriyu-professional-offensive-operations-na-hackthebox/)

---

## 2. Xen

**Difficulty:** Medium-Hard | **Hosts:** 6 (3 Windows workstations, 1 Netscaler/FreeBSD, 1 Citrix Windows, 1 Domain Controller) | **Flags:** 5+

### Overview
Test enumeration, breakout, lateral movement, and privilege escalation within a small Active Directory environment behind a Citrix virtual desktop.

### Attack Chain
1. **Phishing:** Social engineer/phish credentials from users in the Sales department
2. **Citrix Breakout:** Use phished credentials to access Citrix VDI environment, then escape the restricted desktop
3. **Workstation Compromise:** Privilege escalation on 3 end-user Windows computers
4. **Lateral Movement:** Move through the network using harvested credentials
5. **Domain Compromise:** Kerberoasting, credential extraction, DC takeover

### Key Techniques
- Social engineering / credential phishing
- Citrix virtual desktop breakout
- Windows local privilege escalation
- Kerberoasting
- Active Directory enumeration and exploitation
- Domain Controller compromise

### Writeup Resources
- [0xdf Writeup](https://0xdf.gitlab.io/2020/06/17/endgame-xen.html)
- [morph3sec Writeup](https://morph3sec.com/Writeups/HackTheBox/HackTheBox-Endgame-Xen-Writeup/)
- [sinfulz Walkthrough (Medium)](https://medium.com/@sinfulz/hackthebox-xen-endgame-walkthrough-f153c137a873)
- [PuckieStyle Writeup](https://www.puckiestyle.nl/htb-endgame-xen/)
- [dmw0ng Writeup (BirdsArentReal)](https://birdsarentrealctf.dev/2020/06/19/XEN-Writeup-dmw0ng.html)

---

## 3. Hades

**Difficulty:** Hard | **Hosts:** Multiple (small AD enterprise network) | **Flags:** 5+

### Overview
Put your Active Directory enumeration and exploitation, lateral movement, and privilege escalation skills to the test within a small enterprise network. The goal is to gain a foothold, escalate privileges, and ultimately compromise the domain.

### Attack Chain
1. **Chasm (Initial Access):** Enumerate external services, find entry point
2. **Guardian:** AS-REP Roasting to obtain crackable hashes
3. **Lateral Movement:** Exploit Printer Bug from Linux, decrypt DPAPI secrets
4. **Delegation Abuse:** Kerberos Resource-Based Constrained Delegation (RBCD)
5. **DNS Spoofing:** Spoof Active Directory-Integrated DNS for further access
6. **Domain Compromise:** Full domain takeover

### Key Techniques
- AS-REP Roasting
- Printer Bug exploitation (from Linux)
- DPAPI secret decryption
- Kerberos Resource-Based Constrained Delegation (RBCD)
- Active Directory-Integrated DNS spoofing
- Multi-stage lateral movement

### Writeup Resources
- [snovvcrash Writeup](https://snovvcra.sh/2020/12/28/htb-hades.html)
- [flaviu.io Writeup](https://flaviu.io/endgame-hades/)
- [PuckieStyle Writeup](https://www.puckiestyle.nl/htb-endgame-hades/)

---

## 4. RPG

**Difficulty:** Hard | **Hosts:** Multiple | **Flags:** 6

### Overview
A challenging multi-machine scenario focused on Linux exploitation, network pivoting, and advanced techniques.

### Flag Stages
1. **"Would You Like to Play a Game?"** - Initial access
2. **"Sword and Mind"** - Enumeration and exploitation
3. **"One's Act, One's Profit"** - Lateral movement
4. **"The Source of Power"** - Privilege escalation
5. **"Wake From Death and Turn to Life"** - Advanced exploitation
6. **"Collapse of the Empire"** - Final domain/network compromise

### Key Techniques
- Multi-machine network pivoting
- Linux service exploitation
- Advanced enumeration
- Chained exploitation across hosts
- Final domain compromise

### Writeup Resources
- [snovvcrash Writeup](https://snovvcra.sh/2021/08/07/htb-rpg.html)
- [flaviu.io Writeup](https://flaviu.io/endgame-rpg/)
- [HTB Forum Discussion](https://forum.hackthebox.com/t/endgame-rpg/2928)

---

## 5. Ascension

**Difficulty:** Hard | **Hosts:** Multiple | **Flags:** 7

### Overview
An advanced endgame involving network enumeration, web application attacks, Active Directory hacking, and Windows privilege escalation.

### Flag Stages
1. **Takeoff** - Database enumeration (roles, grants, proxy accounts)
2. **Intercept** - Capturing credentials/traffic
3. **Contrails** - Lateral movement
4. **Wingman** - Privilege escalation
5. **Corridor** - Pivoting
6. **Upgrade** - Advanced exploitation
7. **Maverick** - Final compromise

### Key Techniques
- Blind SQL injection
- MSSQL exploitation and agent jobs
- MSSQL proxy abuse
- Network pivoting
- Resource-Based Constrained Delegation (RBCD)
- Multi-stage Active Directory attacks

### Writeup Resources
- [snovvcrash Writeup](https://snovvcra.sh/2024/04/30/htb-ascension.html)
- [GitHub PDF - Hackplayers](https://github.com/Hackplayers/hackthebox-writeups/blob/master/endgames/Ascension/snovvcrash-Ascension.pdf)
- [HTB Forum Discussion](https://forum.hackthebox.com/t/ascension-endgame/3584)

---

## Endgame Progression Path

```
P.O.O. (Beginner) --> Xen (Intermediate) --> Hades (Advanced) --> RPG (Advanced) --> Ascension (Advanced)
```

| Endgame | Focus | Prerequisite Skills |
|---------|-------|-------------------|
| P.O.O. | MSSQL, Web Enum | Basic web, SQL knowledge |
| Xen | Citrix, AD Basics | AD fundamentals, social engineering |
| Hades | AD Advanced | Kerberos, DPAPI, delegation attacks |
| RPG | Linux Networks | Linux exploitation, pivoting |
| Ascension | Full-spectrum AD | SQLi, MSSQL, RBCD, pivoting |
