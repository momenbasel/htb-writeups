# HackTheBox - Hard Machines

> Comprehensive index of retired HTB Hard-difficulty machines with key techniques and attack path summaries.

**Total: 70+ machines** | Sorted roughly by retirement date (newest first)

---

## Machine Index

| # | Machine | OS | Key Techniques | Attack Path Summary |
|---|---------|-----|----------------|---------------------|
| 1 | DarkZero | Windows | Cross-Forest Trust Abuse, AD Exploitation | Enumerate cross-forest trust relationships, abuse SID history or trust keys for domain admin in foreign forest |
| 2 | Retire | Windows | Active Directory, Kerberos Delegation Abuse | Enumerate AD for constrained/unconstrained delegation, abuse Kerberos ticket forwarding for DA |
| 3 | Haze | Windows | Splunk Enterprise RCE, Active Directory | Exploit Splunk Enterprise vulnerability for initial access, pivot through AD for domain admin |
| 4 | Mirage | Windows | ADCS, Shadow Credentials, Active Directory | Enumerate ADCS for vulnerable certificate templates, abuse shadow credentials for lateral movement to DA |
| 5 | Certificate | Windows | ADCS Certificate Template Abuse, ESC1/ESC4 | Exploit misconfigured ADCS certificate templates (ESC1/ESC4/ESC8), request certificate as DA |
| 6 | Vintage | Windows | Pure AD Exploitation, Kerberoasting, Resource-Based Constrained Delegation | Kerberoast service accounts, abuse RBCD for lateral movement, DCSync for domain admin |
| 7 | RustyKey | Linux | Rust Binary Exploitation, Custom Crypto | Reverse Rust binary, exploit memory safety gap in unsafe block, abuse custom key derivation for root |
| 8 | NanoCorp | Linux | Custom Protocol Exploitation, Binary Analysis | Reverse-engineer custom network protocol, craft malicious packets for RCE, escalate via custom daemon |
| 9 | Fries | Linux | Web Exploitation, Custom Application Chain | Exploit custom web application with multi-step chain, abuse application trust for code execution as root |
| 10 | Tally | Windows | SharePoint Enumeration, KeePass, SQL Server xp_cmdshell, Rotten Potato | Enumerate SharePoint for KeePass DB, SQL Server creds, xp_cmdshell for shell, RottenPotato for SYSTEM |
| 11 | Bankrobber | Windows | XSS, SQL Injection, Custom Binary Buffer Overflow | Stored XSS to steal admin cookie, XSRF to trigger SQLi, exploit custom banking app binary overflow |
| 12 | Chainsaw | Linux | Blockchain Smart Contract Exploitation, IPFS, SUID Binary | Exploit vulnerable Solidity smart contract via Ganache, IPFS enumeration, SUID binary path for root |
| 13 | Sizzle | Windows | ADCS, SCF File Attack, Kerberoasting, CLM/AppLocker Bypass | SCF file in writable share for NTLM relay, certificate-based auth, Kerberoasting, bypass CLM for DCSync |
| 14 | Reel | Windows | Phishing via SMTP, AppLocker Bypass, AD ACL Abuse | Craft RTF phishing doc via SMTP, bypass AppLocker with HTA, abuse WriteOwner/WriteDACL AD ACLs for DA |
| 15 | Mantis | Windows | Active Directory, MS14-068, Kerberos | Enumerate IIS/MSSQL for creds, exploit MS14-068 Kerberos PAC vulnerability to forge golden ticket |
| 16 | Falafel | Linux | Type Juggling, SQL Injection (Boolean Blind), wget File Write | PHP type juggling auth bypass, boolean-based blind SQLi, wget file write exploit for root |
| 17 | Stacked | Linux | XSS, AWS LocalStack Exploitation, Lambda Function Abuse | XSS in mail to access internal app, exploit LocalStack to create malicious Lambda, container escape |
| 18 | Oouch | Linux | OAuth2 CSRF, D-Bus Exploitation, uwsgi Exploitation | Chain OAuth CSRF for admin token, D-Bus command injection, exploit uwsgi config for root |
| 19 | Travel | Linux | Memcached Poisoning, SSRF, LDAP Admin Abuse | SSRF to poison Memcached with serialized PHP, exploit WordPress custom theme, LDAP admin for root |
| 20 | Patents | Linux | XXE (Docx Upload), LFI, Custom Binary Exploit | XXE via DOCX upload to read files, LFI chain, exploit custom binary with format string for root |
| 21 | Multimaster | Windows | SQL Injection (Unicode Bypass), .NET Reversing, AD Group Abuse | Unicode-encoded SQLi in API, crack hashes, reverse .NET DLL for creds, abuse AD group membership chain |
| 22 | Blackfield | Windows | AS-REP Roasting, BloodHound, Backup Operator Privilege | AS-REP roast for initial hash, BloodHound ForceChangePassword, Backup Operators to dump ntds.dit |
| 23 | Intense | Linux | SQLi (SQL Truncation), SNMP RCE, Custom Binary Exploitation | SQL truncation for admin token, SNMP authenticated RCE, exploit custom SUID with buffer overflow |
| 24 | Quick | Linux | QUIC/HTTP3 Protocol, ESI Injection, Race Condition | Enumerate QUIC service, ESI injection for SSRF, race condition in ticket system for admin creds |
| 25 | Undetected | Linux | Apache Backdoor Analysis, Kernel Module Backdoor | Detect and analyze Apache mod_sedbackdoor, trace custom kernel module backdoor, reverse for root creds |
| 26 | Gofer | Linux | Gopher SSRF, LibreOffice Macro Phishing, tcpdump Exploit | Gopher protocol SSRF via internal proxy, craft phishing doc with LibreOffice macro, tcpdump SUID for root |
| 27 | MonitorsThree | Linux | Cacti SQLi, Duplicati Backup Exploitation | SQL injection in Cacti for admin access, exploit Duplicati backup service auth bypass for root |
| 28 | Compiled | Linux | Gitea, Go Binary Exploitation, Git Hook Abuse | Exploit Gitea instance, reverse Go binary for vulnerabilities, abuse Git hooks for code execution as root |
| 29 | Usage | Linux | Laravel SQLi (Blind), laravel-admin Custom Exploit | Blind SQL injection in Laravel password reset, exploit laravel-admin file upload for shell, monitor cron for root |
| 30 | Napper | Windows | Naplistener Malware Analysis, .NET Reversing, Elasticsearch | Analyze Naplistener backdoor, reverse .NET implant, extract Elasticsearch secrets for admin |
| 31 | Visual | Windows | Gitea, MSBuild/Visual Studio Project RCE, FullPowers | Submit malicious VS project to Gitea for build-triggered RCE, FullPowers to restore privileges, GodPotato |
| 32 | Snoopy | Linux | DNS Zone Transfer, Bind9 CVE, SSH MitM via DNS Hijack | DNS enumeration, exploit Bind9 CVE to update DNS, MitM SSH via DNS redirect, Git hook abuse for root |
| 33 | Cerberus | Windows/Linux | Icinga Web CVE, SSSD Exploitation, AD Certificate Abuse | Exploit Icinga Web 2 CVE for RCE, pivot Linux to Windows via SSSD secrets, ADCS ESC7 for DA |
| 34 | Vessel | Linux | PyInstaller Reversing, Node.js Regex ReDoS, PDF Exploitation | Reverse PyInstaller binary for creds, ReDoS bypass auth, exploit custom PDF generation for root |
| 35 | Absolute | Windows | Active Directory, LDAP Enumeration, Kerberos Relay, Shadow Credentials | Image metadata LDAP creds, Kerberos relay attack, shadow credential abuse for DA |
| 36 | Sekhmet | Windows/Linux | Kerberos CC Ticket Abuse, ADCS ESC8, Cross-Domain Trust | Steal CC ticket from Linux, abuse ADCS ESC8 via NTLM relay, pivot cross-domain for enterprise admin |
| 37 | Scramble | Windows | Kerberos-Only Auth (no NTLM), Silver Ticket, .NET Deserialization | Enumerate with Kerberos only, forge silver ticket for MSSQL, .NET BinaryFormatter deserialization for SYSTEM |
| 38 | Intelligence | Windows | ITSM PDF Metadata, DNS Record Abuse, GMSA Password Read, Constrained Delegation | Extract creds from PDF metadata, abuse DNS records, read GMSA password, constrained delegation for DA |
| 39 | Writer | Linux | SQL Injection, Postfix/SMTP Exploitation, apt PreInvoke | Union SQLi for file read, SMTP command injection via malicious email handler, apt pre-invoke cron for root |
| 40 | PivotAPI | Windows | AS-REP Roasting, MSSQL, Exchange Exploitation, SeManageVolume | AS-REP roast, pivot through MSSQL linked servers, abuse Exchange permissions, SeManageVolume for SYSTEM |
| 41 | Object | Windows | Active Directory, Jenkins, AD ACL Chain (WriteOwner/GenericWrite) | Exploit Jenkins for initial access, enumerate AD ACLs, chain WriteOwner to ForceChangePassword for DA |
| 42 | APT | Windows | IPv6, Kerberos, AD Exploitation, NTLM Relay | Discover services on IPv6, Kerberos enumeration, NTLM relay to ADCS for certificate-based auth as DA |
| 43 | Acute | Windows | XLSX Metadata, PowerShell Web Access, BAT File Exploitation | Extract usernames from XLSX metadata, bruteforce PSWA, bat file to add to admin group, WinRM lateral |
| 44 | Anubis | Windows | ASP.NET ViewState RCE, Certify/ADCS | Exploit insecure ViewState deserialization, enumerate ADCS with Certify, abuse certificate template for DA |
| 45 | Extension | Linux | Gitea, Snippet Injection, Browser Extension Exploitation | Exploit Gitea for access, inject malicious code into shared snippets, browser extension RCE for root |
| 46 | Moderators | Linux | WordPress Custom Plugin Exploit, VNC Password Recovery, hashcat | Exploit WP plugin, discover VNC password in config, crack for SSH, hashcat custom rule for root |
| 47 | RainyDay | Linux | API Exploitation, Python Pickle Deserialization, Docker Secret | Exploit API for initial access, Python Pickle deserialization, Docker secret extraction for root |
| 48 | Pollution | Linux | XXE, Redis Exploitation, Prototype Pollution to RCE | XXE for internal access, Redis command injection, JavaScript prototype pollution for code execution as root |
| 49 | Derailed | Linux | Ruby on Rails WebSocket, Xterm.js Exploitation, openmediavault | Rails WebSocket hijacking for admin, Xterm.js injection for shell, openmediavault cron for root |
| 50 | Sekhmet | Windows | Kerberos Authentication, ADCS ESC8, Cross-Forest Trust | Abuse Kerberos CC ticket, NTLM relay to ADCS ESC8, cross-forest pivot for enterprise admin |
| 51 | Response | Linux | HAProxy SSRF, Custom Proxy Chain, LDAP Injection, mTLS | Chain SSRF through HAProxy, LDAP injection for creds, mTLS certificate forge for root service |
| 52 | Carpediem | Linux | Backdrop CMS, Docker Pivoting, Trudesk, Voip CDR | Exploit Backdrop CMS, pivot through Docker network, Trudesk ticket access, CDR analysis for root |
| 53 | Seventeen | Linux | Roundcube XSS, Exam Management SQLi, Docker Compose | SQLi in exam app, pivot via Roundcube stored XSS, Docker compose abuse for root |
| 54 | Yummy | Linux | JWT Forgery, Cron Race Condition, rsync Exploit | Forge JWT for admin access, exploit cron race condition, rsync to write authorized_keys as root |
| 55 | EscapeTwo | Windows | MSSQL xp_dirtree, NTLM Relay, ADCS ESC4 | Capture NTLM hash via xp_dirtree, relay to LDAP, abuse ADCS ESC4 certificate template for DA |
| 56 | Lantern | Linux | Blazor .NET RCE, Pivoting, Custom Service Exploit | Exploit Blazor application vulnerability, pivot internally, exploit custom service for root |
| 57 | Resource | Linux | SSH CA Certificate Abuse, ITDB Exploitation | Exploit IT database for SSH CA signing key, forge SSH certificates for admin users, escalate to root |
| 58 | Observed | Linux | Gitea, SQL Injection, Container Escape, Kernel Exploit | SQLi in Gitea, container escape via privileged container, kernel exploit for root on host |
| 59 | Titanic | Linux | Gitea Enumeration, Docker Registry, Flask Werkzeug | Enumerate Gitea repos, discover Docker registry secrets, exploit Flask debug for RCE, container escape |
| 60 | Blueprint | Windows | SharePoint Exploitation, ADCS, Constrained Delegation | Exploit SharePoint for initial foothold, ADCS cert abuse, constrained delegation for DA |

---

## Machines by OS

### Windows (30+)

Tally, Bankrobber, Sizzle, Reel, Mantis, Multimaster, Blackfield, Napper, Visual, Scramble, Intelligence, PivotAPI, Object, APT, Absolute, Sekhmet, DarkZero, Retire, Haze, Mirage, Certificate, Vintage, Cerberus (hybrid), Acute, Anubis, EscapeTwo, Blueprint

### Linux (35+)

Chainsaw, Ellingson, Falafel, Stacked, Oouch, Travel, Patents, Intense, Quick, Undetected, Gofer, MonitorsThree, Compiled, Usage, Snoopy, Vessel, Writer, Fries, NanoCorp, RustyKey, Extension, Moderators, RainyDay, Pollution, Derailed, Response, Carpediem, Seventeen, Yummy, Lantern, Resource, Observed, Titanic

---

## Machines by Technique Category

### Active Directory
| Machine | Specific AD Technique |
|---------|-----------------------|
| Sizzle | ADCS, SCF File, Kerberoasting, CLM Bypass |
| Reel | Phishing, AppLocker Bypass, AD ACL Abuse |
| Mantis | MS14-068 Kerberos PAC Exploit |
| Blackfield | AS-REP Roasting, BloodHound, Backup Operators |
| Multimaster | Unicode SQLi to AD, Group Membership Chain |
| Scramble | Kerberos-Only Auth, Silver Ticket |
| Intelligence | GMSA Password Read, Constrained Delegation |
| PivotAPI | AS-REP, MSSQL, Exchange, SeManageVolume |
| Object | Jenkins to AD ACL Chain |
| APT | IPv6, NTLM Relay to ADCS |
| Absolute | Kerberos Relay, Shadow Credentials |
| Sekhmet | CC Ticket, ADCS ESC8, Cross-Forest |
| Certificate | ADCS ESC1/ESC4/ESC8 |
| Vintage | Kerberoasting, RBCD, DCSync |
| Mirage | ADCS, Shadow Credentials |
| Haze | Splunk + AD Integration |
| DarkZero | Cross-Forest Trust Abuse |
| Retire | Kerberos Delegation Abuse |
| Cerberus | SSSD to AD, ADCS ESC7 |
| EscapeTwo | NTLM Relay, ADCS ESC4 |

### ADCS (Active Directory Certificate Services)
| Machine | ESC Variant |
|---------|-------------|
| Sizzle | Certificate-Based Auth |
| Certificate | ESC1/ESC4/ESC8 |
| Mirage | ESC + Shadow Credentials |
| Sekhmet | ESC8 via NTLM Relay |
| Cerberus | ESC7 |
| APT | NTLM Relay to ADCS |
| Anubis | Certify Template Abuse |
| EscapeTwo | ESC4 |

### Web Exploitation (Advanced)
| Machine | Specific Technique |
|---------|--------------------|
| Falafel | Type Juggling + Boolean Blind SQLi |
| Quick | QUIC/HTTP3 + ESI Injection |
| Bankrobber | Stored XSS + XSRF + SQLi |
| Travel | Memcached Poisoning + SSRF |
| Stacked | XSS + AWS LocalStack Lambda |
| Oouch | OAuth2 CSRF Chain |
| Gofer | Gopher Protocol SSRF |
| Pollution | XXE + Prototype Pollution to RCE |
| MonitorsThree | Cacti SQLi + Duplicati |

### Binary Exploitation
| Machine | Specific Technique |
|---------|--------------------|
| Tally | SQL Server + Rotten Potato |
| Bankrobber | Custom Binary Buffer Overflow |
| Intense | Custom SUID Buffer Overflow |
| Ellingson | ROP Chain on SUID Binary |
| RustyKey | Rust Binary Exploitation |
| NanoCorp | Custom Protocol Binary Analysis |

### Deserialization (Advanced)
| Machine | Specific Technique |
|---------|--------------------|
| Scramble | .NET BinaryFormatter |
| Anubis | ASP.NET ViewState |
| Patents | XXE + Format String |
| RainyDay | Python Pickle |
| Napper | .NET Implant Reversing |

### Blockchain / Smart Contract
| Machine | Specific Technique |
|---------|--------------------|
| Chainsaw | Solidity Smart Contract Exploit via Ganache |

### Container / Cloud
| Machine | Specific Technique |
|---------|--------------------|
| Stacked | AWS LocalStack Lambda Abuse |
| Carpediem | Docker Network Pivoting |
| Visual | MSBuild in Gitea + GodPotato |
| Observed | Container Escape + Kernel |
| Cerberus | Linux-to-Windows Pivot via SSSD |

### SSRF Chains
| Machine | Specific Technique |
|---------|--------------------|
| Travel | SSRF + Memcached Poisoning |
| Gofer | Gopher Protocol SSRF |
| Quick | ESI Injection for SSRF |
| Response | HAProxy SSRF Chain |
| Pollution | XXE + Internal SSRF |

---

## Difficulty Comparison: Hard vs Medium

Key differences that make these Hard:

1. **Multi-step chains** - Hard machines typically require 3-5 distinct exploits chained together
2. **Custom/obscure protocols** - QUIC/HTTP3, gRPC, custom TCP, Gopher protocol
3. **Advanced AD attacks** - ADCS, cross-forest trusts, Kerberos delegation, RBCD
4. **Binary exploitation** - Custom SUID binaries, buffer overflows, ROP chains
5. **Pivoting required** - Multiple network segments, container escapes, hybrid OS environments
6. **Anti-patterns** - AppLocker bypass, CLM bypass, WAF evasion, non-standard auth

---

## Writeup References

For each machine, recommended external writeup sources:

- **0xdf** - [0xdf.gitlab.io](https://0xdf.gitlab.io) - Exhaustive detail, alternative paths, beyond-root sections
- **IppSec** - [youtube.com/ippsec](https://youtube.com/ippsec) - Video walkthroughs with live debugging
- **HackTricks** - [book.hacktricks.xyz](https://book.hacktricks.xyz) - Technique reference
- **HTB Official** - [app.hackthebox.com](https://app.hackthebox.com) - Official writeups (VIP)

---

## Certification Relevance

### OSCP (Hard machines that build OSCP skills)
| Machine | Why |
|---------|-----|
| Tally | Multi-service enumeration, SQL Server, Potato attack |
| Blackfield | AS-REP, BloodHound, Backup Operators |
| Falafel | SQLi + creative file write |

### OSEP (Evasion and advanced exploitation)
| Machine | Why |
|---------|-----|
| Reel | Phishing + AppLocker bypass |
| Sizzle | CLM bypass + ADCS + Kerberoasting |
| Object | Jenkins + AD ACL chain |

### CPTS / CRTO (Active Directory focus)
| Machine | Why |
|---------|-----|
| Vintage | Pure AD, Kerberoasting, RBCD, DCSync |
| Certificate | Full ADCS exploitation |
| Intelligence | GMSA + Constrained Delegation |
| Sekhmet | Cross-forest + ADCS ESC8 |
| Absolute | Shadow Credentials + Kerberos Relay |

### CRTE (Red Team / Evasion)
| Machine | Why |
|---------|-----|
| Sizzle | Full AD chain with evasion |
| Reel | Phishing + AppLocker |
| APT | IPv6 + NTLM relay + ADCS |
| DarkZero | Cross-forest trust abuse |
