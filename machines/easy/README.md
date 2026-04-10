---
layout: default
title: Easy Machines
parent: Machines
nav_order: 1
description: "120+ Easy HTB machine writeups with walkthroughs"
permalink: /machines/easy/
---

# HackTheBox Easy Machines - Comprehensive Reference

> Complete catalog of retired HTB Easy machines with OS, key vulnerability, attack path summary, and quality writeup links.

**Total: 100+ Easy Machines** | Updated: April 2026

---

## Quick Navigation

- [Classic / Legacy Machines (2017-2019)](#classic--legacy-machines-2017-2019)
- [2019-2020 Machines](#2019-2020-machines)
- [2021 Machines](#2021-machines)
- [2022 Machines](#2022-machines)
- [2023 Machines](#2023-machines)
- [2024 Machines (Season 4 & 5)](#2024-machines-season-4--5)
- [2025-2026 Machines (Season 6+)](#2025-2026-machines-season-6)

---

## Classic / Legacy Machines (2017-2019)

| # | Machine | OS | Key Vulnerability / Technique | Attack Path Summary | Writeup |
|---|---------|-----|-------------------------------|---------------------|---------|
| 1 | **Lame** | Linux | Samba 3.0.20 RCE (CVE-2007-2447) | Exploit Samba `username map script` command injection to get root shell directly | [0xdf](https://0xdf.gitlab.io/2020/04/07/htb-lame.html) |
| 2 | **Legacy** | Windows | MS08-067 (NetAPI) | Exploit SMB vulnerability in Windows XP for SYSTEM shell | [0xdf](https://0xdf.gitlab.io/2019/02/09/htb-legacy.html) |
| 3 | **Blue** | Windows | MS17-010 EternalBlue | Exploit SMB EternalBlue vulnerability for SYSTEM shell on Windows 7 | [0xdf](https://0xdf.gitlab.io/2021/05/11/htb-blue.html) |
| 4 | **Devel** | Windows | FTP Anonymous Upload + IIS RCE | Upload ASPX webshell via anonymous FTP to IIS webroot, kernel exploit for SYSTEM | [0xdf](https://0xdf.gitlab.io/2019/03/05/htb-devel.html) |
| 5 | **Beep** | Linux | Elastix LFI / Multiple Vectors | Multiple attack paths: LFI to read credentials, Shellshock, or RCE via FreePBX | [0xdf](https://0xdf.gitlab.io/2021/02/23/htb-beep.html) |
| 6 | **Optimum** | Windows | HFS 2.3 RCE (CVE-2014-6287) | Exploit HttpFileServer RCE for user shell, MS16-032 for SYSTEM | [0xdf](https://0xdf.gitlab.io/2021/03/17/htb-optimum.html) |
| 7 | **Bastard** | Windows | Drupal 7 RCE (Drupalgeddon) | Exploit Drupal RCE for webshell, kernel exploit (MS15-051) for SYSTEM | [0xdf](https://0xdf.gitlab.io/2019/03/12/htb-bastard.html) |
| 8 | **Grandpa** | Windows | IIS 6.0 WebDAV RCE (CVE-2017-7269) | Exploit IIS WebDAV buffer overflow, token impersonation (churrasco) for SYSTEM | [0xdf](https://0xdf.gitlab.io/2019/03/06/htb-grandpa.html) |
| 9 | **Granny** | Windows | IIS 6.0 WebDAV PUT Upload | Upload webshell via WebDAV PUT method, token impersonation for SYSTEM | [0xdf](https://0xdf.gitlab.io/2019/03/06/htb-granny.html) |
| 10 | **Arctic** | Windows | Adobe ColdFusion 8 RCE | Exploit ColdFusion directory traversal + RCE, kernel exploit for SYSTEM | [0xdf](https://0xdf.gitlab.io/2020/05/19/htb-arctic.html) |
| 11 | **Shocker** | Linux | Shellshock (CVE-2014-6271) | Exploit Shellshock in CGI script for user shell, sudo perl for root | [0xdf](https://0xdf.gitlab.io/2021/05/25/htb-shocker.html) |
| 12 | **Nibbles** | Linux | NibbleBlog Arbitrary File Upload | Guess admin credentials on NibbleBlog, upload PHP shell via My Image plugin, sudo for root | [0xdf](https://0xdf.gitlab.io/2018/06/30/htb-nibbles.html) |
| 13 | **Bashed** | Linux | PHP Webshell + Cron Abuse | Find phpbash webshell on dev server, pivot to scriptmanager, cron job runs Python as root | [0xdf](https://0xdf.gitlab.io/2018/04/29/htb-bashed.html) |
| 14 | **Mirai** | Linux | Default Raspberry Pi Credentials | Access Pi-hole admin panel, SSH with default pi:raspberry credentials, recover root flag from USB | [0xdf](https://0xdf.gitlab.io/2021/05/18/htb-mirai.html) |
| 15 | **Sense** | FreeBSD | pfSense RCE (CVE-2014-4688) | Find credentials via directory brute-force, exploit pfSense command injection for root | [0xdf](https://0xdf.gitlab.io/2021/03/08/htb-sense.html) |
| 16 | **Blocky** | Linux | WordPress + Exposed Java Creds | Decompile Minecraft plugin JAR to find DB creds, password reuse for SSH, sudo su for root | [0xdf](https://0xdf.gitlab.io/2021/06/20/htb-blocky.html) |
| 17 | **Cronos** | Linux | DNS Zone Transfer + SQLi + Cron | Zone transfer reveals admin subdomain, SQLi bypass login, command injection, cron privesc | [rana-khalil](https://rana-khalil.gitbook.io/hack-the-box-oscp-preparation/linux-boxes/cronos-writeup-w-o-metasploit) |
| 18 | **Bank** | Linux | File Upload Bypass + SUID | Upload PHP reverse shell (bypass extension filter), find SUID binary for root | [0xdf](https://0xdf.gitlab.io/2021/06/14/htb-bank.html) |
| 19 | **Sunday** | Solaris | Finger Enumeration + Shadow File | Enumerate users via finger service, brute-force SSH, read shadow file, crack root hash | [0xdf](https://0xdf.gitlab.io/2018/09/29/htb-sunday.html) |
| 20 | **Valentine** | Linux | Heartbleed (CVE-2014-0160) | Exploit Heartbleed to leak SSH key passphrase from memory, tmux session hijack for root | [0xdf](https://0xdf.gitlab.io/2018/07/28/htb-valentine.html) |
| 21 | **Irked** | Linux | UnrealIRCd Backdoor + Stego | Exploit UnrealIRCd 3.2.8.1 backdoor for shell, extract password from steganography image for root | [0xdf](https://0xdf.gitlab.io/2019/04/27/htb-irked.html) |
| 22 | **Netmon** | Windows | FTP Anonymous + PRTG RCE | Access FTP to find PRTG config with credentials, exploit PRTG Network Monitor for SYSTEM | [0xdf](https://0xdf.gitlab.io/2019/06/29/htb-netmon.html) |
| 23 | **Jerry** | Windows | Apache Tomcat Default Creds | Login to Tomcat manager with default credentials, deploy WAR file reverse shell for SYSTEM | [0xdf](https://0xdf.gitlab.io/2018/11/17/htb-jerry.html) |
| 24 | **Active** | Windows | GPP Password + Kerberoasting | Decrypt Group Policy Preferences password from SMB, Kerberoast Administrator SPN | [0xdf](https://0xdf.gitlab.io/2018/12/08/htb-active.html) |
| 25 | **Access** | Windows | MDB Credentials + Stored Creds | Extract creds from Access DB on FTP, decrypt PST for password, runas with stored credentials | [0xdf](https://0xdf.gitlab.io/2019/03/02/htb-access.html) |
| 26 | **Bounty** | Windows | IIS Short Name + web.config Upload | Exploit IIS short filename disclosure, upload web.config with ASP code, JuicyPotato for SYSTEM | [0xdf](https://0xdf.gitlab.io/2018/10/27/htb-bounty.html) |
| 27 | **Curling** | Linux | Joomla + Hex Decode + Cron | Find base64 password in page source for Joomla admin, edit template for shell, cron privesc | [0xdf](https://0xdf.gitlab.io/2019/05/18/htb-curling.html) |
| 28 | **FriendZone** | Linux | DNS Zone Transfer + LFI + Cron | Zone transfer reveals vhosts, find creds in SMB, LFI to RCE via uploaded PHP, writable cron module for root | [0xdf](https://0xdf.gitlab.io/2019/10/05/htb-friendzone.html) |
| 29 | **SwagShop** | Linux | Magento RCE (CVE-2015-1397) | Create admin via SQLi, exploit Magento Froghopper RCE, sudo vi for root | [0xdf](https://0xdf.gitlab.io/2019/09/28/htb-swagshop.html) |
| 30 | **Bastion** | Windows | VHD Mount + SAM Dump | Access SMB backup share, mount VHD file, dump SAM hashes, crack mRemoteNG config for admin | [0xdf](https://0xdf.gitlab.io/2019/09/07/htb-bastion.html) |

---

## 2019-2020 Machines

| # | Machine | OS | Key Vulnerability / Technique | Attack Path Summary | Writeup |
|---|---------|-----|-------------------------------|---------------------|---------|
| 31 | **Networked** | Linux | PHP Upload + Command Injection | Upload PHP shell via image extension bypass, crontab script command injection for root | [0xdf](https://0xdf.gitlab.io/2019/11/16/htb-networked.html) |
| 32 | **Haystack** | Linux | ELK Stack + Kibana LFI | Find base64 creds in Elasticsearch, exploit Kibana LFI (CVE-2018-17246) for shell, logstash for root | [0xdf](https://0xdf.gitlab.io/2019/11/02/htb-haystack.html) |
| 33 | **Writeup** | Linux | CMS Made Simple SQLi + PATH Hijack | Exploit CMS Made Simple SQLi (CVE-2019-9053) for creds, SSH, PATH hijack via staff group for root | [0xdf](https://0xdf.gitlab.io/2019/10/12/htb-writeup.html) |
| 34 | **Luke** | Linux | JSON API + Multiple Creds | Enumerate FTP, discover Ajenti panel, chain API auth tokens to extract admin creds | [0xdf](https://0xdf.gitlab.io/2019/09/14/htb-luke.html) |
| 35 | **Postman** | Linux | Redis Unauthorized + Webmin RCE | Write SSH key via unauthenticated Redis, crack encrypted SSH key, Webmin RCE (CVE-2019-12840) as root | [0xdf](https://0xdf.gitlab.io/2020/03/14/htb-postman.html) |
| 36 | **Traverxec** | Linux | Nostromo RCE + Journalctl Privesc | Exploit Nostromo web server RCE (CVE-2019-16278) for shell, find SSH key in htdocs, sudo journalctl pager escape for root | [0xdf](https://0xdf.gitlab.io/2020/04/18/htb-traverxec.html) |
| 37 | **OpenAdmin** | Linux | OpenNetAdmin RCE + Sudo Nano | Exploit OpenNetAdmin RCE, pivot via password reuse, read SSH key via internal Apache, sudo nano for root | [0xdf](https://0xdf.gitlab.io/2020/05/02/htb-openadmin.html) |
| 38 | **Traceback** | Linux | PHP Webshell + Lua Privesc | Find existing webshell from previous attacker, pivot users via Lua binary (sudo luvit), motd write for root | [0xdf](https://0xdf.gitlab.io/2020/08/15/htb-traceback.html) |
| 39 | **Admirer** | Linux | Adminer 4.6.2 SSRF + PATH Hijack | Discover credentials via directory traversal, exploit Adminer SSRF to read config, PYTHONPATH hijack for root | [0xdf](https://0xdf.gitlab.io/2020/09/26/htb-admirer.html) |
| 40 | **Blunder** | Linux | Bludit CMS Brute-force + sudo Bypass | Generate wordlist from site via CeWL, bypass Bludit brute-force protection, upload PHP shell, CVE-2019-14287 sudo bypass for root | [0xdf](https://0xdf.gitlab.io/2020/10/17/htb-blunder.html) |
| 41 | **Tabby** | Linux | LFI + Tomcat WAR Deploy + LXD | LFI reads Tomcat credentials, deploy WAR shell, privesc via lxd group container escape for root | [0xdf](https://0xdf.gitlab.io/2020/11/07/htb-tabby.html) |
| 42 | **Doctor** | Linux | SSTI in Flask + Splunk Privesc | Server-Side Template Injection in Flask app for command execution, Splunk Universal Forwarder RCE for root | [0xdf](https://0xdf.gitlab.io/2021/02/06/htb-doctor.html) |
| 43 | **Academy** | Linux | Laravel Debug RCE + Audit Log | Register with admin role via parameter tampering, exploit Laravel debug mode RCE (CVE-2018-15133), read audit log for creds, sudo composer for root | [0xdf](https://0xdf.gitlab.io/2021/02/27/htb-academy.html) |
| 44 | **Laboratory** | Linux | GitLab SSRF + RCE + PATH Hijack | Exploit GitLab SSRF to file read (CVE-2020-10977), chain to RCE, SUID binary PATH injection for root | [0xdf](https://0xdf.gitlab.io/2021/04/17/htb-laboratory.html) |
| 45 | **Luanne** | NetBSD | Lua Injection + Backup Decrypt | Bozohttpd Lua injection for code exec, find encrypted backup with credentials, doas for root | [0xdf](https://0xdf.gitlab.io/2021/03/27/htb-luanne.html) |
| 46 | **Remote** | Windows | Umbraco RCE + TeamViewer Creds | Mount NFS share to get Umbraco DB, crack admin hash, Umbraco RCE, extract TeamViewer creds for admin | [0xdf](https://0xdf.gitlab.io/2020/09/05/htb-remote.html) |
| 47 | **Help** | Linux | HelpDeskZ SQLi + File Upload | Exploit HelpDeskZ file upload with time-based filename prediction, kernel exploit for root | [0xdf](https://0xdf.gitlab.io/2019/06/08/htb-help.html) |
| 48 | **LaCasaDePapel** | Linux | PHP Dompdf + Client Cert | Exploit Dali backdoor with CSRF, generate client certificate for HTTPS access, find SSH key via LFI, crontab for root | [0xdf](https://0xdf.gitlab.io/2019/07/27/htb-lacasadepapel.html) |

---

## 2021 Machines

| # | Machine | OS | Key Vulnerability / Technique | Attack Path Summary | Writeup |
|---|---------|-----|-------------------------------|---------------------|---------|
| 49 | **ScriptKiddie** | Linux | Msfvenom APK Template Injection | Exploit CVE-2020-7384 msfvenom APK template command injection, incidentresponse cron abuse for root | [0xdf](https://0xdf.gitlab.io/2021/06/05/htb-scriptkiddie.html) |
| 50 | **Spectra** | ChromeOS | WordPress + Autologon Creds | Find WordPress DB creds in testing config, reuse password for SSH, exploit initctl (auto-start service) for root | [0xdf](https://0xdf.gitlab.io/2021/06/26/htb-spectra.html) |
| 51 | **Armageddon** | Linux | Drupal RCE (Drupalgeddon2) | Exploit Drupal CVE-2018-7600 for webshell, find MySQL creds, crack hash, sudo snap install for root | [0xdf](https://0xdf.gitlab.io/2021/07/24/htb-armageddon.html) |
| 52 | **Knife** | Linux | PHP 8.1.0-dev Backdoor + Sudo Knife | Exploit PHP backdoor via User-Agentt header for RCE, sudo knife exec Ruby for root | [0xdf](https://0xdf.gitlab.io/2021/08/28/htb-knife.html) |
| 53 | **Cap** | Linux | IDOR + PCAP Credentials + Capabilities | IDOR vulnerability exposes PCAP with FTP creds, Python has cap_setuid capability for root | [0xdf](https://0xdf.gitlab.io/2021/10/02/htb-cap.html) |
| 54 | **Explore** | Android | ES File Explorer Arbitrary Read | Exploit ES File Explorer CVE-2019-6447 to read files, find credentials image, SSH for user, ADB root | [0xdf](https://0xdf.gitlab.io/2021/10/30/htb-explore.html) |
| 55 | **Love** | Windows | SSRF + AlwaysInstallElevated | SSRF via file scanner reads internal admin page with creds, exploit Voting System upload, AlwaysInstallElevated for SYSTEM | [0xdf](https://0xdf.gitlab.io/2021/08/07/htb-love.html) |
| 56 | **Previse** | Linux | OS Command Injection + PATH Hijack | Create account via request manipulation, find exec() command injection, crack MySQL hash, PATH hijack in SUID script for root | [0xdf](https://0xdf.gitlab.io/2022/01/08/htb-previse.html) |
| 57 | **Horizontall** | Linux | Strapi RCE Chain | Discover Strapi API via JS analysis, chain CVE-2019-18818 (password reset) + CVE-2019-19609 (RCE), Laravel debug RCE via port forward for root | [0xdf](https://0xdf.gitlab.io/2022/02/05/htb-horizontall.html) |
| 58 | **Validation** | Linux | SQL Injection to RCE + Docker Root | Second-order SQLi via country parameter writes PHP webshell, find config creds, su root (password reuse) | [0xdf](https://0xdf.gitlab.io/2022/02/12/htb-validation.html) |
| 59 | **Driver** | Windows | SCF File Attack + PrintNightmare | Upload SCF file to printer share capturing NTLM hash, crack hash for WinRM, PrintNightmare (CVE-2021-1675) for SYSTEM | [0xdf](https://0xdf.gitlab.io/2022/02/26/htb-driver.html) |
| 60 | **Return** | Windows | Printer LDAP Config + Server Operators | Redirect printer LDAP config to capture creds, WinRM access, abuse Server Operators group service control for SYSTEM | [0xdf](https://0xdf.gitlab.io/2022/03/12/htb-return.html) |
| 61 | **Antique** | Linux | SNMP String Leak + CUPS RCE | Extract printer password via SNMP OID walk, telnet access, CUPS (CVE-2012-5519) file read as root | [0xdf](https://0xdf.gitlab.io/2022/03/19/htb-antique.html) |
| 62 | **Backdoor** | Linux | WordPress Plugin LFI + Screen SUID | Exploit eBook Download plugin LFI, enumerate /proc to find gdbserver, exploit gdbserver for shell, SUID screen for root | [0xdf](https://0xdf.gitlab.io/2022/04/23/htb-backdoor.html) |
| 63 | **Nunchucks** | Linux | SSTI in Express.js + AppArmor Bypass | Discover subdomain with Nunjucks SSTI, exploit for shell, bypass AppArmor via Perl shebang bug for root | [0xdf](https://0xdf.gitlab.io/2022/05/07/htb-nunchucks.html) |
| 64 | **Paper** | Linux | WordPress Draft Leak + Rocket.Chat Bot | Exploit WordPress draft content disclosure, find Rocket.Chat registration URL, abuse bot file read, Polkit CVE-2021-3560 for root | [0xdf](https://0xdf.gitlab.io/2022/06/18/htb-paper.html) |
| 65 | **Timelapse** | Windows | PFX Cert Cracking + LAPS | Crack PFX from SMB share, extract cert/key for WinRM, read LAPS password from AD for Administrator | [0xdf](https://0xdf.gitlab.io/2022/08/20/htb-timelapse.html) |
| 66 | **Late** | Linux | SSTI via OCR + SUID Script | Upload image with SSTI payload to Flask-based OCR app, exploit Jinja2 SSTI for shell, write to SUID append script for root | [0xdf](https://0xdf.gitlab.io/2022/08/27/htb-late.html) |

---

## 2022 Machines

| # | Machine | OS | Key Vulnerability / Technique | Attack Path Summary | Writeup |
|---|---------|-----|-------------------------------|---------------------|---------|
| 67 | **Pandora** | Linux | SNMP Credential Leak + Pandora FMS RCE | Enumerate SNMP for cleartext creds, port-forward Pandora FMS, chain SQLi + RCE, SUID binary PATH hijack for root | [0xdf](https://0xdf.gitlab.io/2022/05/21/htb-pandora.html) |
| 68 | **GoodGames** | Linux | SQLi + SSTI + Docker Escape | SQL injection in login to dump admin hash, SSTI in Flask dashboard for shell in container, mount host filesystem for root | [0xdf](https://0xdf.gitlab.io/2022/06/11/htb-goodgames.html) |
| 69 | **NodeBlog** | Linux | NoSQL Injection + XXE + Deserialization | NoSQL injection to bypass login, XXE in blog XML parsing, node-serialize deserialization RCE, MongoDB creds for root | [0xdf](https://0xdf.gitlab.io/2022/05/30/htb-nodeblog.html) |
| 70 | **Trick** | Linux | DNS Enumeration + SQLi + LFI to RCE | DNS zone transfer reveals subdomains, SQLi in payroll app for file read, find vhost with LFI, include mail with PHP code for RCE, fail2ban privesc | [0xdf](https://0xdf.gitlab.io/2022/10/22/htb-trick.html) |
| 71 | **RedPanda** | Linux | Spring Boot SSTI + XXE Cron | SSTI in Java Spring Boot search for shell, exploit XXE in log parser cron job to read root SSH key | [0xdf](https://0xdf.gitlab.io/2022/11/19/htb-redpanda.html) |
| 72 | **Shoppy** | Linux | NoSQL Injection + Docker Group | NoSQL injection in login and search, crack user hash from Mattermost, docker group container escape for root | [0xdf](https://0xdf.gitlab.io/2023/01/14/htb-shoppy.html) |
| 73 | **Photobomb** | Linux | Exposed Creds + Command Injection + PATH | Find credentials in JavaScript file, command injection in image manipulation, sudo script with relative PATH for root | [0xdf](https://0xdf.gitlab.io/2023/02/11/htb-photobomb.html) |
| 74 | **Precious** | Linux | pdfkit RCE + Ruby Deserialization | Exploit pdfkit CVE-2022-25765 command injection for shell, find creds in .bundle config, insecure Ruby YAML deserialization for root | [0xdf](https://0xdf.gitlab.io/2023/05/27/htb-precious.html) |
| 75 | **MetaTwo** | Linux | WordPress BookingPress SQLi + XXE | SQLi in WordPress BookingPress plugin (CVE-2022-0739), XXE in WordPress media upload (CVE-2021-29447), crack Passpie PGP for root | [0xdf](https://0xdf.gitlab.io/2023/04/22/htb-metatwo.html) |
| 76 | **Squashed** | Linux | NFS no_root_squash + X11 Screenshot | Mount NFS share, fake UID to write webshell for user, .Xauthority token to screenshot X11 for root password | [0xdf](https://0xdf.gitlab.io/2023/04/01/htb-squashed.html) |
| 77 | **Stocker** | Linux | NoSQL Injection + PDF HTML Injection | NoSQL injection to bypass Express.js login, HTML injection in PDF generator reads files via iframe, path wildcard sudo for root | [0xdf](https://0xdf.gitlab.io/2023/06/17/htb-stocker.html) |
| 78 | **Soccer** | Linux | Default Creds + WebSocket SQLi + doas | Upload webshell via Tiny File Manager default creds, blind SQLi over WebSocket, doas privesc for root | [0xdf](https://0xdf.gitlab.io/2023/06/10/htb-soccer.html) |
| 79 | **Support** | Windows | LDAP + .NET Binary Analysis | Analyze .NET binary to extract LDAP creds, enumerate AD users/shares, abuse GenericAll on DC for Kerberos RBCD attack | [0xdf](https://0xdf.gitlab.io/2022/12/17/htb-support.html) |

---

## 2023 Machines

| # | Machine | OS | Key Vulnerability / Technique | Attack Path Summary | Writeup |
|---|---------|-----|-------------------------------|---------------------|---------|
| 80 | **PC** | Linux | gRPC Enumeration + SQLi + pyLoad RCE | Enumerate gRPC service, SQL injection in app, find creds, exploit pyLoad (CVE-2023-0297) for root | [0xdf](https://0xdf.gitlab.io/2023/09/16/htb-pc.html) |
| 81 | **Busqueda** | Linux | Searchor Code Injection + Git Creds | Exploit eval() code injection in Searchor Python library, find creds in .git config, relative PATH sudo abuse for root | [0xdf](https://0xdf.gitlab.io/2023/08/12/htb-busqueda.html) |
| 82 | **Pilgrimage** | Linux | ImageMagick LFI + Binwalk RCE | Exploit ImageMagick (CVE-2022-44268) to read files, extract SQLite DB creds, Binwalk CVE-2022-4510 RCE for root | [0xdf](https://0xdf.gitlab.io/2023/11/25/htb-pilgrimage.html) |
| 83 | **Topology** | Linux | LaTeX Injection + gnuplot Privesc | Exploit LaTeX equation generator for file read via \input, find .htpasswd, crack for SSH, gnuplot cron SUID for root | [0xdf](https://0xdf.gitlab.io/2023/11/11/htb-topology.html) |
| 84 | **MonitorsTwo** | Linux | Cacti RCE + Docker Escape + SUID | Exploit Cacti (CVE-2022-46169) for shell in container, find MySQL creds, capsh SUID in container, CVE-2021-41091 Docker escape for root | [0xdf](https://0xdf.gitlab.io/2023/09/02/htb-monitorstwo.html) |
| 85 | **Sau** | Linux | SSRF + Maltrail RCE | Exploit request-baskets SSRF (CVE-2023-27163) to access internal Maltrail, OS command injection (CVE-2023-27163) for shell, sudo systemctl for root | [0xdf](https://0xdf.gitlab.io/2024/01/06/htb-sau.html) |
| 86 | **TwoMillion** | Linux | API IDOR + Command Injection + Kernel CVE | Reverse invite code API, register account, IDOR to make admin, command injection in VPN generate, OverlayFS CVE-2023-0386 for root | [0xdf](https://0xdf.gitlab.io/2023/06/07/htb-twomillion.html) |
| 87 | **Keeper** | Linux | Default Creds + KeePass CVE | Request Tracker default creds, find user's KeePass info in notes, exploit CVE-2023-32784 KeePass memory dump for master password, extract SSH key | [0xdf](https://0xdf.gitlab.io/2024/02/10/htb-keeper.html) |
| 88 | **CozyHosting** | Linux | Spring Boot Actuator + Command Injection | Leak session cookie from Spring Boot Actuator endpoints, command injection in SSH hostname field, crack PostgreSQL hash, sudo ssh for root | [cyberarri](https://cyberarri.com/2025/01/04/cozyhosting-htb-writeup/) |
| 89 | **Analytics** | Linux | Metabase Pre-Auth RCE + Docker Escape | Exploit Metabase CVE-2023-38646 pre-auth RCE for container shell, env variables reveal creds, OverlayFS CVE-2023-2640 for root on host | [0xdf](https://0xdf.gitlab.io/2024/03/23/htb-analytics.html) |
| 90 | **Devvortex** | Linux | Joomla Information Disclosure + RCE | Exploit Joomla CVE-2023-23752 to leak DB creds, access admin panel, template RCE for shell, apport-cli (CVE-2023-1326) for root | [dev.to](https://dev.to/mrtnsgs/hackthebox-writeup-devvortex-retired-1d42) |
| 91 | **Codify** | Linux | vm2 Sandbox Escape + Bcrypt Bug | Exploit vm2 CVE-2023-32314 sandbox escape for RCE, find SQLite DB with bcrypt hash, exploit bcrypt comparison bug in bash for root | [0xdf](https://0xdf.gitlab.io/2024/04/06/htb-codify.html) |
| 92 | **Broker** | Linux | ActiveMQ RCE + Nginx Sudo | Exploit Apache ActiveMQ CVE-2023-46604 for shell, sudo nginx config to write root SSH key | [0xdf](https://0xdf.gitlab.io/2024/02/17/htb-broker.html) |
| 93 | **Bizness** | Linux | Apache OFBiz Pre-Auth RCE | Exploit Apache OFBiz CVE-2023-49070 for shell, find hashed admin password in Derby DB, crack for root | [Medium](https://medium.com/@kennethalvin596/bizness-writeup-hackthebox-0158c1ceeac2) |

---

## 2024 Machines (Season 4 & 5)

| # | Machine | OS | Key Vulnerability / Technique | Attack Path Summary | Writeup |
|---|---------|-----|-------------------------------|---------------------|---------|
| 94 | **Perfection** | Linux | SSTI via Regex Bypass + Hash Mask | Bypass regex filter with newline, exploit Ruby ERB SSTI for shell, crack password hash using mail-revealed format mask, sudo for root | [0xdf](https://0xdf.gitlab.io/2024/07/06/htb-perfection.html) |
| 95 | **Headless** | Linux | Blind XSS + Command Injection | Steal admin cookie via blind XSS in User-Agent header, access dashboard, command injection for shell, syscheck sudo script for root | [Medium](https://medium.com/@ankitsinha81195_47457/htb-writeup-headless-67fd05b685b5) |
| 96 | **WifineticTwo** | Linux | OpenPLC Default Creds + WPS Pixie Dust | Login OpenPLC with default creds, upload PLC script for RCE, WPS Pixie Dust attack on WiFi, pivot to router for root | [Medium](https://medium.com/@jamesjarviscyber/wifinetictwo-hackthebox-writeup-management-summary-654c16eb5647) |
| 97 | **Usage** | Linux | Blind SQLi + Laravel-Admin Upload | Boolean-based SQLi in password reset leaks admin hash, Laravel-Admin CVE-2023-24249 file upload for shell, 7z wildcard file read for root | [0xdf](https://0xdf.gitlab.io/2024/08/10/htb-usage.html) |
| 98 | **BoardLight** | Linux | Dolibarr RCE + Enlightenment SUID | Exploit Dolibarr CVE-2023-30253 PHP injection for shell, find plaintext creds in config, exploit Enlightenment SUID CVE-2022-37706 for root | [cyberarri](https://cyberarri.com/2024/12/31/boardlight-htb-writeup/) |
| 99 | **Crafty** | Windows | Minecraft Log4Shell RCE + Plugin Creds | Exploit Minecraft server Log4Shell (CVE-2021-44228) for shell, reverse engineer Java plugin to find RCON creds, RunAs for admin | [0xdf](https://0xdf.gitlab.io/2024/06/15/htb-crafty.html) |
| 100 | **PermX** | Linux | Chamilo LMS CVE + Symlink Sudoers | Exploit Chamilo CVE-2023-4220 unrestricted file upload for RCE, symlink /etc/sudoers via ACL script to add sudo ALL for root | [b0rgch3n](https://b0rgch3n.github.io/2024/07/18/writeup-hackthebox-permx/) |
| 101 | **Editorial** | Linux | SSRF + Git Credential Exposure | Exploit SSRF in cover upload to access internal API, find credentials in Git repository history, CVE-2022-24439 GitPython RCE with sudo for root | [b0rgch3n](https://b0rgch3n.github.io/2024/09/03/writeup-hackthebox-editorial/) |
| 102 | **GreenHorn** | Linux | Pluck CMS RCE + Pixelated Credential | Crack SHA-512 hash from Gitea, exploit Pluck CVE-2023-50564 ZIP upload RCE, recover pixelated password from PDF using Depix for root | [HTB](https://www.hackthebox.com/machines/greenhorn) |
| 103 | **Mailing** | Windows | LFI + MonikerLink NTLM + LibreOffice | Path traversal to read hMailServer config, CVE-2024-21413 MonikerLink NTLM theft via email, CVE-2023-2255 LibreOffice for admin | [bravosec](https://blog.bravosec.net/posts/HackTheBox-Writeup-Mailing/) |
| 104 | **Sea** | Linux | WonderCMS XSS + Command Injection | Exploit WonderCMS CVE-2023-41425 XSS for RCE, command injection in internal monitoring service for root | [b0rgch3n](https://b0rgch3n.github.io/2024/08/26/writeup-hackthebox-sea/) |
| 105 | **Sightless** | Linux | SQLPad SSTI + Froxlor Blind XSS | Exploit SQLPad CVE-2022-0944 template injection for container shell, crack /etc/shadow hash, Froxlor blind XSS to access KeePass DB for root | [bravosec](https://blog.bravosec.net/posts/HackTheBox-Writeup-Sightless/) |
| 106 | **Chemistry** | Linux | Pymatgen RCE + AioHTTP Path Traversal | Exploit pymatgen library for RCE, crack hash for SSH, AioHTTP path traversal for arbitrary file read as root | [HTB](https://www.hackthebox.com/machines/chemistry) |
| 107 | **Alert** | Linux | XSS + Arbitrary File Read + Cron | XSS in markdown viewer to access internal page with arbitrary file read, crack password hash, overwrite cron-executed PHP file for root | [bravosec](https://blog.bravosec.net/posts/HackTheBox-Writeup-Alert/) |

---

## 2025-2026 Machines (Season 6+)

| # | Machine | OS | Key Vulnerability / Technique | Attack Path Summary | Writeup |
|---|---------|-----|-------------------------------|---------------------|---------|
| 108 | **Underpass** | Linux | daloRADIUS Default Creds + Mosh SUID | Enumerate SNMP, find daloRADIUS with default credentials, crack user hash for SSH, exploit mosh-server sudo for root | [Medium](https://medium.com/@NTHSec/underpass-hackthebox-ctf-walkthrough-5c51af4c60b6) |
| 109 | **Titanic** | Linux | Directory Traversal + Gitea DB Crack | Exploit directory traversal to read Gitea config and database, crack developer password hash, SSH access for root | [threatninja](https://threatninja.net/hack-the-box-titanic-machine-walkthrough-easy-difficulty/) |
| 110 | **LinkVortex** | Linux | Exposed .git + Ghost CMS Symlink | Dump exposed .git directory for credentials, exploit Ghost CMS symlink vulnerability for file read and privilege escalation | [HTB](https://www.hackthebox.com/machines/linkvortex) |
| 111 | **Cicada** | Windows | AD Enumeration + Password Spray + SeBackupPrivilege | Enumerate AD users and shares, find plaintext password in file, password spray for valid creds, abuse SeBackupPrivilege for SYSTEM | [Medium](https://medium.com/@chryb3r/cicada-hackthebox-writeup-44ce0910410b) |
| 112 | **EscapeTwo** | Windows | Excel Credential Extraction + MSSQL | Extract creds from corrupted Excel file on share, password spray, MSSQL access, ADCS ESC1 certificate abuse for admin | [emp3r0r10](https://emp3r0r10.github.io/hackthebox/EscapeTwo-Walkthrough/) |
| 113 | **Dog** | Linux | Exposed Git Repo + Backdrop CMS RCE | Discover exposed .git with credentials, credential stuffing into Backdrop CMS, authenticated RCE via module upload, sudo bee eval for root | [bravosec](https://blog.bravosec.net/posts/HackTheBox-Writeup-Dog/) |
| 114 | **Fluffy** | Windows | CVE-2025-24071 + ADCS ESC16 | Assumed breach: exploit CVE-2025-24071 NTLMv2 leak for user pivot, abuse AD Certificate Services ESC16 for Administrator | [Medium](https://medium.com/@ivandano77/fluffy-writeup-hackthebox-easy-machine-f5d460be3312) |
| 115 | **Planning** | Linux | Grafana CVE-2024-9264 + Cron | Subdomain fuzzing reveals vulnerable Grafana instance, exploit CVE-2024-9264 for RCE, enumerate cron job for root | [Medium](https://medium.com/@ruruuu/hackthebox-planning-writeup-3a1d6d597cca) |
| 116 | **Conversor** | Linux | XSLT Injection + Needrestart CVE | XSLT injection to write malicious script executed by cron, CVE-2024-48990 needrestart PYTHONPATH hijack for root | [Medium](https://medium.com/@ivandano77/conversor-writeup-hackthebox-easy-machine-8826d24b8b0b) |
| 117 | **Artificial** | Linux | TensorFlow Model Code Injection + Restic | Upload malicious AI model with injected shell code, find Backrest backup service creds, abuse Restic restore for root | [Medium](https://medium.com/@ivandano77/artificial-writeup-hackthebox-easy-machine-1a8ce4a0d1f8) |
| 118 | **CodePartTwo** | Linux | Flask js2py Sandbox Escape + npbackup | Exploit vulnerable js2py version in Flask code editor for RCE, abuse npbackup-cli running as root for privesc | [threatninja](https://threatninja.net/hack-the-box-codeparttwo-machine-walkthrough-easy-diffculty/) |
| 119 | **Expressway** | Linux | IKE PSK Crack + Sudo CVE | Enumerate IKE service on UDP 500, obtain and crack PSK hash for SSH, exploit vulnerable sudo version for root | [Medium](https://medium.com/@ivandano77/expressway-writeup-hackthebox-easy-machine-edb56665e955) |
| 120 | **Editor** | Linux | Gitea + Git Credential Exposure + Sudo | Discover Gitea repository with exposed credentials, SSH access, exploit sudo misconfiguration for root | [Medium](https://medium.com/@ivandano77/editor-writeup-hackthebox-easy-machine-c3b457f7f3ef) |

---

## Machines by Technique

### Web Exploitation
| Technique | Machines |
|-----------|----------|
| SQL Injection | Cronos, Trick, Validation, MetaTwo, PC, Usage, Pandora, Pilgrimage |
| NoSQL Injection | Stocker, Shoppy, NodeBlog |
| SSTI | Doctor, RedPanda, Perfection, Precious, Late |
| XSS | Headless, Sea, Alert, Sightless |
| SSRF | Sau, Editorial, Love, Admirer |
| LFI/RFI | Beep, FriendZone, Backdoor, Tabby, Trick |
| Command Injection | CozyHosting, Headless, Photobomb, Mailing, TwoMillion |
| File Upload | Devel, Nibbles, Granny, PermX, GreenHorn |
| Deserialization | Precious, NodeBlog |

### Active Directory
| Technique | Machines |
|-----------|----------|
| Kerberoasting | Active |
| AS-REP Roasting | Forest, Sauna |
| ADCS Abuse | Fluffy, EscapeTwo |
| GPP Passwords | Active |
| LDAP Enumeration | Support, Cicada |
| Password Spraying | Cicada, EscapeTwo |
| BloodHound Enum | Forest, Sauna |

### Classic Network Exploits
| Technique | Machines |
|-----------|----------|
| EternalBlue (MS17-010) | Blue, Legacy |
| MS08-067 | Legacy |
| Shellshock | Shocker, Beep |
| Heartbleed | Valentine |
| Log4Shell | Crafty |
| Default Credentials | Jerry, Mirai, WifineticTwo |

### Privilege Escalation Techniques
| Technique | Machines |
|-----------|----------|
| Sudo Misconfig | Shocker, Knife, Bashed, OpenAdmin, Armageddon |
| SUID/SGID Abuse | Backdoor, Irked, Antique, Timelapse |
| Kernel Exploit | Devel, Grandpa, Granny, TwoMillion, Analytics |
| Cron Job Abuse | Bashed, FriendZone, ScriptKiddie, Conversor |
| Docker/Container Escape | Tabby, GoodGames, MonitorsTwo, Analytics |
| PATH Hijack | Writeup, Previse, Laboratory, Photobomb |
| Token Impersonation | Grandpa, Granny, Bounty |

---

## Recommended Learning Paths

### Absolute Beginner (Start Here)
1. Lame - Single exploit to root
2. Blue - EternalBlue classic
3. Jerry - Default creds Tomcat
4. Netmon - FTP enum + PRTG
5. Mirai - Default Raspberry Pi creds
6. Shocker - Shellshock basics
7. Cap - IDOR + Linux capabilities
8. Knife - Simple backdoor exploit

### OSCP Preparation
1. Lame, Legacy, Blue, Devel, Optimum (Windows/Linux basics)
2. Shocker, Nibbles, Bashed, Valentine (Linux web + privesc)
3. Arctic, Grandpa, Granny, Bastard (Windows IIS/Drupal)
4. Active, Forest, Sauna (Active Directory fundamentals)
5. Cronos, Bank, Sunday, Sense (Varied techniques)

### Active Directory Focus
1. Active - GPP + Kerberoasting
2. Forest - AS-REP Roasting + DCSync
3. Sauna - AS-REP + BloodHound + DCSync
4. Support - .NET analysis + RBCD
5. Cicada - Full AD enumeration chain
6. EscapeTwo - MSSQL + ADCS
7. Fluffy - ADCS ESC16

### Modern Web Exploitation (2023-2026)
1. CozyHosting - Spring Boot Actuator
2. Devvortex - Joomla disclosure
3. Analytics - Metabase pre-auth RCE
4. Perfection - SSTI with filter bypass
5. Headless - Blind XSS cookie theft
6. Usage - SQLi + Laravel upload
7. Sightless - SQLPad SSTI
8. Planning - Grafana CVE

---

## External Resources

### Top Writeup Authors
| Author | URL | Notes |
|--------|-----|-------|
| 0xdf | [0xdf.gitlab.io](https://0xdf.gitlab.io/) | Gold standard HTB writeups, covers nearly every machine |
| IppSec | [youtube.com/ippsec](https://www.youtube.com/c/ippsec) | Video walkthroughs for every retired machine |
| Rana Khalil | [rana-khalil.gitbook.io](https://rana-khalil.gitbook.io/hack-the-box-oscp-preparation/) | OSCP-focused without Metasploit |
| 0xRick | [0xrick.github.io](https://0xrick.github.io/categories/hack-the-box/) | Clean blog writeups |
| Hackplayers | [github.com/Hackplayers](https://github.com/Hackplayers/hackthebox-writeups) | Community repo (2000+ stars) |

### Machine Lists & Trackers
| Resource | URL |
|----------|-----|
| TJNull OSCP-Like List | [NetSecFocus Trophy Room](https://docs.google.com/spreadsheets/d/1dwSMIAPIam0PuRBkCiDI88pU3yzrqqHkDtBngUHNCw8/) |
| 0xdf OffSec Exam Lists | [0xdf Cheatsheets](https://0xdf.gitlab.io/cheatsheets/offsec) |
| HTB Machine Search | [hackthebox.com/machines](https://www.hackthebox.com/machines) |
| IppSec Search | [ippsec.rocks](https://ippsec.rocks/) |
