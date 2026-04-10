# Hack The Box Writeups - The Ultimate HTB Resource

> The most comprehensive collection of **Hack The Box writeups**, **walkthroughs**, and **cheatsheets** on GitHub. 500+ machines, 400+ challenges, ProLabs, Sherlocks (DFIR), CTF events, penetration testing methodology, and OSCP/CPTS certification prep - all in one place.

```
  ___ ___  ___________    __      __         .__  __                                  
 /   |   \ \__    ___/   /  \    /  \________|__|/  |_  ____  __ ________  ______     
/    ~    \  |    |      \   \/\/   /\_  __ \|  \   __\/ __ \|  |  \____ \/  ___/     
\    Y    /  |    |       \        /  |  | \/|  ||  | \  ___/|  |  /  |_> >___ \      
 \___|_  /   |____|        \__/\  /   |__|   |__||__|  \___  >____/|   __/____  >     
       \/                       \/                         \/      |__|       \/      
```

[![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)
[![Stars](https://img.shields.io/github/stars/momenbasel/htb-writeups?style=for-the-badge&color=yellow)](https://github.com/momenbasel/htb-writeups/stargazers)
[![Forks](https://img.shields.io/github/forks/momenbasel/htb-writeups?style=for-the-badge&color=blue)](https://github.com/momenbasel/htb-writeups/network/members)
[![Contributors](https://img.shields.io/github/contributors/momenbasel/htb-writeups?style=for-the-badge&color=green)](https://github.com/momenbasel/htb-writeups/graphs/contributors)
[![License](https://img.shields.io/github/license/momenbasel/htb-writeups?style=for-the-badge)](LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/momenbasel/htb-writeups?style=for-the-badge&color=red)](https://github.com/momenbasel/htb-writeups/commits/main)

**Why this repo?** Unlike scattered blog posts and single-author collections, this is a **structured, searchable index** of the entire HTB ecosystem - machines from 2017 to 2026, every CTF event, every challenge category, every ProLab - cross-referenced by technique, difficulty, OS, and certification relevance. Whether you're preparing for **OSCP**, **CPTS**, **CRTO**, or just sharpening your skills, start here.

> **[Browse the site](https://momenbasel.github.io/htb-writeups/)** for the best experience - interactive tools, search, and dark theme.

---

## Interactive Tools

|  | Tool | Description |
|--|------|-------------|
| **[Machine Finder](https://momenbasel.github.io/htb-writeups/finder/)** | Search & Filter | Find machines by difficulty, OS, technique, CVE, or certification. Table and card views with real-time filtering. |
| **[Knowledge Graph](https://momenbasel.github.io/htb-writeups/graph/)** | Visual Explorer | Interactive D3.js force-directed graph mapping 70+ machines to 40+ techniques and 5 certifications. |
| **[Attack Paths](https://momenbasel.github.io/htb-writeups/attack-paths/)** | Flowcharts | Mermaid diagrams showing complete attack chains for 25+ machines - from recon to root. |
| **[Skill Trees](https://momenbasel.github.io/htb-writeups/skill-trees/)** | Progression Maps | Visual learning paths for AD attacks, web exploitation, Linux/Windows privesc, and cert preparation. |

---

## What's Inside

| Section | Description | Count |
|---------|-------------|-------|
| [Machines](#machines) | Boot2root walkthroughs (Easy to Insane) | 300+ |
| [Challenges](#challenges) | CTF-style challenges across 12 categories | 400+ |
| [ProLabs](#prolabs) | Enterprise-grade lab walkthroughs with network topology diagrams | 6 |
| [Sherlocks](#sherlocks) | DFIR & Blue Team investigations | 70+ |
| [CTF Events](#ctf-events) | Official HTB CTF competition writeups | 14 events |
| [Endgames](#endgames) | Multi-machine scenario walkthroughs | 5 |
| [Fortresses](#fortresses) | Multi-flag single-host challenges | 6 |
| [Resources](#resources) | Tools, cheatsheets, cert prep, methodology | 10 guides |

---

## Machines

Writeups for retired HTB machines organized by difficulty. Each writeup includes enumeration, exploitation, and privilege escalation steps with full command output.

### By Difficulty

| Difficulty | Path | Machines |
|------------|------|----------|
| Easy | [`machines/easy/`](machines/easy/) | 120+ |
| Medium | [`machines/medium/`](machines/medium/) | 112+ |
| Hard | [`machines/hard/`](machines/hard/) | 60+ |
| Insane | [`machines/insane/`](machines/insane/) | 25+ |

### Recently Retired (2025-2026)

| Machine | OS | Difficulty | Key Techniques | Date |
|---------|----|------------|----------------|------|
| [DarkZero](https://0xdf.gitlab.io/2026/04/04/htb-darkzero.html) | Windows | Hard | Cross-Forest Trust, AD Abuse | Apr 2026 |
| [Snapped](https://0xdf.gitlab.io/2026/04/01/htb-snapped.html) | Linux | Medium | Nginx UI RCE, Static Site Exploitation | Mar 2026 |
| [Browsed](https://0xdf.gitlab.io/2026/03/28/htb-browsed.html) | Linux | Medium | Browser Extension Exploitation, Headless Chrome | Mar 2026 |
| [Previous](https://0xdf.gitlab.io/2026/01/10/htb-previous.html) | Linux | Medium | NextJS Exploitation, Framework Abuse | Jan 2026 |
| [Retire](machines/hard/) | Windows | Hard | Active Directory, Kerberos Abuse | Jan 2026 |
| [Fries](machines/hard/) | Linux | Hard | Web Exploitation, Custom Exploitation | Nov 2025 |
| [NanoCorp](machines/hard/) | Linux | Hard | Custom Protocol, Binary Analysis | Nov 2025 |
| [Hercules](machines/insane/) | Linux | Insane | Multi-Stage Exploitation | Oct 2025 |
| [Signed](https://0xdf.gitlab.io/2026/02/07/htb-signed.html) | Linux | Medium | Code Signing Bypass, Certificate Abuse | Oct 2025 |
| [University](https://0xdf.gitlab.io/2025/08/09/htb-university.html) | Linux | Insane | Multi-Vector Attack, Complex Chain | Aug 2025 |
| [Dog](https://0xdf.gitlab.io/2025/07/12/htb-dog.html) | Linux | Easy | Backdrop CMS, Web Exploitation | Jul 2025 |
| [Mirage](https://0xdf.gitlab.io/2025/11/22/htb-mirage.html) | Windows | Hard | Active Directory, ADCS | Jul 2025 |
| [Voleur](https://0xdf.gitlab.io/2025/11/01/htb-voleur.html) | Linux | Medium | Data Exfiltration, Custom Exploitation | Jul 2025 |
| [RustyKey](https://0xdf.gitlab.io/2025/11/08/htb-rustykey.html) | Linux | Hard | Rust Binary Exploitation | Jun 2025 |
| [TombWatcher](https://0xdf.gitlab.io/2025/10/11/htb-tombwatcher.html) | Linux | Medium | Custom Service Exploitation | Jun 2025 |
| [Haze](https://0xdf.gitlab.io/2025/06/28/htb-haze.html) | Windows | Hard | Splunk Enterprise Exploitation | Jun 2025 |
| [Certificate](https://0xdf.gitlab.io/2025/10/04/htb-certificate.html) | Windows | Hard | ADCS, Certificate Template Abuse | May 2025 |
| [Vintage](https://0xdf.gitlab.io/2025/04/26/htb-vintage.html) | Windows | Hard | Pure Active Directory, Kerberoasting | Apr 2025 |

### By Operating System

- **Linux** - [`machines/` filtered by OS](machines/) - Ubuntu, Debian, CentOS, custom distros
- **Windows** - [`machines/` filtered by OS](machines/) - Windows Server, Active Directory environments
- **FreeBSD/OpenBSD** - Rare but exist in the harder tiers

### By Technique

<details>
<summary><b>Active Directory</b> - Kerberoasting, AS-REP Roasting, ADCS, DCSync, Pass-the-Hash, BloodHound</summary>

| Machine | Difficulty | Specific AD Technique |
|---------|------------|-----------------------|
| DarkZero | Hard | Cross-Forest Trust Abuse |
| Vintage | Hard | Kerberoasting, Pure AD |
| Certificate | Hard | ADCS Certificate Template Abuse |
| Mirage | Hard | ADCS, Shadow Credentials |
| Haze | Hard | Splunk + AD Integration |
| Retire | Hard | Kerberos Delegation Abuse |

</details>

<details>
<summary><b>Web Exploitation</b> - SQLi, XSS, SSRF, SSTI, LFI/RFI, Deserialization</summary>

| Machine | Difficulty | Specific Web Technique |
|---------|------------|-----------------------|
| Dog | Easy | Backdrop CMS RCE |
| Browsed | Medium | Browser Extension RCE |
| Previous | Medium | NextJS Framework Exploitation |
| Snapped | Medium | Nginx UI Admin Panel RCE |
| Fries | Hard | Custom Web App Exploitation |

</details>

<details>
<summary><b>Binary Exploitation</b> - Buffer Overflow, ROP, Heap Exploitation, Format Strings</summary>

| Machine | Difficulty | Specific Technique |
|---------|------------|-----------------------|
| RustyKey | Hard | Rust Binary Exploitation |
| NanoCorp | Hard | Custom Protocol Exploitation |

</details>

<details>
<summary><b>Cloud & Infrastructure</b> - AWS, Azure, GCP, Docker, Kubernetes</summary>

| Machine | Difficulty | Specific Technique |
|---------|------------|-----------------------|
| Hercules | Insane | Container Escape, Cloud Metadata |

</details>

---

## Challenges

CTF-style challenges organized by category. Each writeup includes the challenge description, approach, solution, and lessons learned.

| Category | Path | Count | Key Skills |
|----------|------|-------|------------|
| Web | [`challenges/web/`](challenges/web/) | 75+ | XSS, SQLi, SSTI, SSRF, Deserialization, JWT, GraphQL |
| Crypto | [`challenges/crypto/`](challenges/crypto/) | 93+ | RSA, AES, ECC, Padding Oracle, PRNG, Lattice Attacks |
| Forensics | [`challenges/forensics/`](challenges/forensics/) | 33+ | Memory Analysis, Disk Forensics, Network PCAP, Malware |
| Reversing | [`challenges/reversing/`](challenges/reversing/) | 44+ | x86/x64, .NET, Python, Angr, Anti-Debug, VM |
| Pwn | [`challenges/pwn/`](challenges/pwn/) | 61+ | Stack/Heap Overflow, ROP, SROP, Kernel, tcache |
| Mobile | [`challenges/mobile/`](challenges/mobile/) | 10+ | Android APK, Frida, Smali, Certificate Pinning |
| Hardware | [`challenges/hardware/`](challenges/hardware/) | 11+ | UART, SPI, Firmware, VHDL, RF Analysis |
| OSINT | [`challenges/osint/`](challenges/osint/) | 12+ | Geolocation, Social Media, DNS, Metadata |
| Misc | [`challenges/misc/`](challenges/misc/) | 35+ | Scripting, Logic, Encoding, Pickle, Pyjail |
| Stego | [`challenges/stego/`](challenges/stego/) | 12+ | Image, Audio, LSB, Steghide, ImageMagick |
| Blockchain | [`challenges/blockchain/`](challenges/blockchain/) | 10+ | Solidity, Smart Contracts, ERC-721, ECDSA |
| AI/ML | [`challenges/ai-ml/`](challenges/ai-ml/) | 5+ | Adversarial ML, Prompt Injection, LLM Bypass |

---

## ProLabs

Enterprise-grade lab environments simulating real corporate networks. These writeups cover multi-machine attack paths, lateral movement, and domain dominance.

| Lab | Difficulty | Machines | Focus |
|-----|-----------|----------|-------|
| [Dante](prolabs/#{0}) | Beginner | 14 | Network Pentesting Fundamentals |
| [Offshore](prolabs/#{0}) | Intermediate | 21 | Active Directory, Multi-Domain |
| [RastaLabs](prolabs/#{0}) | Intermediate | 15 | Red Team Simulation, Phishing |
| [Zephyr](prolabs/#{0}) | Intermediate | 17 | ADCS, DPAPI, Constrained Delegation |
| [Cybernetics](prolabs/#{0}) | Advanced | 20+ | Advanced AD, Cross-Forest Attacks |
| [APTLabs](prolabs/#{0}) | Advanced | 20+ | APT Simulation, Multi-Vector |

---

## Sherlocks

DFIR (Digital Forensics & Incident Response) investigation labs. Blue team scenarios where you investigate security incidents and answer forensic questions.

| Category | Path | Focus |
|----------|------|-------|
| Easy | [`sherlocks/easy/`](sherlocks/) | Log Analysis, Basic DFIR |
| Medium | [`sherlocks/medium/`](sherlocks/) | Memory Forensics, Malware Triage |
| Hard | [`sherlocks/hard/`](sherlocks/) | APT Investigation, Complex IR |

### Featured Sherlocks

| Name | Difficulty | Focus Area | Writeup |
|------|-----------|------------|---------|
| Meerkat | Easy | Suricata IDS, Credential Stuffing, CVE-2022-25237 | [0xdf](https://0xdf.gitlab.io/2024/04/23/htb-sherlock-meerkat.html) |
| Brutus | Easy | SSH Brute Force, auth.log Analysis | [0xdf](https://0xdf.gitlab.io/2024/04/09/htb-sherlock-brutus.html) |
| Noted | Easy | Notepad++ Artifacts, Data Extortion | [0xdf](https://0xdf.gitlab.io/2024/06/13/htb-sherlock-noted.html) |
| Knock Knock | Easy | PCAP, FTP, Port Knocking, GonnaCry Ransomware | [0xdf](https://0xdf.gitlab.io/2023/12/04/htb-sherlock-knock-knock.html) |
| Bumblebee | Easy | phpBB SQLite, Access Log Analysis | [0xdf](https://0xdf.gitlab.io/2024/05/22/htb-sherlock-bumblebee.html) |
| Crown Jewel-1 | Medium | NTDS.dit Dump, Volume Shadow Copy Service | [CyberWired](https://www.cyberwiredtraining.net/writeups/htb-sherlock-crownjewel-1-jezdr) |
| Noxious | Medium | LLMNR Poisoning, Rogue Device Detection | [0xdf](https://0xdf.gitlab.io/2024/09/04/htb-sherlock-noxious.html) |
| Subatomic | Medium | Electron Malware, Discord Hijacking | [0xdf](https://0xdf.gitlab.io/2024/04/18/htb-sherlock-subatomic.html) |
| Nubilum-1 | Medium | AWS CloudTrail, PoshC2, Cloud Forensics | [0xdf](https://0xdf.gitlab.io/2024/05/30/htb-sherlock-nubilum-1.html) |
| MisCloud | Medium | GCP Breach, Gitea Vulnerability | [CyberEthical](https://blog.cyberethical.me/htb-sherlock-miscloud) |
| OpTinselTrace (1-5) | Hard | Full APT Campaign Investigation (Christmas 2023) | [GitHub](https://github.com/dbissell6/DFIR/blob/main/WalkThroughs/OpTinselTrace-1-5.md) |
| APTNightmare | Hard | Advanced Persistent Threat Investigation | [GitHub](https://github.com/jon-brandy/hackthebox/blob/main/Categories/Sherlocks/APTNightmare/README.md) |

See the [full Sherlocks index](sherlocks/README.md) for 70+ Sherlocks with writeup links.

---

## CTF Events

Writeups from official Hack The Box competitive CTF events.

| Event | Year | Path | Highlights |
|-------|------|------|------------|
| Cyber Apocalypse | 2025 | [`ctf-events/cyber-apocalypse-2025/`](ctf-events/) | Web, Crypto, Pwn, Forensics |
| Business CTF | 2025 | [`ctf-events/business-ctf-2025/`](ctf-events/) | Enterprise Security Focus |
| University CTF | 2025 | [`ctf-events/university-ctf-2025/`](ctf-events/) | Academic Team Competition |
| Cyber Apocalypse | 2024 | [`ctf-events/cyber-apocalypse-2024/`](ctf-events/) | Hacker Royale Theme |
| Business CTF | 2024 | [`ctf-events/business-ctf-2024/`](ctf-events/) | Corporate Scenario |
| University CTF | 2024 | [`ctf-events/university-ctf-2024/`](ctf-events/) | Binary Badlands Theme |

---

## Endgames

Multi-machine, multi-stage scenarios that simulate real penetration testing engagements. See [`endgames/README.md`](endgames/README.md) for detailed walkthroughs.

| Endgame | Path | Flags | Focus |
|---------|------|-------|-------|
| P.O.O. | [`endgames/poo/`](endgames/) | 5 | MSSQL Linked Servers, IIS Enumeration |
| Xen | [`endgames/xen/`](endgames/) | 5+ | Citrix Breakout, AD, Phishing |
| Hades | [`endgames/hades/`](endgames/) | 5+ | AS-REP Roast, DPAPI, RBCD, DNS Spoofing |
| RPG | [`endgames/rpg/`](endgames/) | 6 | Linux Exploitation, Multi-Host Pivoting |
| Ascension | [`endgames/ascension/`](endgames/) | 7 | Blind SQLi, MSSQL Proxy, RBCD |

---

## Fortresses

Multi-flag single-host challenges created by partner companies. Like machines on steroids. See [`fortresses/README.md`](fortresses/README.md) for detailed walkthroughs.

| Fortress | Creator | Flags | Focus |
|----------|---------|-------|-------|
| [Jet](fortresses/) | Jet | 11 | Multi-service exploitation |
| [Akerva](fortresses/) | Akerva | 8 | WordPress, SNMP, web chains |
| [Context](fortresses/) | Context/Accenture | 7 | Web + infrastructure |
| [Synacktiv](fortresses/) | Synacktiv | Multiple | Symfony, AppSec, infrastructure |
| [AWS](fortresses/) | Amazon Web Services | Multiple | Cloud security, IAM, Lambda, S3 |
| [Faraday](fortresses/) | Faraday | 7 | General offensive security |

---

## Resources

### Tools by Category

<details>
<summary><b>Enumeration & Reconnaissance</b></summary>

| Tool | Purpose | Link |
|------|---------|------|
| Nmap | Port scanning & service detection | [nmap.org](https://nmap.org) |
| RustScan | Fast port scanner | [GitHub](https://github.com/RustScan/RustScan) |
| Gobuster | Directory/DNS/vhost brute-forcing | [GitHub](https://github.com/OJ/gobuster) |
| Feroxbuster | Recursive content discovery | [GitHub](https://github.com/epi052/feroxbuster) |
| ffuf | Fast web fuzzer | [GitHub](https://github.com/ffuf/ffuf) |
| enum4linux-ng | SMB/Samba enumeration | [GitHub](https://github.com/cddmp/enum4linux-ng) |

</details>

<details>
<summary><b>Web Exploitation</b></summary>

| Tool | Purpose | Link |
|------|---------|------|
| Burp Suite | Web proxy & scanner | [portswigger.net](https://portswigger.net/burp) |
| SQLMap | SQL injection automation | [GitHub](https://github.com/sqlmapproject/sqlmap) |
| Nuclei | Template-based vuln scanner | [GitHub](https://github.com/projectdiscovery/nuclei) |
| Caido | Modern web proxy | [caido.io](https://caido.io) |
| PayloadsAllTheThings | Payload repository | [GitHub](https://github.com/swisskyrepo/PayloadsAllTheThings) |

</details>

<details>
<summary><b>Active Directory</b></summary>

| Tool | Purpose | Link |
|------|---------|------|
| BloodHound | AD relationship mapping | [GitHub](https://github.com/SpecterOps/BloodHound) |
| Impacket | Network protocol toolkit | [GitHub](https://github.com/fortra/impacket) |
| Rubeus | Kerberos abuse | [GitHub](https://github.com/GhostPack/Rubeus) |
| Certipy | ADCS exploitation | [GitHub](https://github.com/ly4k/Certipy) |
| NetExec (nxc) | Network execution toolkit | [GitHub](https://github.com/Pennyw0rth/NetExec) |
| Ligolo-ng | Tunneling/pivoting | [GitHub](https://github.com/nicocha30/ligolo-ng) |

</details>

<details>
<summary><b>Privilege Escalation</b></summary>

| Tool | Purpose | Link |
|------|---------|------|
| LinPEAS | Linux privesc enumeration | [GitHub](https://github.com/peass-ng/PEASS-ng) |
| WinPEAS | Windows privesc enumeration | [GitHub](https://github.com/peass-ng/PEASS-ng) |
| pspy | Process monitoring (no root) | [GitHub](https://github.com/DominicBreuker/pspy) |
| PowerUp | Windows privesc PowerShell | [GitHub](https://github.com/PowerShellMafia/PowerSploit) |
| GTFOBins | Unix binary exploitation | [gtfobins.github.io](https://gtfobins.github.io) |
| LOLBAS | Windows living-off-the-land | [lolbas-project.github.io](https://lolbas-project.github.io) |

</details>

<details>
<summary><b>Forensics & DFIR</b></summary>

| Tool | Purpose | Link |
|------|---------|------|
| Volatility 3 | Memory forensics | [GitHub](https://github.com/volatilityfoundation/volatility3) |
| Autopsy | Disk forensics | [autopsy.com](https://www.autopsy.com) |
| Wireshark | Network capture analysis | [wireshark.org](https://www.wireshark.org) |
| CyberChef | Data transformation | [GitHub](https://github.com/gchq/CyberChef) |
| Chainsaw | Windows event log analysis | [GitHub](https://github.com/WithSecureLabs/chainsaw) |

</details>

<details>
<summary><b>Reverse Engineering</b></summary>

| Tool | Purpose | Link |
|------|---------|------|
| Ghidra | Binary analysis | [ghidra-sre.org](https://ghidra-sre.org) |
| IDA Free | Disassembler | [hex-rays.com](https://hex-rays.com/ida-free) |
| radare2 | CLI reverse engineering | [GitHub](https://github.com/radareorg/radare2) |
| Binary Ninja | Binary analysis platform | [binary.ninja](https://binary.ninja) |
| dnSpy | .NET decompiler | [GitHub](https://github.com/dnSpy/dnSpy) |

</details>

<details>
<summary><b>Binary Exploitation</b></summary>

| Tool | Purpose | Link |
|------|---------|------|
| pwntools | CTF exploit framework | [GitHub](https://github.com/Gallopsled/pwntools) |
| ROPgadget | ROP chain builder | [GitHub](https://github.com/JonathanSalwan/ROPgadget) |
| GEF | GDB enhanced features | [GitHub](https://github.com/hugsy/gef) |
| one_gadget | libc one-shot gadget | [GitHub](https://github.com/david942j/one_gadget) |
| checksec | Binary security checks | [GitHub](https://github.com/slimm609/checksec.sh) |

</details>

### Certification Prep

Map your HTB journey to professional certifications.

<details>
<summary><b>OSCP (Offensive Security Certified Professional)</b></summary>

**Recommended HTB Machines for OSCP Prep:**

| Machine | Difficulty | Key Skills |
|---------|-----------|------------|
| Lame | Easy | Samba RCE, Basic Exploitation |
| Legacy | Easy | MS08-067, Windows Exploitation |
| Blue | Easy | EternalBlue (MS17-010) |
| Optimum | Easy | HFS RCE, Windows Privesc |
| Shocker | Easy | Shellshock, Linux Basics |
| Nibbles | Easy | CMS Exploitation, File Upload |
| Bashed | Easy | PHP Webshell, Cron Abuse |
| Arctic | Easy | ColdFusion, Windows Exploitation |
| Grandpa | Easy | IIS WebDAV, Token Impersonation |
| Bastard | Medium | Drupal RCE, Windows Privesc |
| Cronos | Medium | DNS Zone Transfer, SQL Injection |
| SolidState | Medium | Apache James RCE, Cron Privesc |
| Node | Medium | API Exploitation, Kernel Exploit |
| Valentine | Easy | Heartbleed, tmux Hijack |
| Poison | Medium | LFI, VNC Tunneling |
| Sunday | Easy | Finger Enumeration, Shadow File |
| DevOops | Medium | XXE, Git Secrets |
| Jeeves | Medium | Jenkins RCE, KeePass Cracking |
| Conceal | Hard | IPSec VPN, SNMP, JuicyPotato |

</details>

<details>
<summary><b>CPTS (Certified Penetration Testing Specialist)</b></summary>

**Recommended HTB Machines for CPTS Prep:**

| Machine | Difficulty | Key Skills |
|---------|-----------|------------|
| Active | Easy | AD Basics, GPP Abuse, Kerberoasting |
| Forest | Easy | AS-REP Roasting, DCSync |
| Sauna | Easy | AS-REP Roasting, WinRM |
| Monteverde | Medium | Azure AD, Password Spraying |
| Resolute | Medium | DNS Admin DLL Injection |
| Cascade | Medium | LDAP Enumeration, .NET Reversing |
| Blackfield | Hard | AS-REP, Backup Operators Privesc |
| Vintage | Hard | Pure AD Exploitation |
| Certificate | Hard | ADCS Exploitation |
| Support | Easy | LDAP, .NET Binary Analysis |

</details>

<details>
<summary><b>CRTO (Certified Red Team Operator)</b></summary>

Focus on ProLabs: **RastaLabs** and **Zephyr** are directly aligned with CRTO material.

| Machine/Lab | Type | Key Skills |
|-------------|------|------------|
| RastaLabs | ProLab | Phishing, C2, Lateral Movement |
| Zephyr | ProLab | ADCS, DPAPI, Constrained Delegation |
| Offshore | ProLab | Multi-Domain AD |
| Reel | Hard | Phishing, AppLocker Bypass |
| Mantis | Hard | AD, Kerberos, MS14-068 |

</details>

### Cheatsheets

| Cheatsheet | Description |
|------------|-------------|
| [Linux Enumeration](resources/cheatsheets/linux-enumeration.md) | Post-exploitation Linux enumeration commands |
| [Windows Enumeration](resources/cheatsheets/windows-enumeration.md) | Post-exploitation Windows enumeration commands |
| [Active Directory](resources/cheatsheets/active-directory.md) | AD attack methodology and commands |
| [Web Application](resources/cheatsheets/web-application.md) | Web exploitation techniques and payloads |
| [Privilege Escalation - Linux](resources/cheatsheets/privesc-linux.md) | Linux privilege escalation vectors |
| [Privilege Escalation - Windows](resources/cheatsheets/privesc-windows.md) | Windows privilege escalation vectors |
| [File Transfers](resources/cheatsheets/file-transfers.md) | Methods to transfer files between machines |
| [Reverse Shells](resources/cheatsheets/reverse-shells.md) | Reverse shell one-liners for all languages |
| [Pivoting & Tunneling](resources/cheatsheets/pivoting.md) | SSH tunneling, Chisel, Ligolo, SOCKS |
| [Password Attacks](resources/cheatsheets/password-attacks.md) | Cracking, spraying, brute-forcing |

### Methodology

| Guide | Description |
|-------|-------------|
| [HTB Machine Approach](resources/methodology/machine-approach.md) | How to systematically approach any HTB machine |
| [Note-Taking Template](resources/methodology/note-taking.md) | Structured note-taking for writeups |
| [Report Writing](resources/methodology/report-writing.md) | Professional pentest report template |

---

## Repository Structure

```
htb-writeups/
|-- machines/
|   |-- easy/                    # Easy difficulty machines
|   |-- medium/                  # Medium difficulty machines
|   |-- hard/                    # Hard difficulty machines
|   |-- insane/                  # Insane difficulty machines
|-- challenges/
|   |-- web/                     # Web exploitation challenges
|   |-- crypto/                  # Cryptography challenges
|   |-- forensics/               # Digital forensics challenges
|   |-- reversing/               # Reverse engineering challenges
|   |-- pwn/                     # Binary exploitation challenges
|   |-- mobile/                  # Mobile security challenges
|   |-- hardware/                # Hardware hacking challenges
|   |-- osint/                   # OSINT challenges
|   |-- misc/                    # Miscellaneous challenges
|   |-- stego/                   # Steganography challenges
|   |-- blockchain/              # Blockchain/smart contract challenges
|   |-- ai-ml/                   # AI/ML security challenges
|-- prolabs/
|   |-- dante/                   # Dante ProLab walkthrough
|   |-- offshore/                # Offshore ProLab walkthrough
|   |-- rastalabs/               # RastaLabs ProLab walkthrough
|   |-- zephyr/                  # Zephyr ProLab walkthrough
|   |-- cybernetics/             # Cybernetics ProLab walkthrough
|   |-- aptlabs/                 # APTLabs ProLab walkthrough
|-- sherlocks/
|   |-- easy/                    # Easy DFIR investigations
|   |-- medium/                  # Medium DFIR investigations
|   |-- hard/                    # Hard DFIR investigations
|-- ctf-events/                  # Official HTB CTF writeups
|-- endgames/                    # Multi-machine scenarios
|-- fortresses/                  # Fortress challenges
|-- resources/
|   |-- cheatsheets/             # Quick reference guides
|   |-- tools/                   # Tool guides and configs
|   |-- methodology/             # Approach guides and templates
|   |-- cert-prep/               # Certification preparation guides
|-- templates/                   # Writeup templates
```

---

## How to Use This Repository

### For Beginners
1. Start with **Easy machines** - they teach fundamentals
2. Follow the **[Machine Approach Guide](resources/methodology/machine-approach.md)** for a systematic method
3. Use the **[OSCP Prep](#oscp-offensive-security-certified-professional)** list if you're studying for certs
4. Try the machine yourself FIRST, then check the writeup

### For Intermediate Players
1. Focus on **Medium/Hard machines** by technique (AD, Web, etc.)
2. Work through a **ProLab** (start with Dante)
3. Attempt **Sherlock** challenges for blue team skills
4. Participate in **CTF events** using past writeups as training

### For Advanced Players
1. Target **Insane machines** and **Hard challenges**
2. Complete **Cybernetics** or **APTLabs** ProLabs
3. Write and contribute your own writeups
4. Develop custom tools and methodologies

---

## Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

**Quick start:**
1. Fork the repository
2. Use the appropriate [template](CONTRIBUTING.md) for your writeup
3. Place it in the correct category folder
4. Submit a Pull Request

**Writeup Requirements:**
- Only **retired** machines/challenges (no active content)
- Include all steps: enumeration, exploitation, privilege escalation
- Add screenshots or command output for key steps
- Use the provided templates for consistency
- No spoilers for active content

---

## Disclaimer

These writeups are for **educational purposes only**. All content covers **retired** machines and challenges that are no longer active on the Hack The Box platform. Sharing solutions for active machines violates HTB's Terms of Service.

Always practice ethical hacking. Only test systems you have explicit authorization to test.

---

## Related Resources

| Resource | Description |
|----------|-------------|
| [HackTricks](https://book.hacktricks.wiki/) | Comprehensive pentesting reference |
| [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings) | Payload and bypass collection |
| [The Hacker Recipes](https://thehacker.recipes/) | Structured attack recipes |
| [GTFOBins](https://gtfobins.github.io/) | Unix binary exploitation reference |
| [LOLBAS](https://lolbas-project.github.io/) | Windows living-off-the-land binaries |
| [WADComs](https://wadcoms.github.io/) | Windows/AD command reference |
| [RevShells](https://www.revshells.com/) | Reverse shell generator |
| [CyberChef](https://gchq.github.io/CyberChef/) | Data transformation toolkit |
| [SecLists](https://github.com/danielmiessler/SecLists) | Wordlists for security testing |
| [IppSec.rocks](https://ippsec.rocks/) | Searchable index of IppSec's HTB videos |

---

## License

This project is licensed under the MIT License - see [LICENSE](LICENSE) for details.

---

<p align="center">
  <b>If this helped you pop a box or pass a cert, drop a star - it helps others find it too.</b>
  <br><br>
  <a href="https://github.com/momenbasel/htb-writeups/stargazers"><img src="https://img.shields.io/github/stars/momenbasel/htb-writeups?style=social" alt="Star this repo"></a>
</p>

---

<sub>**Keywords:** hack the box writeups, HTB walkthrough, hackthebox machines, HTB challenges, OSCP prep machines, CPTS certification, penetration testing writeups, CTF writeups, active directory hacking, privilege escalation, web exploitation, binary exploitation, digital forensics, incident response, red team, blue team, cybersecurity training, ethical hacking, infosec resources, security cheatsheets</sub>
