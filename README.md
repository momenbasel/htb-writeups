# Hack The Box Writeups

> A curated, community-driven collection of Hack The Box writeups covering machines, challenges, ProLabs, Sherlocks, CTF events, and more - organized by category, difficulty, and technique.

```
  ___ ___  ___________    __      __         .__  __                                  
 /   |   \ \__    ___/   /  \    /  \________|__|/  |_  ____  __ ________  ______     
/    ~    \  |    |      \   \/\/   /\_  __ \|  \   __\/ __ \|  |  \____ \/  ___/     
\    Y    /  |    |       \        /  |  | \/|  ||  | \  ___/|  |  /  |_> >___ \      
 \___|_  /   |____|        \__/\  /   |__|   |__||__|  \___  >____/|   __/____  >     
       \/                       \/                         \/      |__|       \/      
```

[![Stars](https://img.shields.io/github/stars/momenbasel/htb-writeups?style=for-the-badge&color=yellow)](https://github.com/momenbasel/htb-writeups/stargazers)
[![Forks](https://img.shields.io/github/forks/momenbasel/htb-writeups?style=for-the-badge&color=blue)](https://github.com/momenbasel/htb-writeups/network/members)
[![Contributors](https://img.shields.io/github/contributors/momenbasel/htb-writeups?style=for-the-badge&color=green)](https://github.com/momenbasel/htb-writeups/graphs/contributors)
[![License](https://img.shields.io/github/license/momenbasel/htb-writeups?style=for-the-badge)](LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/momenbasel/htb-writeups?style=for-the-badge&color=red)](https://github.com/momenbasel/htb-writeups/commits/main)

---

## What's Inside

| Section | Description | Count |
|---------|-------------|-------|
| [Machines](#machines) | Boot2root walkthroughs (Easy to Insane) | 300+ |
| [Challenges](#challenges) | CTF-style challenges across 12 categories | 400+ |
| [ProLabs](#prolabs) | Enterprise-grade lab walkthroughs | 6 |
| [Sherlocks](#sherlocks) | DFIR & Blue Team investigations | 38+ |
| [CTF Events](#ctf-events) | Official HTB CTF competition writeups | 6 events |
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
| [DarkZero](machines/hard/DarkZero/) | Windows | Hard | Cross-Forest Trust, AD Abuse | Apr 2026 |
| [Snapped](machines/medium/Snapped/) | Linux | Medium | Nginx UI RCE, Static Site Exploitation | Mar 2026 |
| [Browsed](machines/medium/Browsed/) | Linux | Medium | Browser Extension Exploitation, Headless Chrome | Mar 2026 |
| [Previous](machines/medium/Previous/) | Linux | Medium | NextJS Exploitation, Framework Abuse | Jan 2026 |
| [Retire](machines/hard/Retire/) | Windows | Hard | Active Directory, Kerberos Abuse | Jan 2026 |
| [Fries](machines/hard/Fries/) | Linux | Hard | Web Exploitation, Custom Exploitation | Nov 2025 |
| [NanoCorp](machines/hard/NanoCorp/) | Linux | Hard | Custom Protocol, Binary Analysis | Nov 2025 |
| [Hercules](machines/insane/Hercules/) | Linux | Insane | Multi-Stage Exploitation | Oct 2025 |
| [Signed](machines/medium/Signed/) | Linux | Medium | Code Signing Bypass, Certificate Abuse | Oct 2025 |
| [University](machines/insane/University/) | Linux | Insane | Multi-Vector Attack, Complex Chain | Aug 2025 |
| [Dog](machines/easy/Dog/) | Linux | Easy | Backdrop CMS, Web Exploitation | Jul 2025 |
| [Mirage](machines/hard/Mirage/) | Windows | Hard | Active Directory, ADCS | Jul 2025 |
| [Voleur](machines/medium/Voleur/) | Linux | Medium | Data Exfiltration, Custom Exploitation | Jul 2025 |
| [RustyKey](machines/hard/RustyKey/) | Linux | Hard | Rust Binary Exploitation | Jun 2025 |
| [TombWatcher](machines/medium/TombWatcher/) | Linux | Medium | Custom Service Exploitation | Jun 2025 |
| [Haze](machines/hard/Haze/) | Windows | Hard | Splunk Enterprise Exploitation | Jun 2025 |
| [Certificate](machines/hard/Certificate/) | Windows | Hard | ADCS, Certificate Template Abuse | May 2025 |
| [Vintage](machines/hard/Vintage/) | Windows | Hard | Pure Active Directory, Kerberoasting | Apr 2025 |

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
| Web | [`challenges/web/`](challenges/web/) | 15+ | XSS, SQLi, SSTI, SSRF, Deserialization |
| Crypto | [`challenges/crypto/`](challenges/crypto/) | 10+ | RSA, AES, ECC, Custom Ciphers |
| Forensics | [`challenges/forensics/`](challenges/forensics/) | 10+ | Memory Analysis, Disk Forensics, Network PCAP |
| Reversing | [`challenges/reversing/`](challenges/reversing/) | 10+ | x86/x64, ARM, .NET, Java, Obfuscation |
| Pwn | [`challenges/pwn/`](challenges/pwn/) | 8+ | Stack/Heap Overflow, ROP, Format Strings |
| Mobile | [`challenges/mobile/`](challenges/mobile/) | 5+ | Android APK, iOS, Frida, Smali |
| Hardware | [`challenges/hardware/`](challenges/hardware/) | 3+ | UART, SPI, Firmware Extraction |
| OSINT | [`challenges/osint/`](challenges/osint/) | 5+ | Geolocation, Social Media, Metadata |
| Misc | [`challenges/misc/`](challenges/misc/) | 5+ | Scripting, Logic, Encoding |
| Stego | [`challenges/stego/`](challenges/stego/) | 5+ | Image, Audio, LSB, Steghide |
| Blockchain | [`challenges/blockchain/`](challenges/blockchain/) | 3+ | Smart Contracts, Solidity, DeFi |
| AI/ML | [`challenges/ai-ml/`](challenges/ai-ml/) | 3+ | Adversarial ML, Model Exploitation |

---

## ProLabs

Enterprise-grade lab environments simulating real corporate networks. These writeups cover multi-machine attack paths, lateral movement, and domain dominance.

| Lab | Difficulty | Machines | Focus |
|-----|-----------|----------|-------|
| [Dante](prolabs/dante/) | Beginner | 14 | Network Pentesting Fundamentals |
| [Offshore](prolabs/offshore/) | Intermediate | 21 | Active Directory, Multi-Domain |
| [RastaLabs](prolabs/rastalabs/) | Intermediate | 15 | Red Team Simulation, Phishing |
| [Zephyr](prolabs/zephyr/) | Intermediate | 17 | ADCS, DPAPI, Constrained Delegation |
| [Cybernetics](prolabs/cybernetics/) | Advanced | 20+ | Advanced AD, Cross-Forest Attacks |
| [APTLabs](prolabs/aptlabs/) | Advanced | 20+ | APT Simulation, Multi-Vector |

---

## Sherlocks

DFIR (Digital Forensics & Incident Response) investigation labs. Blue team scenarios where you investigate security incidents and answer forensic questions.

| Category | Path | Focus |
|----------|------|-------|
| Easy | [`sherlocks/easy/`](sherlocks/easy/) | Log Analysis, Basic DFIR |
| Medium | [`sherlocks/medium/`](sherlocks/medium/) | Memory Forensics, Malware Triage |
| Hard | [`sherlocks/hard/`](sherlocks/hard/) | APT Investigation, Complex IR |

### Featured Sherlocks

| Name | Difficulty | Focus Area |
|------|-----------|------------|
| Crown Jewel 1 | Medium | AD Attack Investigation, NTDS.dit Analysis |
| Crown Jewel 2 | Medium | Lateral Movement Detection |
| Noted | Easy | Endpoint Forensics |
| Bumblebee | Medium | Malware Analysis |
| OpTinselTrace | Hard | APT Campaign Investigation |
| Knock Knock | Easy | Network Forensics |
| Noxious | Medium | DNS Poisoning Investigation |
| Tracer | Hard | Advanced Threat Hunting |

---

## CTF Events

Writeups from official Hack The Box competitive CTF events.

| Event | Year | Path | Highlights |
|-------|------|------|------------|
| Cyber Apocalypse | 2025 | [`ctf-events/cyber-apocalypse-2025/`](ctf-events/cyber-apocalypse-2025/) | Web, Crypto, Pwn, Forensics |
| Business CTF | 2025 | [`ctf-events/business-ctf-2025/`](ctf-events/business-ctf-2025/) | Enterprise Security Focus |
| University CTF | 2025 | [`ctf-events/university-ctf-2025/`](ctf-events/university-ctf-2025/) | Academic Team Competition |
| Cyber Apocalypse | 2024 | [`ctf-events/cyber-apocalypse-2024/`](ctf-events/cyber-apocalypse-2024/) | Hacker Royale Theme |
| Business CTF | 2024 | [`ctf-events/business-ctf-2024/`](ctf-events/business-ctf-2024/) | Corporate Scenario |
| University CTF | 2024 | [`ctf-events/university-ctf-2024/`](ctf-events/university-ctf-2024/) | Binary Badlands Theme |

---

## Endgames

Multi-machine, multi-stage scenarios that simulate real penetration testing engagements. See [`endgames/README.md`](endgames/README.md) for detailed walkthroughs.

| Endgame | Path | Flags | Focus |
|---------|------|-------|-------|
| P.O.O. | [`endgames/poo/`](endgames/poo/) | 5 | MSSQL Linked Servers, IIS Enumeration |
| Xen | [`endgames/xen/`](endgames/xen/) | 5+ | Citrix Breakout, AD, Phishing |
| Hades | [`endgames/hades/`](endgames/hades/) | 5+ | AS-REP Roast, DPAPI, RBCD, DNS Spoofing |
| RPG | [`endgames/rpg/`](endgames/rpg/) | 6 | Linux Exploitation, Multi-Host Pivoting |
| Ascension | [`endgames/ascension/`](endgames/ascension/) | 7 | Blind SQLi, MSSQL Proxy, RBCD |

---

## Fortresses

Multi-flag single-host challenges created by partner companies. Like machines on steroids. See [`fortresses/README.md`](fortresses/README.md) for detailed walkthroughs.

| Fortress | Creator | Flags | Focus |
|----------|---------|-------|-------|
| [Jet](fortresses/jet/) | Jet | 11 | Multi-service exploitation |
| [Akerva](fortresses/akerva/) | Akerva | 8 | WordPress, SNMP, web chains |
| [Context](fortresses/context/) | Context/Accenture | 7 | Web + infrastructure |
| [Synacktiv](fortresses/synacktiv/) | Synacktiv | Multiple | Symfony, AppSec, infrastructure |
| [AWS](fortresses/aws/) | Amazon Web Services | Multiple | Cloud security, IAM, Lambda, S3 |
| [Faraday](fortresses/faraday/) | Faraday | 7 | General offensive security |

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
2. Use the appropriate [template](templates/) for your writeup
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

## License

This project is licensed under the MIT License - see [LICENSE](LICENSE) for details.

---

<p align="center">
  <b>Found this useful? Give it a star and share it with your team!</b>
</p>
