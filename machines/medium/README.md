---
layout: default
title: Medium Machines
parent: Machines
nav_order: 2
description: "112+ Medium HTB machine writeups with walkthroughs"
permalink: /machines/medium/
---

# HackTheBox - Medium Machines

> Comprehensive index of retired HTB Medium-difficulty machines with key techniques and attack path summaries.

**Total: 100+ machines** | Sorted roughly by retirement date (newest first)

---

## Machine Index

| # | Machine | OS | Key Techniques | Attack Path Summary | Writeup |
|---|---------|-----|----------------|---------------------|---------|
| 0a | Helix | Linux | Apache NiFi ExecuteSQL + H2 Java Alias RCE | Enumerate vhost `flow.helix.htb:8080/nifi`, abuse ExecuteSQL processor with malicious H2 JDBC URL, exploit H2 CREATE ALIAS Java aliases for RCE, sudo abuse for root | [Ibrahim](https://www.ibrahimisiaqbolaji.com/2026/05/helix-htb-write-up.html), [1337sheets](https://1337sheets.com/hack-the-box-htb-helix-writeup-medium-weekly-may-8th-2026/) |
| 0b | PingPong | Linux | Multi-Forest AD Trust + MSSQL Delegation + ADCS | Enumerate `ping.htb` + `pong.htb` cross-forest trust (NTLM disabled, Kerberos-only, AES256), MSSQL/Kerberos delegation to compromise dc2.pong.htb, extract cross-realm material, abuse AD CS template for Administrator@ping.htb cert | [HackIndex](https://hackindex.io/writeups/pingpong), [Axura](https://4xura.com/writeups-for-ctfs/htb/htb-writeup-pingpong/), [Ibrahim](https://www.ibrahimisiaqbolaji.com/2026/04/pingpong-htb-write-up.html), [Toshith](https://blog.toshith.in/story/NjY), [vapt.services](https://vapt.services/pingpong-htb-machine-a-realistic-red-team-simulation-in-disguise/) |
| 0c | Logging | Linux | Log Poisoning via User-Agent + LFI + Cron Privesc | LFI to read Apache logs, poison User-Agent header with PHP payload, trigger via include for shell, abuse misconfigured cron script for root | [1337sheets](https://1337sheets.com/hack-the-box-season-10-htb-logging-writeup-medium-weekly-april-18th-2026/), [Ibrahim](https://www.ibrahimisiaqbolaji.com/2026/04/logging-htb-write-up.html), [Axura](https://4xura.com/writeups-for-ctfs/htb/htb-writeup-logging/) |
| 0d | DevArea | Linux | Apache CXF SSRF CVE-2022-46364 + HoverFly CVE-2024-45388 + syswatch | XOP Include SSRF in CXF SOAP service reads files as dev_ryan, leak HoverFly creds, CVE-2024-45388 path traversal for RCE, syswatch bash overwrite for root | [TomatoBuster](https://tomatobuster.github.io/WriteUps/writeups/devarea.html), [Ibrahim](https://www.ibrahimisiaqbolaji.com/2026/03/devarea-htb-write-up.html), [CyberSecGuru](https://thecybersecguru.com/ctf-walkthroughs/beginners-guide-to-conquering-devarea-on-hackthebox/) |
| 0e | Interpreter | Linux | Mirth Connect CVE-2023-43208 + Python eval() RCE | Pre-auth Java XStream deserialization in Mirth Connect REST API for shell, dump SQLite hash for SSH, exploit Python eval() in root-bound localhost service for root | [jimmexploit](https://www.jimmexploit.blog/blog/htb-season-10-interpreter-writeup), [1337sheets](https://1337sheets.com/hack-the-box-season-ten-htb-interpreter-writeup-medium-weekly-february-twenty-first/), [CyberSecGuru](https://thecybersecguru.com/ctf-walkthroughs/mastering-interpreter-beginners-guide-from-hackthebox/) |
| 0f | VariaType | Linux | Git Disclosure + fontTools CVE-2025-66034 + FontForge CVE-2024-25082 + Setuptools CVE-2025-47273 | Dump exposed `.git`, recover deleted-commit creds, fontTools varLib XML injection writes PHP webshell, FontForge ZIP filename command injection for user, sudo Python script downloads remote setuptools wheel with path traversal for root | [havocsec](https://havocsec.me/pentesting/hackthebox/htb-variatype-complete-writeup), [ItsSunshineXD](https://itssunshinexd.medium.com/htb-writeup-variatype-dc75e409ee8e), [HTB-Andres](https://htb-writeup.beehiiv.com/p/variatype-machine-hackthebox), [Bimo754](https://github.com/Bimo754/Writeups-Public/blob/main/Linux/Medium/VariaType/README.md) |
| 0g | Principal | Linux | PAC4J JWT Forge + SSH Certificate Authority | Steal JWT public key, forge JWT with admin claims to access dashboard, abuse SSH CA signing config to issue admin-signed cert for root SSH | [0xdf](https://0xdf.gitlab.io/2026/03/30/htb-principal.html) |
| 0h | Soulmate | Linux | CrushFTP CVE Auth Bypass + Erlang SSH Hardcoded Creds | Exploit CrushFTP authentication bypass CVE chain for file read/admin access, find hardcoded Erlang SSH credentials, lateral via SSH | [0xdf](https://0xdf.gitlab.io/2026/02/14/htb-soulmate.html) |
| 0i | Slonik | Linux | NFS Misconfig + PostgreSQL RCE + pg_basebackup Cron | Mount writable NFS share for foothold, PostgreSQL `COPY ... FROM PROGRAM` RCE for service shell, abuse `pg_basebackup` cron writing to attacker-controlled path for root | [0xdf](https://0xdf.gitlab.io/2026/02/12/htb-slonik.html) |
| 0j | Bamboo | Linux | Squid Proxy Pivot + PaperCut Auth Bypass + Script Server | Bounce through Squid proxy to internal PaperCut, exploit auth bypass CVE chain, abuse server-side script execution for root | [0xdf](https://0xdf.gitlab.io/2026/02/03/htb-bamboo.html) |
| 0k | JobTwo | Windows | VBA Phishing + hMailServer Blowfish + Veeam CVE | VBA macro for foothold, decrypt hMailServer Blowfish-stored creds, exploit Veeam Backup unauth deserialization CVE for SYSTEM | [0xdf](https://0xdf.gitlab.io/2026/01/27/htb-jobtwo.html) |
| 0l | Imagery | Linux | Flask Stored XSS + Directory Traversal + Command Injection | Stored XSS in bug-report form steals admin cookie, directory traversal leaks source code revealing command injection in image processor, pivot to root via sudo misconfig | [0xdf](https://0xdf.gitlab.io/2026/01/24/htb-imagery.html) |
| 0m | HackNet | Debian | Django Pickle Deserialization + SSTI + GPG Key Crack | Authenticated Django pickle deserialization for shell, SSTI in admin email template, crack GPG private key passphrase to decrypt root credential vault | [0xdf](https://0xdf.gitlab.io/2026/01/17/htb-hacknet.html) |
| 0n | Store | Linux | XOR Static-Key Crypto Break + Node Inspector | Upload files to learn 9-byte XOR keystream, directory traversal to leak encrypted SFTP password file, decrypt with recovered XOR key, SFTP tunnel to localhost Node `--inspect` debugger for RCE | [0xdf](https://0xdf.gitlab.io/2025/10/30/htb-store.html) |
| 1 | Signed | Linux | Code Signing Bypass, Certificate Abuse | Forge code signature to deploy malicious update, escalate via trusted binary execution | [0xdf](https://0xdf.gitlab.io/2026/02/07/htb-signed.html) |
| 2 | Voleur | Linux | Data Exfiltration, Custom Service Exploitation | Exploit custom data service for initial access, abuse misconfigured backup for root | [0xdf](https://0xdf.gitlab.io/2025/11/01/htb-voleur.html) |
| 3 | TombWatcher | Linux | Custom Service Exploitation, Process Injection | Attack custom monitoring daemon, pivot via writable service config to root | [0xdf](https://0xdf.gitlab.io/2025/10/11/htb-tombwatcher.html) |
| 4 | Snapped | Linux | Nginx UI RCE, Static Site Exploitation | Exploit Nginx UI admin panel for RCE, abuse static site generator config for root | [0xdf](https://0xdf.gitlab.io/2026/04/01/htb-snapped.html) |
| 5 | Browsed | Linux | Browser Extension Exploitation, Headless Chrome | Exploit vulnerable browser extension in headless Chrome instance, escalate via debug port | [0xdf](https://0xdf.gitlab.io/2026/03/28/htb-browsed.html) |
| 6 | Previous | Linux | Next.js Exploitation, Framework Abuse | Exploit Next.js middleware auth bypass (CVE-2025-29927), abuse server actions for root | [0xdf](https://0xdf.gitlab.io/2026/01/10/htb-previous.html) |
| 7 | Cicada | Windows | Active Directory, SMB Enumeration, Password Spraying | Enumerate SMB shares for creds, password spray AD users, abuse SeBackupPrivilege for DA | [0xdf](https://0xdf.gitlab.io/2025/02/15/htb-cicada.html) |
| 8 | Sightless | Linux | SQLPad RCE, Froxlor Exploitation | Exploit SQLPad template injection for container escape, pivot to Froxlor admin for root | [0xdf](https://0xdf.gitlab.io/2025/01/11/htb-sightless.html) |
| 9 | Alert | Linux | XSS, LFI, Markdown Renderer Exploitation | Stored XSS in markdown app to steal admin cookie, LFI to read sensitive config, group privesc | [0xdf](https://0xdf.gitlab.io/2025/03/22/htb-alert.html) |
| 10 | Instant | Linux | APK Reversing, API Token Extraction, SSH Key Recovery | Reverse Android APK for API token, access admin API for SSH key, login as root | [0xdf](https://0xdf.gitlab.io/2025/03/01/htb-instant.html) |
| 11 | Sea | Linux | WonderCMS XSS-to-RCE, System Monitor Exploitation | Chain XSS to install malicious WonderCMS theme for RCE, command injection in system monitor as root | [0xdf](https://0xdf.gitlab.io/2024/12/21/htb-sea.html) |
| 12 | PermX | Linux | Chamilo LMS RCE, ACL Abuse | Exploit Chamilo LMS unauthenticated file upload for RCE, abuse sudoers ACL script for root | [0xdf](https://0xdf.gitlab.io/2024/11/02/htb-permx.html), [Medium](https://medium.com/@pk2212/htb-permx-writeup-walkthrough-df745737713b) |
| 13 | GreenHorn | Linux | Pluck CMS RCE, Depixelization | Crack Pluck CMS password hash, upload webshell via module, depixelize blurred password image for root | [0xdf](https://0xdf.gitlab.io/2024/12/07/htb-greenhorn.html) |
| 14 | IClean | Linux | XSS, SSTI, qpdf Exploitation | XSS to steal admin session, SSTI in invoice generator for RCE, abuse qpdf sudo for root | [0xdf](https://0xdf.gitlab.io/2024/08/03/htb-iclean.html) |
| 15 | Headless | Linux | Blind XSS, Command Injection | Blind XSS in user-agent to steal admin cookie, command injection in admin dashboard, syscheck script abuse | [0xdf](https://0xdf.gitlab.io/2024/07/20/htb-headless.html), [IppSec](https://www.youtube.com/watch?v=FDCpJbS1OuQ) |
| 16 | Mailing | Windows | LFI, CVE-2024-21413 (Outlook MonikerLink), LibreOffice Macro | LFI to get password hash, MonikerLink exploit to steal NTLM, LibreOffice macro for admin | [0xdf](https://0xdf.gitlab.io/2024/09/07/htb-mailing.html) |
| 17 | Perfection | Linux | SSTI (ERB), Password Cracking with Custom Mask | Server-Side Template Injection via newline bypass in ERB, crack sqlite hash with name-based mask | [0xdf](https://0xdf.gitlab.io/2024/07/06/htb-perfection.html), [IppSec](https://www.youtube.com/watch?v=zcVCLoMsOKA), [Medium](https://medium.com/@jamesjarviscyber/perfection-hackthebox-walkthrough-management-summary-a493c71355ac) |
| 18 | Crafty | Windows | Minecraft Log4Shell, RunasCs | Exploit Minecraft server via Log4Shell (CVE-2021-44228), find admin creds, RunasCs for admin | [0xdf](https://0xdf.gitlab.io/2024/06/15/htb-crafty.html) |
| 19 | Boardlight | Linux | Dolibarr CMS RCE, SUID Enlightenment Exploit | Default creds on Dolibarr, PHP RCE via injected code, SUID enlightenment_sys CVE for root | [0xdf](https://0xdf.gitlab.io/2024/09/28/htb-boardlight.html) |
| 20 | Editorial | Linux | SSRF, Git Repository Secrets | SSRF in image URL preview to discover internal API, enumerate git commits for credentials, sudo abuse | [0xdf](https://0xdf.gitlab.io/2024/10/19/htb-editorial.html), [Medium](https://medium.com/@firstprof.com/hackthebox-writeup-editorial-46df30be745f) |
| 21 | Clicker | Linux | NFS, SQL Injection (CRLF), Perl Privilege Escalation | Mount NFS share, CRLF injection to set admin role, Perl environment variable injection for root | [0xdf](https://0xdf.gitlab.io/2024/01/27/htb-clicker.html) |
| 22 | Drive | Linux | IDOR, SQLite Database Cracking, Gitea RCE | IDOR to access reserved files, crack SQLite password hashes, exploit Gitea instance for root | [0xdf](https://0xdf.gitlab.io/2024/02/17/htb-drive.html) |
| 23 | Jupiter | Linux | Grafana SQLi (PostgreSQL), Jupyter Notebook RCE, Shadow Simulation | SQL injection in Grafana API for RCE via PostgreSQL COPY, Jupyter notebook for lateral, binary sattrack with network config | [0xdf](https://0xdf.gitlab.io/2023/10/21/htb-jupiter.html), [IppSec](https://www.youtube.com/watch?v=HOvVjVw3pww), [erichogue](https://erichogue.ca/2023/10/HTB/Jupiter), [threatninja](https://threatninja.net/hack-the-box-jupiter-machine-walkthrough-medium-difficulty/) |
| 24 | Sandworm | Linux | PGP Signature Verification SSTI, Rust Sandbox Escape, Firejail CVE | SSTI in PGP signature verification (SSG), escape Rust sandbox, Firejail CVE-2022-31214 for root | [0xdf](https://0xdf.gitlab.io/2023/11/18/htb-sandworm.html), [IppSec](https://www.youtube.com/watch?v=RD58QpRu7u4), [erichogue](https://erichogue.ca/2023/11/HTB/Sandworm), [threatninja](https://threatninja.net/hack-the-box-sandworm-machine-walkthrough-medium/) |
| 25 | RedPanda | Linux | SSTI (Java/Spring Boot), XXE via Image Metadata, Path Traversal | SSTI in Spring Boot search, craft image with XXE metadata, path traversal to read root SSH key | [0xdf](https://0xdf.gitlab.io/2022/11/26/htb-redpanda.html), [IppSec](https://www.youtube.com/watch?v=HqIUffFdjuI) |
| 26 | Photobomb | Linux | Auth Bypass, Command Injection, PATH Hijack | Basic auth credential in JS source, command injection in image conversion, PATH hijack in cleanup script for root | [0xdf](https://0xdf.gitlab.io/2023/02/11/htb-photobomb.html), [IppSec](https://www.youtube.com/watch?v=wE5j2WLuMQI) |
| 27 | Bagel | Linux | .NET DLL Reversing, LFI, JSON Deserialization | LFI via WebSocket, reverse .NET DLL for deserialization gadget, exploit JSON handler for RCE, sudo dotnet | [0xdf](https://0xdf.gitlab.io/2023/06/03/htb-bagel.html) |
| 28 | Nunchucks | Linux | SSTI (Nunjucks), AppArmor Bypass via Shebang | SSTI in Nunjucks template engine, bypass AppArmor with Perl shebang trick for root capabilities | [0xdf](https://0xdf.gitlab.io/2021/11/02/htb-nunchucks.html) |
| 29 | Backdoor | Linux | WordPress Plugin Directory Traversal, /proc Enumeration, Screen Session | LFI via WordPress eBook plugin to read /proc, discover gdbserver, hijack root screen session | [0xdf](https://0xdf.gitlab.io/2022/04/23/htb-backdoor.html), [IppSec](https://www.youtube.com/watch?v=2EjUMTGkb_w) |
| 30 | Shibboleth | Linux | IPMI Hash Dump, Zabbix RCE, MariaDB CVE | Dump IPMI hashes via UDP, use creds on Zabbix for RCE, MariaDB CVE-2021-27928 for root | [0xdf](https://0xdf.gitlab.io/2022/04/02/htb-shibboleth.html) |
| 31 | Timing | Linux | LFI with PHP Filters, Mass Assignment, Git Repository | LFI via PHP filter chains, mass assignment to elevate role, find git repo for creds, wget sudo abuse | [0xdf](https://0xdf.gitlab.io/2022/06/04/htb-timing.html) |
| 32 | Paper | Linux | WordPress Secret Draft Leak, Rocket.Chat Bot RCE | Access secret draft via ?static=1, exploit Rocket.Chat bot with directory traversal, Polkit CVE for root | [0xdf](https://0xdf.gitlab.io/2022/06/18/htb-paper.html), [IppSec](https://www.youtube.com/watch?v=eI2k-M7Ugko) |
| 33 | Pandora | Linux | SNMP Enumeration, Pandora FMS SQLi, SUID Path Hijack | SNMP credential leak, SQL injection in Pandora FMS for admin, SUID binary PATH injection for root | [0xdf](https://0xdf.gitlab.io/2022/05/21/htb-pandora.html), [HackingArticles](https://www.hackingarticles.in/pandora-hackthebox-walkthrough/), [IppSec](https://www.youtube.com/watch?v=vSnB0AZDvjM) |
| 34 | Forge | Linux | SSRF, FTP via SSRF, PDB Exploitation | SSRF bypass with uppercase URL to reach internal admin, FTP credential retrieval, Python PDB sudo for root | [0xdf](https://0xdf.gitlab.io/2022/01/22/htb-forge.html) |
| 35 | Horizontall | Linux | Strapi RCE, Laravel Debug Mode RCE via Port Forward | Exploit Strapi CMS CVE-2019-18818/19609, port forward to internal Laravel, CVE-2021-3129 for root | [0xdf](https://0xdf.gitlab.io/2022/02/05/htb-horizontall.html) |
| 36 | Seal | Linux | GitBucket Source Review, Tomcat Symlink Bypass, Ansible Playbook | Discover Tomcat creds in GitBucket, symlink path traversal for WAR deploy, Ansible playbook run as root | [0xdf](https://0xdf.gitlab.io/2021/11/13/htb-seal.html) |
| 37 | Previse | Linux | Exec-After-Redirect (EAR), OS Command Injection, PATH Hijack | Bypass redirect to create account, command injection in log parsing, PATH hijack for root | [0xdf](https://0xdf.gitlab.io/2022/01/08/htb-previse.html), [IppSec](https://www.youtube.com/watch?v=bFqb0n68M8Q) |
| 38 | Cap | Linux | IDOR on PCAP Files, FTP Credential Sniffing, Linux Capabilities | IDOR to download PCAP with cleartext FTP creds, cap_setuid capability on Python for root | [0xdf](https://0xdf.gitlab.io/2021/10/02/htb-cap.html), [HackingArticles](https://www.hackingarticles.in/cap-hackthebox-walkthrough/), [IppSec](https://www.youtube.com/watch?v=O_z6o2xuvlw), [Medium](https://medium.com/@ruruuu/hackthebox-cap-writeup-95e2d8ca64c2) |
| 39 | Dynstr | Linux | DNS Update API Command Injection, nsupdate, SSH Key Plant | Command injection in no-ip DNS API, nsupdate to add DNS record, writable authorized_keys as bindmgr | [0xdf](https://0xdf.gitlab.io/2021/10/16/htb-dynstr.html) |
| 40 | Pit | Linux | SNMP Walk, SeedDMS Exploitation, SELinux Context | SNMP reveals CentOS config with SeedDMS path, exploit SeedDMS for RCE, SNMP exec script for root | [0xdf](https://0xdf.gitlab.io/2021/09/25/htb-pit.html) |
| 41 | Love | Windows | SSRF, Voting System File Upload RCE | SSRF to access internal site with admin creds, file upload RCE in Voting System, AlwaysInstallElevated | [0xdf](https://0xdf.gitlab.io/2021/08/07/htb-love.html), [HackingArticles](https://www.hackingarticles.in/love-hackthebox-walkthrough/), [IppSec](https://www.youtube.com/watch?v=V_7ubkfnPK4), [Medium](https://doomdesire.medium.com/love-writeup-hackthebox-f5a32aec9b56) |
| 42 | Spectra | Linux (ChromeOS) | WordPress, Autologin Config, initctl Exploit | WordPress creds from config backup, autologin password reuse, writable init job for root |
| 43 | Armageddon | Linux | Drupal 7 RCE (Drupalgeddon2), snap install Exploit | Drupalgeddon2 CVE-2018-7600 for shell, crack MySQL hash, sudo snap install with crafted snap for root | [0xdf](https://0xdf.gitlab.io/2021/07/24/htb-armageddon.html) |
| 44 | ScriptKiddie | Linux | Msfvenom APK Template CVE, Cron/Input Injection | Exploit CVE-2020-7384 via APK template upload, inject commands into cron-processed log, sudo abuse | [0xdf](https://0xdf.gitlab.io/2021/06/05/htb-scriptkiddie.html), [IppSec](https://www.youtube.com/watch?v=NoPhFSfO9hE) |
| 45 | Delivery | Linux | MatterMost, Email Verification Bypass, Hashcat Rules | Use osTicket to receive verification email, access MatterMost for creds, hashcat rule-based attack for root | [0xdf](https://0xdf.gitlab.io/2021/05/22/htb-delivery.html) |
| 46 | Time | Linux | Java Deserialization (Jackson), systemd Timer Abuse | Jackson deserialization CVE-2019-12384 via SSRF-to-RCE chain, writable systemd timer script for root | [0xdf](https://0xdf.gitlab.io/2021/04/03/htb-time.html) |
| 47 | Academy | Linux | HTB Academy Clone, Laravel .env Leak, Audit Log Deserialization | Register with admin role parameter, access admin panel, Laravel log viewer for RCE, composer sudo | [0xdf](https://0xdf.gitlab.io/2021/02/27/htb-academy.html) |
| 48 | Worker | Windows | SVN Repository, Azure DevOps, Azure Pipeline RCE | Checkout SVN for creds, access Azure DevOps, create pipeline with reverse shell, abuse Azure service | [0xdf](https://0xdf.gitlab.io/2021/01/30/htb-worker.html) |
| 49 | Buff | Windows | Gym Management System RCE, CloudMe Buffer Overflow | Unauthenticated file upload in Gym CMS, port forward to CloudMe, exploit stack buffer overflow | [0xdf](https://0xdf.gitlab.io/2020/11/21/htb-buff.html) |
| 50 | Tabby | Linux | LFI, Tomcat Manager WAR Deploy, LXD Group Escalation | LFI to read Tomcat users config, deploy WAR shell via host-manager, LXD container mount for root | [0xdf](https://0xdf.gitlab.io/2020/11/07/htb-tabby.html), [HackingArticles](https://www.hackingarticles.in/tabby-hackthebox-walkthrough/), [rana-khalil](https://rana-khalil.gitbook.io/hack-the-box-oscp-preparation/linux-boxes/tabby-writeup-w-o-metasploit), [snowscan](https://snowscan.io/htb-writeup-tabby/) |
| 51 | Blunder | Linux | Bludit CMS Brute Force Bypass, CVE-2019-16113, sudo < 1.8.28 | Bypass anti-brute-force via X-Forwarded-For, Bludit directory traversal RCE, sudo CVE-2019-14287 for root | [0xdf](https://0xdf.gitlab.io/2020/10/17/htb-blunder.html), [snowscan](https://snowscan.io/htb-writeup-blunder/), [Medium](https://medium.com/@paradoxis/hackthebox-blunder-d3669b73875c) |
| 52 | Cache | Linux | OpenEMR SQLi and Auth Bypass, Memcached, Docker Group | Exploit OpenEMR for creds, dump Memcached for SSH creds, Docker group for root | [0xdf](https://0xdf.gitlab.io/2020/10/10/htb-cache.html) |
| 53 | Magic | Linux | SQLi Login Bypass, Image Upload Webshell, SUID mysqldump | SQL injection to bypass login, embed PHP in image upload, SUID mysqldump path to root password | [0xdf](https://0xdf.gitlab.io/2020/08/22/htb-magic.html) |
| 54 | Admirer | Linux | Adminer CVE-2021-21311, Python Library Hijack | Discover Adminer via robots.txt, exploit MySQL local file read, Python shutil module hijack via sudo | [0xdf](https://0xdf.gitlab.io/2020/09/26/htb-admirer.html) |
| 55 | OpenAdmin | Linux | OpenNetAdmin RCE, Internal Apache, nano sudo | Exploit OpenNetAdmin CVE-2019-25065, pivot to internal Apache config for SSH key, nano sudo for root | [0xdf](https://0xdf.gitlab.io/2020/05/02/htb-openadmin.html), [HackingArticles](https://www.hackingarticles.in/hack-the-box-open-admin-box-walkthrough/), [snowscan](https://snowscan.io/htb-writeup-openadmin/), [Medium](https://musyokaian.medium.com/openadmin-walkthrough-hackthebox-8ab40e4072a5), [chr0x6eos](https://chr0x6eos.github.io/2020/05/02/htb-OpenAdmin.html), [ivanitlearning](https://ivanitlearning.wordpress.com/2020/09/24/hackthebox-openadmin/) |
| 56 | Traverxec | Linux | nostromo RCE, .htpasswd Cracking, journalctl sudo | Exploit nostromo nhttpd CVE-2019-16278, crack htpasswd for SSH key, journalctl pager escape for root | [0xdf](https://0xdf.gitlab.io/2020/04/11/htb-traverxec.html), [HackingArticles](https://www.hackingarticles.in/traverxec-hackthebox-walkthrough/), [snowscan](https://snowscan.io/htb-writeup-traverxec/) |
| 57 | Postman | Linux | Redis Unauthenticated, SSH Key Write, Webmin RCE | Write SSH key via Redis, crack encrypted key for user, Webmin CVE-2019-12840 authenticated RCE for root | [0xdf](https://0xdf.gitlab.io/2020/03/14/htb-postman.html), [HackingArticles](https://www.hackingarticles.in/hack-the-box-postman-walkthrough/), [snowscan](https://snowscan.io/htb-writeup-postman/), [Medium](https://medium.com/@v1per/postman-hackthebox-writeup-5d31df5bf6d9), [ivanitlearning](https://ivanitlearning.wordpress.com/2020/09/20/hackthebox-postman/) |
| 58 | Mango | Linux | NoSQL Injection, SSH Credential Reuse, jjs SUID | NoSQL regex injection to dump creds, SSH lateral movement, Java jjs SUID for root | [0xdf](https://0xdf.gitlab.io/2020/04/18/htb-mango.html) |
| 59 | Json | Windows | .NET JSON Deserialization, JuicyPotato | Deserialize JSON bearer token for RCE, JuicyPotato SeImpersonatePrivilege for SYSTEM | [0xdf](https://0xdf.gitlab.io/2020/02/15/htb-json.html) |
| 60 | Ellingson | Linux | Werkzeug Debug Console, Hashcat Binary, ROP Binary Exploit | Access Werkzeug debug console, dump shadow hashes from custom binary, ROP exploit SUID binary for root | [0xdf](https://0xdf.gitlab.io/2019/10/19/htb-ellingson.html) |
| 61 | Haystack | Linux | ELK Stack, Elasticsearch Credential Dump, Kibana LFI/RCE | Search Elasticsearch for base64 creds, exploit Kibana CVE-2018-17246 for shell, Logstash pipeline for root | [0xdf](https://0xdf.gitlab.io/2019/11/02/htb-haystack.html) |
| 62 | Jarvis | Linux | SQLi (PHPMyAdmin), Systemctl SUID | SQLi in hotel booking for PHPMyAdmin access, OS shell via PHPMyAdmin, systemctl SUID for root | [0xdf](https://0xdf.gitlab.io/2019/11/09/htb-jarvis.html) |
| 63 | Networked | Linux | PHP Upload Bypass, Command Injection in Filename, Network Script Abuse | Bypass upload filter with double extension, command injection via filename, writable network-scripts for root | [0xdf](https://0xdf.gitlab.io/2019/11/16/htb-networked.html), [HackingArticles](https://www.hackingarticles.in/hack-the-box-networked-walkthrough/), [rana-khalil](https://rana-khalil.gitbook.io/hack-the-box-oscp-preparation/linux-boxes/networked-writeup-w-o-metasploit), [0xRick](https://0xrick.github.io/hack-the-box/networked/), [snowscan](https://snowscan.io/htb-writeup-networked/) |
| 64 | SwagShop | Linux | Magento Exploit Chain, vi sudo | Magento CVE-2015-1397 SQLi for admin, Magento Froghopper RCE, sudo vi escape for root | [0xdf](https://0xdf.gitlab.io/2019/09/28/htb-swagshop.html), [HackingArticles](https://www.hackingarticles.in/swagshop-hackthebox-walkthrough/), [rana-khalil](https://rana-khalil.gitbook.io/hack-the-box-oscp-preparation/linux-boxes/swagshop-writeup-w-o-metasploit), [0xRick](https://0xrick.github.io/hack-the-box/swagshop/), [snowscan](https://snowscan.io/htb-writeup-swagshop/) |
| 65 | FriendZone | Linux | DNS Zone Transfer, SMB Share Upload, Python Library Hijack | DNS zone transfer for subdomains, upload webshell via SMB, writable os.py for root cron | [0xdf](https://0xdf.gitlab.io/2019/07/13/htb-friendzone.html), [HackingArticles](https://www.hackingarticles.in/hack-the-box-friendzone-walkthrough/), [rana-khalil](https://rana-khalil.gitbook.io/hack-the-box-oscp-preparation/linux-boxes/friendzone-writeup-w-o-metasploit), [0xRick](https://0xrick.github.io/hack-the-box/friendzone/), [snowscan](https://snowscan.io/htb-writeup-friendzone/) |
| 66 | Irked | Linux | UnrealIRCd Backdoor, Steganography, Custom SUID Binary | Exploit UnrealIRCd 3.2.8.1 backdoor, extract steghide password, analyze SUID binary for root | [0xdf](https://0xdf.gitlab.io/2019/04/27/htb-irked.html), [HackingArticles](https://www.hackingarticles.in/hack-the-box-irked-walkthrough/), [rana-khalil](https://rana-khalil.gitbook.io/hack-the-box-oscp-preparation/linux-boxes/irked-writeup-w-o-metasploit), [IppSec](https://www.youtube.com/watch?v=OGFTM_qvtVI), [0xRick](https://0xrick.github.io/hack-the-box/irked/), [snowscan](https://snowscan.io/htb-writeup-irked/) |
| 67 | SecNotes | Windows | CSRF to Change Password, SMB Write, WSL | CSRF in contact form to change admin password, SMB share write for webshell, WSL bash.exe for root | [0xdf](https://0xdf.gitlab.io/2019/01/19/htb-secnotes.html) |
| 68 | Access | Windows | MDB File, Encrypted ZIP, Stored Credentials (runas) | FTP to get MDB/ZIP, extract PST for creds, runas /savecred for Administrator | [0xdf](https://0xdf.gitlab.io/2019/03/02/htb-access.html) |
| 69 | Jerry | Windows | Apache Tomcat Default Credentials, WAR Deploy | Default Tomcat manager credentials, deploy WAR reverse shell, already SYSTEM | [0xdf](https://0xdf.gitlab.io/2018/11/17/htb-jerry.html), [HackingArticles](https://www.hackingarticles.in/hack-the-box-jerry-walkthrough/), [rana-khalil](https://rana-khalil.gitbook.io/hack-the-box-oscp-preparation/windows-boxes/jerry-writeup-w-o-metasploit), [IppSec](https://www.youtube.com/watch?v=PJeBIey8gc4), [0xRick](https://0xrick.github.io/hack-the-box/jerry/), [Medium](https://medium.com/ctf-writeups/hack-the-box-jerry-write-up-6f045601315f) |
| 70 | TartarSauce | Linux | WordPress Plugin RFI, tar Wildcard Injection, systemd Timer | RFI via WordPress Gwolle plugin, pivot via tar checkpoint injection, abuse systemd timer for root | [0xdf](https://0xdf.gitlab.io/2018/10/20/htb-tartarsauce.html) |
| 71 | Sunday | Solaris | Finger Enumeration, SHA256 Hash Cracking, wget sudo | Enumerate users via finger, brute-force SSH, crack shadow hash, sudo wget to overwrite shadow | [0xdf](https://0xdf.gitlab.io/2018/09/29/htb-sunday.html) |
| 72 | Hawk | Linux | FTP Anon with Encrypted File, OpenSSL Decrypt, Drupal RCE, H2 Database | Decrypt FTP file for Drupal creds, Drupal PHP execution, H2 database console for root | [0xdf](https://0xdf.gitlab.io/2018/11/30/htb-hawk.html) |
| 73 | Poison | FreeBSD | LFI, Log Poisoning, VNC Credential Decrypt, SSH Tunnel | LFI to read phpinfo/logs, log poisoning for shell, decrypt VNC secret, tunnel VNC for root desktop | [0xdf](https://0xdf.gitlab.io/2018/09/08/htb-poison.html) |
| 74 | Chatterbox | Windows | AChat Buffer Overflow, Acl.exe Credential Reuse, PowerShell | Exploit AChat 0.150 BOF for shell, enumerate admin password reuse, icacls/PowerShell for root.txt | [0xdf](https://0xdf.gitlab.io/2018/06/18/htb-chatterbox.html) |
| 75 | Node | Linux | API User Enumeration, MongoDB Backup Download, Kernel Exploit | API leaks user hashes, download encrypted backup, crack and SSH, kernel exploit (CVE-2017-16995) for root | [0xdf](https://0xdf.gitlab.io/2021/06/08/htb-node.html) |
| 76 | SolidState | Linux | Apache James 2.3.2 RCE, Cron Script Abuse | Exploit Apache James admin with default creds, read user email for SSH creds, writable cron script for root | [0xdf](https://0xdf.gitlab.io/2020/04/30/htb-solidstate.html) |
| 77 | Nineveh | Linux | Brute Force Login, PHPLiteAdmin, LFI + Chkrootkit | Hydra brute force, PHPLiteAdmin create PHP DB, LFI to include DB for shell, Chkrootkit CVE for root | [0xdf](https://0xdf.gitlab.io/2020/04/22/htb-nineveh.html) |
| 78 | Cronos | Linux | DNS Zone Transfer, SQL Injection, Cron Job Abuse | Zone transfer reveals subdomain, SQLi bypasses login, command injection, cron runs Laravel artisan as root | [0xdf](https://0xdf.gitlab.io/2020/04/14/htb-cronos.html), [HackingArticles](https://www.hackingarticles.in/hack-the-box-challenge-cronos-walkthrough/), [IppSec](https://www.youtube.com/watch?v=CYeVUmOar3I) |
| 79 | Delivery | Linux | osTicket + MatterMost, Email Verification Bypass, Hashcat Rules | Create ticket for email, verify MatterMost account, get internal creds, hashcat rule-based crack for root | [0xdf](https://0xdf.gitlab.io/2021/05/22/htb-delivery.html) |
| 80 | Monteverde | Windows | Azure AD Enum, Password Spraying, Azure AD Connect | Enumerate AD users, spray found credentials, exploit Azure AD Connect for admin password | [0xdf](https://0xdf.gitlab.io/2020/06/13/htb-monteverde.html), [IppSec](https://www.youtube.com/watch?v=HTJjPZvOtJ4) |
| 81 | Resolute | Windows | Anonymous LDAP, Password Spraying, DnsAdmins DLL Injection | LDAP anonymous reveals password in description, spray users, DnsAdmins group DLL injection for SYSTEM | [0xdf](https://0xdf.gitlab.io/2020/05/30/htb-resolute.html), [IppSec](https://www.youtube.com/watch?v=8KJebvmd1Fk), [Medium](https://medium.com/@josephalan17201972/hackthebox-resolute-write-up-58d6e081ab4e), [HackingArticles](https://www.hackingarticles.in/resolute-hackthebox-walkthrough/), [chr0x6eos](https://chr0x6eos.github.io/2020/05/30/htb-Resolute.html), [zweilosec](https://zweilosec.github.io/posts/resolute/) |
| 82 | Cascade | Windows | LDAP Base64 Encoded Creds, .NET Reversing, TempAdmin AD Object | LDAP attribute leaks encoded password, reverse .NET binary for crypto key, recover TempAdmin creds via AD tombstone | [0xdf](https://0xdf.gitlab.io/2020/07/25/htb-cascade.html), [IppSec](https://www.youtube.com/watch?v=mr-fsVLoQGw), [Medium](https://olivierkonate.medium.com/hackthebox-cascade-dff0349ac16c), [HackingArticles](https://www.hackingarticles.in/cascade-hackthebox-walkthrough/), [chr0x6eos](https://chr0x6eos.github.io/2020/07/25/htb-Cascade.html), [ivanitlearning](https://ivanitlearning.wordpress.com/2020/12/16/hackthebox-cascade/) |
| 83 | Book | Linux | SQL Truncation Attack, XSS-to-PDF SSRF, Logrotate Race Condition | SQL truncation to clone admin email, XSS in PDF generation to read files, logrotate CVE for root | [0xdf](https://0xdf.gitlab.io/2020/07/11/htb-book.html) |
| 84 | Traceback | Linux | Webshell Discovery, Lua sudo, SSH motd Abuse | Discover planted webshell from OSINT, sudo Lua for user pivot, writable SSH motd script for root | [0xdf](https://0xdf.gitlab.io/2020/08/15/htb-traceback.html), [HackingArticles](https://www.hackingarticles.in/traceback-hackthebox-walkthrough/), [snowscan](https://snowscan.io/htb-writeup-traceback/) |
| 85 | Unbalanced | Linux | Squid Proxy, XPath Injection, Pi-hole RCE | Enumerate via Squid proxy, XPath injection to extract creds, Pi-hole authenticated RCE for root | [0xdf](https://0xdf.gitlab.io/2020/12/05/htb-unbalanced.html) |
| 86 | OpenKeys | OpenBSD | OpenBSD Auth Bypass (CVE-2019-19521), Xlock skey | CVE-2019-19521 auth bypass via username trick, CVE-2019-19520 xlock S/Key, CVE-2019-19522 for root | [0xdf](https://0xdf.gitlab.io/2020/12/12/htb-openkeys.html) |
| 87 | Doctor | Linux | SSTI (Jinja2), Splunk Universal Forwarder RCE | SSTI via message posting, reverse shell, abuse Splunk Universal Forwarder for root RCE | [0xdf](https://0xdf.gitlab.io/2021/02/06/htb-doctor.html), [HackingArticles](https://www.hackingarticles.in/doctor-hackthebox-walkthrough/), [IppSec](https://www.youtube.com/watch?v=JcOR9krOPFY), [Medium](https://jdroberts96.medium.com/hackthebox-writeup-doctor-a07a5405b0f9), [chr0x6eos](https://chr0x6eos.github.io/2021/02/06/htb-Doctor.html) |
| 88 | Laser | Linux | Solr RCE, gRPC Exploitation, Feed Printer | Exploit Apache Solr, interact with gRPC service, abuse printer feed for root | [0xdf](https://0xdf.gitlab.io/2020/12/19/htb-laser.html) |
| 89 | Jewel | Linux | Gitweb, Ruby Deserialization (CVE-2020-8165), google-authenticator | Ruby on Rails deserialization via Gitweb source, bypass 2FA with recovered TOTP seed, gem sudo for root | [0xdf](https://0xdf.gitlab.io/2021/02/13/htb-jewel.html) |
| 90 | Passage | Linux | CuteNews RCE, USBCreator D-Bus Exploit | Exploit CuteNews avatar upload for RCE, SSH key reuse for lateral, USBCreator D-Bus arbitrary read for root | [0xdf](https://0xdf.gitlab.io/2021/03/06/htb-passage.html) |
| 91 | Compromised | Linux | Backdoor Discovery, LiteCart RCE, PAM Backdoor Analysis | Discover existing backdoor in LiteCart, MySQL UDF for shell, analyze PAM backdoor for root creds | [0xdf](https://0xdf.gitlab.io/2021/01/23/htb-compromised.html) |
| 92 | Ophiuchi | Linux | Java YAML Deserialization (SnakeYAML), wasm Reverse | SnakeYAML deserialization RCE, reverse WASM binary to understand sudo script, craft correct WASM for root | [0xdf](https://0xdf.gitlab.io/2021/07/03/htb-ophiuchi.html) |
| 93 | Tenet | Linux | PHP Deserialization, Race Condition in SSH Key Write | PHP object injection for RCE, race condition to inject SSH key during cron-based reset for root | [0xdf](https://0xdf.gitlab.io/2021/06/12/htb-tenet.html) |
| 94 | Knife | Linux | PHP 8.1 Backdoor (CVE-2021-41773), knife sudo | Exploit PHP backdoor via User-Agentt header, sudo knife exec for root | [0xdf](https://0xdf.gitlab.io/2021/08/28/htb-knife.html), [HackingArticles](https://www.hackingarticles.in/knife-hackthebox-walkthrough/), [IppSec](https://www.youtube.com/watch?v=93JnRTF5sQM), [Medium](https://joshuanatan.medium.com/htb-knife-7cf987fa7cac) |
| 95 | BountyHunter | Linux | XXE Injection, Python eval Exploitation | XXE in bounty submission to read files, discover Python script, exploit eval() via sudo for root | [0xdf](https://0xdf.gitlab.io/2021/11/20/htb-bountyhunter.html) |
| 96 | Trick | Linux | DNS Zone Transfer, SQLi, LFI, Fail2Ban Abuse | Zone transfer for subdomains, SQLi for creds, LFI to discover services, Fail2Ban action injection for root | [0xdf](https://0xdf.gitlab.io/2022/10/29/htb-trick.html), [IppSec](https://www.youtube.com/watch?v=i5NHOdCKYEY) |
| 97 | Noter | Linux | Flask Cookie Forgery, MySQL UDF RCE | Forge Flask session cookie, access note with MySQL creds, MySQL raptor UDF for root | [0xdf](https://0xdf.gitlab.io/2022/09/03/htb-noter.html) |
| 98 | Faculty | Linux | SQLi, mPDF LFI, meta-git RCE | SQLi to bypass login, mPDF attachment:// to read passwd, meta-git command injection, gdb cap for root | [0xdf](https://0xdf.gitlab.io/2022/10/22/htb-faculty.html) |
| 99 | Shared | Linux | SQL Injection via Cookie, Redis/CVE-2022-0543, ipython Startup | SQLi in checkout cookie, exploit Redis Lua sandbox escape, writable ipython startup dir for root | [0xdf](https://0xdf.gitlab.io/2022/11/12/htb-shared.html) |
| 100 | Shoppy | Linux | NoSQL Auth Bypass, Mattermost Cred Disclosure, Docker Group | NoSQL injection for admin, Mattermost creds, SSH, Docker group for root | [0xdf](https://0xdf.gitlab.io/2023/01/14/htb-shoppy.html), [IppSec](https://www.youtube.com/watch?v=G_d-SiSoKdg) |
| 101 | Health | Linux | SSRF, Gogs Exploitation, Cron Abuse | SSRF via health check webhook redirect, access internal Gogs, forge admin token, cron DB query for root | [0xdf](https://0xdf.gitlab.io/2023/01/07/htb-health.html) |
| 102 | Ambassador | Linux | Grafana LFI (CVE-2021-43798), Consul RCE | Grafana directory traversal for SQLite DB with creds, Consul service registration for RCE as root | [0xdf](https://0xdf.gitlab.io/2023/01/28/htb-ambassador.html) |
| 103 | MetaTwo | Linux | WordPress CVE-2022-0739, XXE via Media Upload, Passpie GPG Crack | BookingPress SQLi, WordPress XXE via iDOCX upload for creds, crack Passpie GPG key for root | [0xdf](https://0xdf.gitlab.io/2023/04/29/htb-metatwo.html) |
| 104 | Precious | Linux | pdfkit Command Injection, Ruby Bundler sudo | pdfkit CVE-2022-25765 for shell, discover yaml creds, sudo bundle exec with crafted Gemfile for root | [0xdf](https://0xdf.gitlab.io/2023/05/20/htb-precious.html), [IppSec](https://www.youtube.com/watch?v=jVjGCOqg3WU) |
| 105 | Busqueda | Linux | Python eval Injection, Gitea Secrets, Docker Inspect | Searchor eval injection for RCE, discover Gitea from git config, Docker inspect reveals root creds | [0xdf](https://0xdf.gitlab.io/2023/08/12/htb-busqueda.html), [IppSec](https://www.youtube.com/watch?v=5dHgfviJWmg), [Medium](https://medium.com/@onurinalkac/hackthebox-21-busqueda-writeup-dd4cf53b2d58) |
| 106 | Pilgrimage | Linux | ImageMagick CVE-2022-44268 (Arbitrary File Read), Binwalk RCE | ImageMagick info leak to read SQLite DB for creds, Binwalk CVE-2022-4510 crafted PFS for root | [0xdf](https://0xdf.gitlab.io/2023/11/25/htb-pilgrimage.html), [IppSec](https://www.youtube.com/watch?v=Bnm2K9xUX0o), [Medium](https://datafarm-cybersecurity.medium.com/pilgrimage-write-up-hack-the-box-fc6ace08a445) |
| 107 | Topology | Linux | LaTeX Injection, gnuplot Exploitation | LaTeX injection to read files via equation generator, writable gnuplot config for root via cron | [0xdf](https://0xdf.gitlab.io/2023/11/04/htb-topology.html), [IppSec](https://www.youtube.com/watch?v=LqkA0UnNjGM), [Medium](https://medium.com/@josephalan17201972/topology-hack-the-box-write-up-b7a0f2ae5531) |
| 108 | Keeper | Linux | Request Tracker Default Creds, KeePass CVE-2023-32784 | RT default creds, discover KeePass dump, extract master password from memory dump, get PuTTY key for root | [0xdf](https://0xdf.gitlab.io/2024/02/10/htb-keeper.html), [IppSec](https://www.youtube.com/watch?v=0AafRQIaWmQ), [Medium](https://medium.com/@li_allouche/hack-the-box-keeper-writeup-56644dc6a55f), [erichogue](https://erichogue.ca/2024/02/HTB/Keeper) |
| 109 | CozyHosting | Linux | Spring Boot Actuator Session Leak, Command Injection, PostgreSQL | Steal session via Actuator endpoint, command injection in SSH hostname, PostgreSQL hash crack, sudo ssh for root | [0xdf](https://0xdf.gitlab.io/2024/03/02/htb-cozyhosting.html), [IppSec](https://www.youtube.com/watch?v=okTl6kWrncg), [Medium](https://medium.com/@johnniketas/hackthebox-cozyhosting-c6e5272e7090) |
| 110 | Devvortex | Linux | Joomla CVE-2023-23752 Info Leak, MySQL Credential Dump, Apport-CLI | Joomla API info disclosure for admin creds, MySQL for bcrypt hash, Apport CLI pager escape for root | [0xdf](https://0xdf.gitlab.io/2024/04/27/htb-devvortex.html), [IppSec](https://www.youtube.com/watch?v=jdWOXokQQK0), [Medium](https://rianfriedt.medium.com/devvortex-writeup-hack-the-box-rian-friedt-a46ae2ab7886) |
| 111 | Surveillance | Linux | Craft CMS CVE-2023-41892 RCE, ZoneMinder SQLi/RCE | Craft CMS unauthenticated RCE, discover internal ZoneMinder, SQLi for creds, ZoneMinder RCE for root | [0xdf](https://0xdf.gitlab.io/2024/04/20/htb-surveillance.html) |
| 112 | Skyfall | Linux | MinIO CVE-2023-28432 Info Leak, Vault OTP, Vault SSH-CA | MinIO info disclosure for Vault creds, Vault OTP for SSH, Vault SSH-CA abuse for root | [0xdf](https://0xdf.gitlab.io/2024/08/31/htb-skyfall.html) |

---

## Machines by OS

### Linux (85+)

Cronos, Nineveh, SolidState, Node, Poison (FreeBSD), Hawk, TartarSauce, Irked, FriendZone, SwagShop, Networked, Jarvis, Haystack, Ellingson, Mango, Postman, Traverxec, OpenAdmin, Admirer, Magic, Cache, Blunder, Tabby, Academy, Time, Delivery, ScriptKiddie, Armageddon, Horizontall, Forge, Pandora, Paper, Nunchucks, Backdoor, Shibboleth, Timing, RedPanda, Photobomb, Bagel, Sandworm, Jupiter, Drive, Clicker, Perfection, Headless, IClean, GreenHorn, PermX, Sea, Sightless, Alert, Instant, Boardlight, Editorial, Snapped, Browsed, Previous, TombWatcher, Voleur, Signed, Cap, Previse, Seal, Dynstr, Book, Traceback, Doctor, Passage, Compromised, Ophiuchi, Tenet, Knife, BountyHunter, Trick, Noter, Faculty, Shared, Shoppy, Health, Ambassador, MetaTwo, Precious, Busqueda, Pilgrimage, Topology, Keeper, CozyHosting, Devvortex, Surveillance, Skyfall, Pit, Unbalanced, Jewel

### Windows (15+)

Chatterbox, Jerry, Access, SecNotes, Json, Love, Worker, Buff, Mailing, Crafty, Cicada, Monteverde, Resolute, Cascade

### Solaris/Other (2+)

Sunday (Solaris), OpenKeys (OpenBSD), Poison (FreeBSD), Spectra (ChromeOS)

---

## Machines by Technique Category

### Web Exploitation

| Machine | Specific Technique |
|---------|--------------------|
| Cronos | SQL Injection, Command Injection |
| Nineveh | PHPLiteAdmin, LFI |
| SwagShop | Magento Exploit Chain |
| Jarvis | PHPMyAdmin SQLi |
| Horizontall | Strapi CMS RCE |
| Forge | SSRF to Internal Services |
| IClean | XSS + SSTI Chain |
| Sea | WonderCMS XSS-to-RCE |
| PermX | Chamilo LMS RCE |
| Headless | Blind XSS + Command Injection |
| Editorial | SSRF + Git Secrets |
| Busqueda | Python eval Injection |
| CozyHosting | Spring Boot Actuator Leak |
| Devvortex | Joomla API Info Disclosure |

### Active Directory / Windows Domain

| Machine | Specific Technique |
|---------|--------------------|
| Monteverde | Azure AD Connect |
| Resolute | DnsAdmins DLL Injection |
| Cascade | LDAP Attribute Leak, AD Tombstone |
| Cicada | SMB Enumeration, SeBackupPrivilege |

### Deserialization

| Machine | Specific Technique |
|---------|--------------------|
| Json | .NET JSON Deserialization |
| Time | Jackson Java Deserialization |
| Bagel | .NET JSON Deserialization |
| RedPanda | SSTI + XXE via Metadata |
| Ophiuchi | SnakeYAML Deserialization |
| Tenet | PHP Object Deserialization |

### Template Injection (SSTI)

| Machine | Specific Technique |
|---------|--------------------|
| Sandworm | SSTI in PGP Verification (Jinja2) |
| RedPanda | SSTI in Spring Boot (Thymeleaf) |
| IClean | SSTI in Invoice Generator |
| Perfection | ERB SSTI via Newline Bypass |
| Doctor | Jinja2 SSTI |
| Nunchucks | Nunjucks SSTI |

### LFI / File Read

| Machine | Specific Technique |
|---------|--------------------|
| Nineveh | LFI + Chkrootkit |
| Poison | LFI + Log Poisoning |
| Backdoor | LFI via WordPress Plugin + /proc Read |
| Timing | PHP Filter Chain LFI |
| Tabby | LFI to Read Tomcat Creds |
| Pilgrimage | ImageMagick Arbitrary File Read |

### Binary Exploitation / Custom Protocols

| Machine | Specific Technique |
|---------|--------------------|
| Ellingson | Custom SUID ROP Exploit |
| Chatterbox | AChat Buffer Overflow |
| Buff | CloudMe Stack Buffer Overflow |
| Node | Kernel Exploit CVE-2017-16995 |

### Container / Virtualization Escape

| Machine | Specific Technique |
|---------|--------------------|
| Tabby | LXD Group Container Mount |
| Cache | Docker Group Escape |
| Shoppy | Docker Group Escape |
| Sightless | Container Escape |

---

## Writeup References

For each machine, recommended external writeup sources:

- **0xdf** - [0xdf.gitlab.io](https://0xdf.gitlab.io) - Extremely detailed, gold standard
- **IppSec** - [youtube.com/ippsec](https://youtube.com/ippsec) - Video walkthroughs for every retired machine
- **HackingArticles** - [hackingarticles.in](https://www.hackingarticles.in/) - Raj Chandel, extensive classic machine coverage
- **Rana Khalil** - [rana-khalil.gitbook.io](https://rana-khalil.gitbook.io/hack-the-box-oscp-preparation/) - OSCP-focused, no Metasploit
- **snowscan** - [snowscan.io](https://snowscan.io/) - Detailed writeups, consistent quality
- **0xRick** - [0xrick.github.io](https://0xrick.github.io/categories/hack-the-box/) - Clean blog writeups
- **HackTricks** - [book.hacktricks.xyz](https://book.hacktricks.xyz) - Technique reference
- **HTB Official** - [app.hackthebox.com](https://app.hackthebox.com) - Official writeups (VIP)

---

## OSCP-Like Medium Machines (Prioritized)

These machines most closely simulate OSCP exam conditions (no Metasploit, manual exploitation):

| Priority | Machine | Why |
|----------|---------|-----|
| 1 | Cronos | DNS + SQLi + Cron - classic OSCP chain, [HackingArticles](https://www.hackingarticles.in/hack-the-box-challenge-cronos-walkthrough/), [IppSec](https://www.youtube.com/watch?v=CYeVUmOar3I) |
| 2 | SolidState | Service exploit + cron privesc |
| 3 | Poison | LFI + log poisoning fundamentals |
| 4 | Jerry | Tomcat basics - quick win practice, [HackingArticles](https://www.hackingarticles.in/hack-the-box-jerry-walkthrough/), [rana-khalil](https://rana-khalil.gitbook.io/hack-the-box-oscp-preparation/windows-boxes/jerry-writeup-w-o-metasploit), [IppSec](https://www.youtube.com/watch?v=PJeBIey8gc4), [0xRick](https://0xrick.github.io/hack-the-box/jerry/), [Medium](https://medium.com/ctf-writeups/hack-the-box-jerry-write-up-6f045601315f) |
| 5 | Tabby | LFI + WAR deploy + container privesc, [HackingArticles](https://www.hackingarticles.in/tabby-hackthebox-walkthrough/), [rana-khalil](https://rana-khalil.gitbook.io/hack-the-box-oscp-preparation/linux-boxes/tabby-writeup-w-o-metasploit), [snowscan](https://snowscan.io/htb-writeup-tabby/) |
| 6 | Previse | EAR + command injection + PATH hijack, [IppSec](https://www.youtube.com/watch?v=bFqb0n68M8Q) |
| 7 | Cap | IDOR + capabilities privesc, [HackingArticles](https://www.hackingarticles.in/cap-hackthebox-walkthrough/), [IppSec](https://www.youtube.com/watch?v=O_z6o2xuvlw), [Medium](https://medium.com/@ruruuu/hackthebox-cap-writeup-95e2d8ca64c2) |
| 8 | Photobomb | Auth bypass + command injection + PATH hijack, [IppSec](https://www.youtube.com/watch?v=wE5j2WLuMQI) |
| 9 | OpenAdmin | Known CVE + SSH key + sudo escape, [HackingArticles](https://www.hackingarticles.in/hack-the-box-open-admin-box-walkthrough/), [snowscan](https://snowscan.io/htb-writeup-openadmin/), [Medium](https://musyokaian.medium.com/openadmin-walkthrough-hackthebox-8ab40e4072a5), [chr0x6eos](https://chr0x6eos.github.io/2020/05/02/htb-OpenAdmin.html), [ivanitlearning](https://ivanitlearning.wordpress.com/2020/09/24/hackthebox-openadmin/) |
| 10 | Magic | SQLi + upload filter bypass + SUID abuse |
