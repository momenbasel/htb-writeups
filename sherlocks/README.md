# HTB Sherlocks

Writeups for Hack The Box Sherlock DFIR (Digital Forensics & Incident Response) investigation labs.

Sherlocks are defensive security labs that simulate real-world security incidents. You investigate evidence, analyze artifacts, and answer forensic questions to solve the case.

## By Difficulty

| Difficulty | Path | Count | Focus |
|------------|------|-------|-------|
| [Easy](easy/) | `sherlocks/easy/` | 15+ | Log Analysis, Basic DFIR, Simple Investigations |
| [Medium](medium/) | `sherlocks/medium/` | 15+ | Memory Forensics, Malware Triage, AD Investigations |
| [Hard](hard/) | `sherlocks/hard/` | 8+ | APT Investigations, Complex IR, Multi-Source Correlation |

---

## Easy Sherlocks

| Sherlock | Category | Focus | Key Skills |
|----------|----------|-------|------------|
| [Noted](easy/noted/) | Endpoint | Endpoint forensics, file analysis | File system timeline analysis |
| [Knock Knock](easy/knock-knock/) | Network | Network traffic analysis | Wireshark, packet analysis |
| [Logjammer](easy/logjammer/) | Log Analysis | Windows event logs | Event ID analysis, PowerShell |
| [Reaper](easy/reaper/) | Endpoint | Process analysis | Process tree, parent-child relationships |
| [Bumblebee](easy/bumblebee/) | Malware | Malware delivery analysis | Email analysis, dropper behavior |
| [Campfire-1](easy/campfire-1/) | Active Directory | Kerberoasting detection | 4769 events, AD attack detection |
| [Campfire-2](easy/campfire-2/) | Active Directory | DCSync detection | 4662 events, replication detection |
| [Recollection](easy/recollection/) | Memory | Memory forensics basics | Volatility, process analysis |
| [Pikaptcha](easy/pikaptcha/) | Endpoint | User activity forensics | Browser artifacts, user timeline |
| [I Cant Believe Its Not Sutter](easy/sutter/) | Network | HTTP traffic analysis | Web attack detection |
| [Unit42](easy/unit42/) | Malware | Phishing analysis | Email header analysis |
| [TraceBack](easy/traceback/) | Endpoint | Linux forensics | Auth logs, bash history |
| [Brutus](easy/brutus/) | Log Analysis | Brute force detection | Failed login analysis |
| [Meerkat](easy/meerkat/) | Network | IDS alert analysis | Suricata/Snort alert triage |
| [Fragmented](easy/fragmented/) | Disk | File recovery | File carving, deleted files |

## Medium Sherlocks

| Sherlock | Category | Focus | Key Skills |
|----------|----------|-------|------------|
| [Crown Jewel 1](medium/crown-jewel-1/) | Active Directory | AD attack investigation | NTDS.dit dump detection |
| [Crown Jewel 2](medium/crown-jewel-2/) | Active Directory | Lateral movement | Pass-the-Hash, ticket abuse |
| [Noxious](medium/noxious/) | Network | DNS poisoning | LLMNR/NBT-NS poisoning detection |
| [Tracer](medium/tracer/) | Threat Hunting | Advanced threat hunting | IOC correlation |
| [Subatomic](medium/subatomic/) | Malware | Electron app malware | Node.js malware analysis |
| [Heartbreaker](medium/heartbreaker/) | Malware | Ransomware investigation | Ransomware behavior analysis |
| [Jugglin](medium/jugglin/) | Web | Web application attack | SQLi, RCE chain detection |
| [Nubilum-1](medium/nubilum-1/) | Cloud | AWS forensics | CloudTrail analysis |
| [TickTock](medium/ticktock/) | Endpoint | Scheduled task abuse | Persistence mechanism detection |
| [Hyperfiletable](medium/hyperfiletable/) | Disk | NTFS forensics | MFT analysis, ADS |
| [Lockpick-1](medium/lockpick-1/) | Malware | Ransomware crypto | Encryption analysis |
| [Lockpick-2](medium/lockpick-2/) | Malware | Ransomware recovery | Key recovery techniques |
| [Ore](medium/ore/) | Endpoint | Cryptominer detection | Process, network indicators |
| [RogueOne](medium/rogueone/) | Network | C2 detection | C2 traffic patterns |
| [Wanted](medium/wanted/) | OSINT/IR | Threat actor attribution | IOC enrichment |

## Hard Sherlocks

| Sherlock | Category | Focus | Key Skills |
|----------|----------|-------|------------|
| [OpTinselTrace](hard/optinseltrace/) | APT | Full APT investigation | Multi-artifact correlation |
| [Pandora](hard/pandora/) | Cloud | Cloud breach IR | Multi-cloud investigation |
| [Constellation](hard/constellation/) | APT | Advanced threat actor | TTP mapping, MITRE ATT&CK |
| [Litter](hard/litter/) | Network | Data exfiltration | DNS tunneling detection |
| [Knock Knock 2](hard/knock-knock-2/) | Network | Advanced network forensics | Encrypted traffic analysis |
| [CrownJewel-3](hard/crown-jewel-3/) | Active Directory | Domain compromise | Full AD attack chain |
| [Specter](hard/specter/) | Memory | Advanced memory forensics | Rootkit detection |
| [BlackEnergy](hard/black-energy/) | ICS | Industrial incident | ICS/SCADA forensics |

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

## Essential DFIR Tools

| Tool | Purpose |
|------|---------|
| Volatility 3 | Memory forensics |
| Chainsaw | Windows event log analysis |
| Hayabusa | Windows event log fast forensics |
| KAPE | Evidence collection |
| Eric Zimmerman Tools | Windows artifact parsing |
| Autopsy | Disk forensics |
| Wireshark/tshark | Network capture analysis |
| Velociraptor | Endpoint detection & forensics |
| YARA | Pattern matching for malware |
| CyberChef | Data transformation |
