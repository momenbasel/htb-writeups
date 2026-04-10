# Forensics Challenges

Writeups for HTB Digital Forensics challenges.

## Challenge Index

| Challenge | Difficulty | Techniques | Key Takeaway |
|-----------|-----------|------------|--------------|
| [Plaintext Tleasure](plaintext-treasure/) | Very Easy | PCAP Analysis, HTTP | Extracting credentials from unencrypted traffic |
| [Wrong Spooky Season](wrong-spooky-season/) | Very Easy | PCAP, Command Injection | Analyzing attack traffic in packet captures |
| [Illumination](illumination/) | Easy | Git History, Secrets | Finding secrets in git commit history |
| [MarketDump](market-dump/) | Easy | PCAP, Network Forensics | Analyzing network traffic for data exfiltration |
| [DVCT-1](dvct-1/) | Easy | Docker Forensics | Analyzing Docker image layers |
| [Perseverance](perseverance/) | Easy | Memory Forensics, Volatility | RAM dump analysis for credentials |
| [Litter](litter/) | Easy | PCAP, DNS Exfiltration | Detecting DNS-based data exfiltration |
| [Reminiscent](reminiscent/) | Easy | Memory Forensics, Volatility | Process analysis in memory dumps |
| [Diagnostic](diagnostic/) | Easy | PCAP, Malware Traffic | Analyzing malicious traffic patterns |
| [Rogue](rogue/) | Easy | PCAP, Wireless | Rogue access point detection |
| [oBfsC4t10n](obfuscation/) | Medium | JavaScript Deobfuscation | Reversing obfuscated JavaScript |
| [Seized](seized/) | Medium | Memory Forensics, Volatility3 | Advanced memory analysis techniques |
| [Forensic Encryption](forensic-encryption/) | Medium | Disk Forensics, LUKS | Encrypted disk analysis |
| [Automation](automation/) | Medium | PCAP, PowerShell Analysis | Detecting PowerShell-based attacks |
| [TrueSecrets](true-secrets/) | Medium | TrueCrypt, Disk Forensics | Analyzing TrueCrypt volumes |
| [Relic Maps](relic-maps/) | Medium | Malware Analysis, VBA | Analyzing malicious Office documents |
| [ProcNet](procnet/) | Medium | /proc Filesystem, Linux Forensics | Linux process forensics |
| [Phreaky](phreaky/) | Medium | PCAP, Email Forensics | Extracting attachments from email traffic |
| [Fake Boost](fake-boost/) | Medium | Discord, Malware Analysis | Analyzing Discord-based malware |
| [Game Invitation](game-invitation/) | Medium | Malware, HTA Analysis | Analyzing weaponized game invitations |
| [Nubilum-1](nubilum-1/) | Hard | Cloud Forensics, AWS | AWS CloudTrail log analysis |
| [Nubilum-2](nubilum-2/) | Hard | Cloud Forensics, S3 | AWS S3 bucket forensics |
| [PerfectScope](perfect-scope/) | Hard | Memory Forensics, Rootkit | Detecting rootkits in memory |

## Forensics Toolkit

| Tool | Purpose | Common Usage |
|------|---------|-------------|
| Volatility 3 | Memory analysis | `vol -f dump.raw windows.pslist` |
| Wireshark | PCAP analysis | GUI packet inspection |
| tshark | CLI PCAP analysis | `tshark -r capture.pcap -Y "http"` |
| Autopsy | Disk forensics | GUI disk image analysis |
| binwalk | Firmware/file extraction | `binwalk -e firmware.bin` |
| foremost | File carving | `foremost -i disk.img` |
| strings | String extraction | `strings -n 8 binary` |
| exiftool | Metadata extraction | `exiftool image.jpg` |
| CyberChef | Data transformation | Encoding, decoding, crypto |
| FTK Imager | Disk imaging | Forensic image creation |

## Analysis Categories

### Network Forensics
Analyze packet captures for evidence of attacks, data exfiltration, and malicious communications.

### Memory Forensics  
Extract artifacts from RAM dumps including processes, network connections, injected code, and credentials.

### Disk Forensics
Examine disk images for deleted files, encrypted volumes, hidden partitions, and filesystem artifacts.

### Cloud Forensics
Investigate cloud-specific artifacts including CloudTrail logs, S3 access logs, and IAM activity.
