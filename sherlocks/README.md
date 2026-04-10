---
layout: default
title: Sherlocks
nav_order: 5
description: "70+ HTB Sherlock DFIR investigation writeups"
permalink: /sherlocks/
---

# HackTheBox Sherlocks - Comprehensive Index

> Complete index of all known HackTheBox Sherlock DFIR investigation labs with writeup links, difficulty ratings, categories, and key techniques.

Sherlocks are defensive security labs that simulate real-world security incidents. You investigate evidence, analyze artifacts, and answer forensic questions to solve the case.

---

## Summary

| Difficulty | Path | Count | Focus |
|------------|------|-------|-------|
| [Easy](#easy-sherlocks) | [`sherlocks/easy/`](easy/) | 25+ | Log Analysis, Basic DFIR, Simple Malware Triage |
| [Medium](#medium-sherlocks) | [`sherlocks/medium/`](medium/) | 30+ | Memory Forensics, AD Attacks, Cloud IR, Complex Malware |
| [Hard](#hard-sherlocks) | [`sherlocks/hard/`](hard/) | 15+ | APT Investigation, Complex IR, Multi-Source Correlation |
| [Insane](#insane-sherlocks) | - | 5+ | Full-Scale Incident Response, Advanced Threat Actor Attribution |

---

## Easy Sherlocks

| # | Sherlock | Category | Key Techniques | Writeup |
|---|---------|----------|----------------|---------|
| 1 | Meerkat | SOC | Suricata alerts, PCAP, credential stuffing, CVE-2022-25237 (Bonitasoft) | [0xdf](https://0xdf.gitlab.io/2024/04/23/htb-sherlock-meerkat.html) |
| 2 | Brutus | DFIR | SSH brute force, auth.log analysis, failed login detection | [0xdf](https://0xdf.gitlab.io/2024/04/09/htb-sherlock-brutus.html) |
| 3 | BFT | DFIR | Master File Table (MFT) analysis, Zimmerman tools, ZoneID | [0xdf](https://0xdf.gitlab.io/2024/04/17/htb-sherlock-bft.html) |
| 4 | Unit42 | Malware Analysis | Sysmon logs, UltraVNC backdoor, Palo Alto Unit42 campaign | [0xdf](https://0xdf.gitlab.io/2024/04/11/htb-sherlock-unit42.html) |
| 5 | Noted | DFIR | Notepad++ artifacts, AppData analysis, data extortion | [0xdf](https://0xdf.gitlab.io/2024/06/13/htb-sherlock-noted.html) |
| 6 | Bumblebee | DFIR | phpBB SQLite database, access logs, web shell analysis | [0xdf](https://0xdf.gitlab.io/2024/05/22/htb-sherlock-bumblebee.html) |
| 7 | Knock Knock | Network Forensics | PCAP, password spray, FTP, port knocking, SSH, GonnaCry ransomware | [0xdf](https://0xdf.gitlab.io/2023/12/04/htb-sherlock-knock-knock.html) |
| 8 | i-like-to | DFIR | MOVEit Transfer compromise, CVE investigation | [0xdf](https://0xdf.gitlab.io/2023/11/17/htb-sherlock-i-like-to.html) |
| 9 | Recollection | DFIR | Memory forensics, Volatility, process analysis | [jon-brandy GitHub](https://github.com/jon-brandy/hackthebox/blob/main/Categories/Sherlocks/Recollection/README.md) |
| 10 | Logjammer | Log Analysis | Windows Event Logs (Security, System, Defender, Firewall, PowerShell), scheduled tasks | [Medium - Chicken0248](https://medium.com/@chaoskist/htb-sherlocks-write-up-logjammer-5474d716ce66) |
| 11 | Pikaptcha | DFIR | Registry Explorer, NetworkMiner, PowerShell run dialog abuse, fake CAPTCHA | [0xdf](https://0xdf.gitlab.io/2024/10/22/htb-sherlock-pikaptcha.html) |
| 12 | Campfire-1 | Active Directory | Kerberoasting detection, PowerView, Rubeus, Event ID 4769 | [0xdf](https://0xdf.gitlab.io/2024/06/24/htb-sherlock-campfire-1.html) |
| 13 | Campfire-2 | Active Directory | AS-REP Roasting, event log analysis, compromised accounts | [0xdf](https://0xdf.gitlab.io/2024/07/26/htb-sherlock-campfire-2.html) |
| 14 | Safecracker | DFIR | Malicious file forensic analysis | [adeadfed](https://adeadfed.com/posts/htb-sherlock-safecracker-writeup/) |
| 15 | Litter | SOC | Network forensics, data exfiltration indicators | [Medium - jniket](https://medium.com/@johnniketas/hackthebox-sherlock-litter-9307c7b48f5b) |
| 16 | Heartbreaker-Continuum | Malware Analysis | PEStudio, Ghidra code analysis, VirusTotal, MITRE ATT&CK mapping | [Medium - Mattv0](https://medium.com/@mattv0/htb-heartbreaker-continuum-writeup-3c0bcb311956) |
| 17 | Lockpick | Malware Analysis | Ransomware analysis, encryption key recovery | [Thamizhiniyan GitBook](https://thamizhiniyancs.gitbook.io/writeups/hackthebox/sherlocks/malware-analysis/easy/heartbreaker-continuum) |
| 18 | Lockpick 2.0 | Malware Analysis | Advanced ransomware, key recovery techniques | [Thamizhiniyan GitBook](https://thamizhiniyancs.gitbook.io/writeups/hackthebox/sherlocks) |
| 19 | SmartyPants | DFIR | Windows RDP event logs, Smart Screen debug logs | [jon-brandy GitHub](https://github.com/jon-brandy/hackthebox) |
| 20 | JingleBell | DFIR | Holiday-themed forensics investigation | [abubakar-shahid GitHub](https://github.com/abubakar-shahid/HackTheBox-Sherlocks-Writeups) |
| 21 | JenkreadD | DFIR | Jenkins CVE-2024-23897 arbitrary file read | [HTB Blog](https://www.hackthebox.com/blog/sherlocks) |
| 22 | Packet Puzzle | Network Forensics | PCAP analysis, Japanese crypto firm cyberattack | [Medium - Deven](https://medium.com/@devenchhajed24/packet-puzzle-hack-the-box-sherlock-write-up-e94a6d3b9e6b) |

---

## Medium Sherlocks

| # | Sherlock | Category | Key Techniques | Writeup |
|---|---------|----------|----------------|---------|
| 1 | Crown Jewel-1 | Active Directory | NTDS.dit dump, Volume Shadow Copy Service, AD enumeration | [Medium - Drew](https://stumblesec.com/hackthebox-crownjewel-1-sherlock-walkthrough-2efb81522f2c) |
| 2 | Crown Jewel-2 | Active Directory | Lateral movement detection, Pass-the-Hash | [SystemWeakness](https://systemweakness.com/htb-sherlocks-write-up-crownjewel-1-0d380f22a2ba) |
| 3 | Noxious | Active Directory | LLMNR poisoning, rogue device detection, AD network recon | [0xdf](https://0xdf.gitlab.io/2024/09/04/htb-sherlock-noxious.html) |
| 4 | Reaper | Active Directory | NTLM relay attack, LLMNR response poisoning, Security Log | [0xdf](https://0xdf.gitlab.io/2024/08/22/htb-sherlock-reaper.html) |
| 5 | Subatomic | Malware Analysis | Electron app malware, fake game installer, Discord hijacking | [0xdf](https://0xdf.gitlab.io/2024/04/18/htb-sherlock-subatomic.html) |
| 6 | Constellation | DFIR | Insider threat, URL forensics, Discord/Google timeline | [0xdf](https://0xdf.gitlab.io/2024/06/05/htb-sherlock-constellation.html) |
| 7 | TickTock | DFIR | Spear-phishing investigation, email forensics | [Medium - jniket](https://medium.com/@johnniketas/hackthebox-sherlock-ticktock-d89b229bf573) |
| 8 | Tracer | Threat Hunting | PsExec detection, SOC alert investigation, lateral movement | [Medium - Ahmad](https://medium.com/@ahmad77.omari77/hackthebox-sherlocks-tracer-4f202b9548dd) |
| 9 | Hyperfiletable | DFIR | MFT parsing, analyzeMFT, MFTExplorer, ZoneID, file sizes | [Medium - L0rd$ud0](https://medium.com/@l0rd5ud0777/htb-sherlocks-hyperfiletable-writeup-9eed9b743726) |
| 10 | Nubilum-1 | Cloud Forensics | AWS CloudTrail logs, compromised EC2, PoshC2 C2 server | [0xdf](https://0xdf.gitlab.io/2024/05/30/htb-sherlock-nubilum-1.html) |
| 11 | Nubilum-2 | Cloud Forensics | AWS cloud forensics, advanced cloud investigation | [Medium - Chicken0248](https://medium.com/@chaoskist/htb-sherlocks-write-up-nubilum-2-d2a6d6aba3aa) |
| 12 | Jugglin | DFIR | Windows Subsystem for Linux (WSL) abuse, threat actor leveraging WSL | [Medium - Chicken0248](https://medium.com/@chaoskist/htb-sherlocks-write-up-jugglin-d52d7377f5d2) |
| 13 | Ultimatum | DFIR | WordPress compromise, Threat Actor investigation | [SystemWeakness](https://systemweakness.com/htb-sherlocks-write-up-ultimatum-b86de6fa5d40) |
| 14 | Ore | DFIR | Grafana artifacts, XMRIG cryptominer, CatScale, UNIX log analysis | [jon-brandy GitHub](https://github.com/jon-brandy/hackthebox) |
| 15 | RogueOne | Network Forensics | C2 traffic detection, network-based threat hunting | [jon-brandy GitHub](https://github.com/jon-brandy/hackthebox) |
| 16 | Lockpick 3.0 | Malware Analysis | Advanced ransomware variant, increased threat actor skillset | [Roy](https://roylau98.github.io/writeups/sherlockLockpick3) |
| 17 | Lockpick 4.0 | Malware Analysis | Latest ransomware evolution, key recovery | [Roy](https://roylau98.github.io/writeups/sherlockLockpick4) |
| 18 | MisCloud | Cloud Forensics | GCP breach, Gitea vulnerability, cloud misconfiguration | [Medium - Praj](https://prajshete17.medium.com/writeup-htb-sherlocks-miscloud-medium-93831e2fbf42) |
| 19 | Heartbreaker-Denouement | Cloud Forensics | CloudTrail log parsing, ELK stack analysis | [GitHub](https://github.com/septdney/htb-sherlock-heartbreaker-denouement) |
| 20 | ProcNet | Network Forensics | Network traffic analysis, malware investigation, API data capture | [Medium - d3lt4labs](https://medium.com/@d3lt4labs/procnet-htb-sherlock-write-up-94b0558bf47d) |
| 21 | Nuts | DFIR | File forensics, forensic image analysis | [itsrad.io](https://itsrad.io/blog/2025/Nuts-Write-Up/) |
| 22 | Fragility | DFIR | Exfiltrated file analysis, secret message decoding | [HTB Forum](https://forum.hackthebox.com/t/fragility-sherlock-labs/315895) |
| 23 | Exitiabilis | DFIR | HELK analysis, Cisco AnyConnect VPN compromise | [HTB Blog](https://www.hackthebox.com/blog/sherlocks) |
| 24 | Jinkies | DFIR | Investigation and forensics analysis | [warlocksmurf](https://github.com/warlocksmurf/HTBSherlock-writeups) |
| 25 | LATUS | DFIR | Multi-artifact forensic investigation | [HTB Forum](https://forum.hackthebox.com/t/sherlock-latus-help/326838) |
| 26 | Loggy | Log Analysis | Log aggregation and analysis, timeline construction | [jon-brandy GitHub](https://github.com/jon-brandy/hackthebox/blob/main/Categories/Sherlocks/Loggy/README.md) |

---

## Hard Sherlocks

| # | Sherlock | Category | Key Techniques | Writeup |
|---|---------|----------|----------------|---------|
| 1 | OpTinselTrace-1 | APT Investigation | Christmas-themed APT, initial access analysis | [warlocksmurf](https://github.com/warlocksmurf/HTBSherlock-writeups/blob/main/optinseltrace2023-sherlock/README.md) |
| 2 | OpTinselTrace-2 | APT Investigation | Lateral movement, persistence mechanisms | [Miranda-Bai GitHub](https://github.com/Miranda-Bai/Sherlocks) |
| 3 | OpTinselTrace-3 | APT Investigation | Volatility3, Chainsaw, memory + event log correlation | [Medium - Ari](https://medium.com/@ari.null/optinseltrace-3-hack-the-box-sherlock-writeup-dae64f3512fe) |
| 4 | OpTinselTrace-4 | APT Investigation | Data exfiltration, C2 communication analysis | [jon-brandy GitHub](https://github.com/jon-brandy/hackthebox) |
| 5 | OpTinselTrace-5 | APT Investigation | Full APT chain reconstruction, reporting | [warlocksmurf](https://github.com/warlocksmurf/HTBSherlock-writeups) |
| 6 | APTNightmare | APT Investigation | Advanced persistent threat investigation | [jon-brandy GitHub](https://github.com/jon-brandy/hackthebox/blob/main/Categories/Sherlocks/APTNightmare/README.md) |
| 7 | APTNightmare2 | APT Investigation | Continued APT investigation, advanced TTPs | [Medium - Jake](https://medium.com/@jakewhelihan/hackthebox-sherlock-writeup-aptnightmare2-48ecfcb5a00e) |
| 8 | BOughT | DFIR | Complex forensic investigation | [warlocksmurf](https://github.com/warlocksmurf/HTBSherlock-writeups) |
| 9 | Zenith | DFIR | Advanced incident response | [jon-brandy GitHub](https://github.com/jon-brandy/hackthebox) |
| 10 | Payload | Malware Analysis | Advanced malware analysis, payload extraction | [jon-brandy GitHub](https://github.com/jon-brandy/hackthebox) |
| 11 | CrashDump | DFIR | Crash dump analysis, kernel-level forensics | [jon-brandy GitHub](https://github.com/jon-brandy/hackthebox) |
| 12 | Lupin | DFIR | Advanced theft/exfiltration investigation | [jon-brandy GitHub](https://github.com/jon-brandy/hackthebox) |
| 13 | Secret Pictures | DFIR | Hidden data, steganographic forensics | [jon-brandy GitHub](https://github.com/jon-brandy/hackthebox) |
| 14 | Malevolent Modmaker | Malware Analysis | Custom malware module analysis | [jon-brandy GitHub](https://github.com/jon-brandy/hackthebox) |
| 15 | SalineBreeze-2 | DFIR | Advanced breach investigation | [jon-brandy GitHub](https://github.com/jon-brandy/hackthebox) |

---

## Insane Sherlocks

| # | Sherlock | Category | Key Techniques | Writeup |
|---|---------|----------|----------------|---------|
| 1 | Hunter | Threat Hunting | Full-scale threat hunting operation | [warlocksmurf](https://github.com/warlocksmurf/HTBSherlock-writeups) |
| 2 | Einlansen | DFIR | Complex multi-vector investigation | [HTB Forum](https://forum.hackthebox.com/) |

---

## Operation Series

### OpTinselTrace (Christmas 2023 - 5 Parts)
Christmas-themed APT investigation following the compromise of Father Christmas's operations by The Grinch. Five interconnected Sherlocks covering the full attack lifecycle.

| Part | Focus | Difficulty | Key Tools |
|------|-------|------------|-----------|
| OpTinselTrace-1 | Initial Access | Hard | Email analysis, URL investigation |
| OpTinselTrace-2 | Execution & Persistence | Hard | Registry, scheduled tasks |
| OpTinselTrace-3 | Lateral Movement | Hard | Volatility3, Chainsaw |
| OpTinselTrace-4 | Data Collection | Hard | Network forensics, C2 |
| OpTinselTrace-5 | Exfiltration & Reporting | Hard | Full chain reconstruction |

### Operation Blackout 2025

| Sherlock | Focus | Difficulty |
|----------|-------|------------|
| Phantom Check | Initial investigation | Medium |
| Smoke & Mirrors | Advanced deception detection | Medium |

### Lockpick Series (Ransomware Evolution)

| Version | Difficulty | Focus |
|---------|------------|-------|
| Lockpick | Easy | Basic ransomware analysis |
| Lockpick 2.0 | Easy | Ransomware recovery |
| Lockpick 3.0 | Medium | Advanced ransomware variant |
| Lockpick 4.0 | Medium | Latest ransomware evolution |

### Crown Jewel Series (Active Directory)

| Version | Difficulty | Focus |
|---------|------------|-------|
| Crown Jewel-1 | Medium | NTDS.dit dump, VSS analysis |
| Crown Jewel-2 | Medium | Lateral movement detection |

### Campfire Series (AD Attacks)

| Version | Difficulty | Focus |
|---------|------------|-------|
| Campfire-1 | Easy | Kerberoasting detection |
| Campfire-2 | Easy | AS-REP Roasting detection |

### Heartbreaker Series

| Version | Difficulty | Focus |
|---------|------------|-------|
| Heartbreaker-Continuum | Easy | Malware static analysis |
| Heartbreaker-Denouement | Medium | CloudTrail log investigation |

### Nubilum Series (Cloud Forensics)

| Version | Difficulty | Focus |
|---------|------------|-------|
| Nubilum-1 | Medium | AWS CloudTrail, EC2, PoshC2 |
| Nubilum-2 | Medium | Advanced AWS investigation |

### APTNightmare Series

| Version | Difficulty | Focus |
|---------|------------|-------|
| APTNightmare | Hard | APT investigation |
| APTNightmare2 | Hard | Advanced APT TTPs |

---

## By Category

### DFIR (Digital Forensics & Incident Response)
Noted, BFT, Recollection, Logjammer, Pikaptcha, SmartyPants, JingleBell, Safecracker, Constellation, TickTock, Hyperfiletable, Ultimatum, Ore, Nuts, Fragility, Exitiabilis, Jinkies, LATUS, BOughT, Zenith, CrashDump, Lupin, Secret Pictures, SalineBreeze-2

### Malware Analysis
Unit42, Heartbreaker-Continuum, Lockpick (1.0-4.0), Subatomic, Heartbreaker-Denouement, Payload, Malevolent Modmaker

### Active Directory
Campfire-1, Campfire-2, Crown Jewel-1, Crown Jewel-2, Noxious, Reaper

### Network Forensics
Meerkat, Knock Knock, Litter, RogueOne, ProcNet, Packet Puzzle

### Cloud Forensics
Nubilum-1, Nubilum-2, MisCloud, Heartbreaker-Denouement

### SOC / Threat Hunting
Meerkat, Litter, Tracer, Hunter

### Log Analysis
Brutus, Logjammer, Loggy

### APT Investigation
OpTinselTrace (1-5), APTNightmare, APTNightmare2

---

## Key Writeup Repositories

| Source | URL | Coverage |
|--------|-----|----------|
| 0xdf | [0xdf.gitlab.io](https://0xdf.gitlab.io/) | 15+ Sherlocks with deep analysis |
| jon-brandy | [GitHub](https://github.com/jon-brandy/hackthebox) | 35+ Sherlocks across all difficulties |
| abubakar-shahid | [GitHub](https://github.com/abubakar-shahid/HackTheBox-Sherlocks-Writeups) | DFIR-focused writeups |
| h0ny | [GitHub](https://github.com/h0ny/HackTheBox-Sherlocks-Writeups) | Multi-category Sherlocks |
| warlocksmurf | [GitHub](https://github.com/warlocksmurf/HTBSherlock-writeups) | OpTinselTrace + various |
| Chicken0248 | [Medium](https://medium.com/@chaoskist) | Nubilum, Logjammer, Pikaptcha, Jugglin, Noxious, Knock Knock, Reaper, Ultimatum |
| CyberKatalyst | [GitHub](https://github.com/CyberKatalyst/HackTheBox) | Sherlock writeup collection |
| Miranda-Bai | [GitHub](https://github.com/Miranda-Bai/Sherlocks) | Nubilum, OpTinselTrace, Recollection, RogueOne, Noted |
| Thamizhiniyan CS | [GitBook](https://thamizhiniyancs.gitbook.io/writeups/hackthebox/sherlocks) | DFIR, SOC, Malware Analysis |
| Roy | [Blog](https://roylau98.github.io/writeups/) | Lockpick 3.0, Lockpick 4.0 |

---

## Investigation Methodology

### Phase 1: Triage
1. Identify the type of incident (malware, intrusion, data breach, etc.)
2. Determine the scope (affected systems, users, timeframe)
3. Preserve evidence integrity

### Phase 2: Evidence Collection
1. Collect logs (Windows Event, syslog, application)
2. Collect memory dumps if available
3. Collect disk images or filesystem artifacts
4. Collect network captures

### Phase 3: Analysis
1. Build a timeline of events
2. Identify IOCs (IPs, domains, hashes, filenames)
3. Trace the attack chain (initial access -> execution -> persistence -> lateral movement -> exfiltration)
4. Map to MITRE ATT&CK framework

### Phase 4: Reporting
1. Document findings with evidence
2. Provide timeline
3. Recommend containment and remediation

---

## Essential DFIR Tools

| Tool | Purpose |
|------|---------|
| Volatility 3 | Memory forensics |
| Chainsaw | Windows event log analysis |
| Hayabusa | Windows event log fast forensics |
| KAPE | Evidence collection |
| Eric Zimmerman Tools | Windows artifact parsing (MFTECmd, Registry Explorer, etc.) |
| Autopsy | Disk forensics |
| Wireshark/tshark | Network capture analysis |
| NetworkMiner | Network forensic analysis |
| Velociraptor | Endpoint detection & forensics |
| YARA | Pattern matching for malware |
| CyberChef | Data transformation |
| PEStudio | PE file static analysis |
| Ghidra | Binary reverse engineering |
| analyzeMFT | MFT parsing |
| Event Log Explorer | Windows EVTX analysis |
