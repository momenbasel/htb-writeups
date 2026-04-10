---
layout: default
title: Insane Machines
parent: Machines
nav_order: 4
description: "25+ Insane HTB machine writeups with walkthroughs"
permalink: /machines/insane/
---

# HackTheBox INSANE Difficulty Machines - Complete Reference

> Exhaustive list of ALL known retired Insane-rated HTB machines with key techniques and writeup links.

---

## Linux Insane Machines

| # | Machine | OS | Key Techniques | One-Line Summary | Writeup Links |
|---|---------|----|----|------|------|
| 1 | **Brainfuck** | Linux | WordPress plugin exploit, Vigenere cipher, LXD privesc | Chain WP auth bypass with crypto analysis and container group abuse for root | [0xdf](https://0xdf.gitlab.io/2022/06/01/htb-brainfuck.html), [Medium](https://sparshjazz.medium.com/hackthebox-brainfuck-difficulty-insane-53f0fe650f5b) |
| 2 | **Ariekei** | Linux | Shellshock, ImageTragick, Docker pivoting | Exploit two famous CVEs through Docker container layers for multi-hop access | [0xdf](https://0xdf.gitlab.io/2022/04/20/htb-ariekei.html), [Medium](https://medium.com/@gabriel.pirjolescu/hack-the-box-ariekei-write-up-cd8f261cd2ca) |
| 3 | **Jail** | Linux | NFS, custom binary exploit, rvim escape | Escape multiple sandbox environments with buffer overflow and NFS share abuse | [HTB](https://www.hackthebox.com/machines/jail) |
| 4 | **Nightmare** | Linux | Second-order SQLi, exploit modification | Register SQLi-laden username then trigger on login for indirect injection | [HackingArticles](https://www.hackingarticles.in/hack-the-box-nightmare-walkthrough/) |
| 5 | **CTF** | Linux | LDAP injection, OTP bypass, token manipulation | Exploit LDAP-based auth with injection to bypass OTP and escalate | [HTB](https://www.hackthebox.com/machines/ctf) |
| 6 | **Mischief** | Linux | SNMP enumeration, IPv6, command injection | Leverage SNMP to discover IPv6 address, then command injection to root | [HTB](https://www.hackthebox.com/machines/mischief) |
| 7 | **Fulcrum** | Linux | Multi-pivot (Linux/Windows), PowerShell, XXE | Chain XXE through multiple network pivots across Linux and Windows hosts | [HTB](https://www.hackthebox.com/machines/fulcrum), [dastinia](https://dastinia.io/write-up/hackthebox/2018/06/27/hackthebox-fulcrum-writeup/) |
| 8 | **Rope** | Linux | Format string, BOF, canary bypass, ret2libc | Binary exploitation gauntlet with format strings and return-oriented attacks | [Medium](https://medium.com/@noobintheshell/htb-rope-6e06c00f07b8) |
| 9 | **Bankrobber** | Windows | XSS, CSRF, SQLi source leak, BOF | Chain XSS to steal admin cookies, SQLi to leak code, BOF for SYSTEM | [0xdf](https://0xdf.gitlab.io/2020/03/07/htb-bankrobber.html), [snowscan](https://snowscan.io/htb-writeup-bankrobber/) |
| 10 | **Zetta** | Linux | FTP bounce IPv6 leak, rsync brute, PostgreSQL injection | FTP FXP leaks IPv6, rsync password brute on IPv6, syslog SQL injection to postgres | [0xdf](https://0xdf.gitlab.io/2020/02/22/htb-zetta.html) |
| 11 | **PlayerTwo** | Linux | Twirp protobuf API, firmware analysis, heap exploit | Enumerate protobuf API, analyze firmware update mechanism, heap exploitation for root | [0xdf](https://0xdf.gitlab.io/2020/06/27/htb-playertwo.html) |
| 12 | **RE** | Windows | Malicious ODS macro, WinRAR CVE, UsoSvc privesc | Upload malicious ODS to SOC malware dropbox, exploit WinRAR zipslip and UsoSvc | [Medium](https://device-asdf.medium.com/re-hackthebox-writeup-930ed462bad1) |
| 13 | **Oouch** | Linux | OAuth CSRF chain, SSRF, DBus exploitation, uWSGI RCE | Chain OAuth flaws with SSRF to steal sessions, pivot through Docker via DBus | [0xdf](https://0xdf.gitlab.io/2020/08/01/htb-oouch.html), [hg8](https://hg8.sh/posts/oouch/) |
| 14 | **Unbalanced** | Linux | Rsync, EncFS cracking, Squid proxy, XPath injection, Pi-hole RCE | Decrypt EncFS backup via rsync, chain XPath injection through Squid to Pi-hole RCE | [0xdf](https://0xdf.gitlab.io/2020/12/05/htb-unbalanced.html) |
| 15 | **Travel** | Linux | Memcache SSRF poisoning, PHP deserialization, LDAP privesc | Poison memcache via gopher SSRF with serialized PHP payload, escalate through LDAP | [snowscan](https://snowscan.io/htb-writeup-travel/), [chr0x6eos](https://chr0x6eos.github.io/2020/09/12/htb-Travel.html) |
| 16 | **Dyplesher** | Linux | Git repo creds, Minecraft plugin RCE, Wireshark sniffing | Discover creds in exposed Git, upload malicious Minecraft plugin, sniff traffic as wireshark group | [zweilosec](https://zweilosec.github.io/posts/dyplesher/) |
| 17 | **Laser** | Linux | Printer exploitation, gRPC/protobuf, Solr SSRF, pickle deser | Query network printer for encrypted PDF, interact with gRPC to exploit Solr via pickle | [0xdf](https://0xdf.gitlab.io/2020/12/19/htb-laser.html) |
| 18 | **CrossFit** | Linux | XSS to CORS to CSRF, FTP upload, command injection | Chain XSS through CORS to forge admin account on subdomain, upload webshell via FTP | [0xdf](https://0xdf.gitlab.io/2021/03/20/htb-crossfit.html) |
| 19 | **Fatty** | Linux | Java thick client reversing, deserialization, classpath injection | Reverse Java client-server app, exploit insecure deserialization via classpath manipulation | [HTB](https://www.hackthebox.com/machines/fatty) |
| 20 | **RopeTwo** | Linux | V8 JavaScript engine exploit, heap, kernel module | Exploit patched V8 engine with OOB read/write, craft addrof/fakeobj primitives, kernel exploit | [0xdf](https://0xdf.gitlab.io/2021/01/16/htb-ropetwo.html) |
| 21 | **CrossFitTwo** | BSD | Unbound DNS poisoning, WebSocket injection, Yubikey | Poison Unbound DNS, exploit WebSocket chat, abuse Yubikey OTP for privilege escalation | [HTB](https://www.hackthebox.com/machines/crossfittwo) |
| 22 | **Stacked** | Linux | XSS, LocalStack/AWS exploitation, Lambda RCE | Exploit XSS in web form to pivot to internal LocalStack, abuse Lambda for code execution | [HTB](https://www.hackthebox.com/machines/stacked) |
| 23 | **Unobtanium** | Linux | Electron app reversing, prototype pollution, K8s lateral movement | Reverse Electron app, chain LFI + prototype pollution + command injection, pivot through Kubernetes | [0xdf](https://0xdf.gitlab.io/2021/09/04/htb-unobtainium.html) |
| 24 | **Sink** | Linux | HTTP request smuggling, AWS Secrets Manager, KMS | Exploit HTTP desync to hijack admin session, enumerate AWS secrets and decrypt with KMS | [threatninja](https://threatninja.net/hackthebox-sink-machine-walkthrough-insane-difficulty/) |
| 25 | **Proper** | Windows | SQLi with HMAC bypass, ToC/ToU race, Go binary analysis | Exploit SQL injection past HMAC validation, race condition file write, reverse Go binary | [vulndev](https://vuln.dev/2021/08/21/sqli-toc-tou-arbitrary-file-write-proper-hackthebox/) |
| 26 | **Scanned** | Linux | Chroot jail escape, setuid abuse, Linux capabilities | Upload binary to escape chroot sandbox, abuse setuid with LD_PRELOAD through jail boundary | [0xdf](https://0xdf.gitlab.io/2022/09/10/htb-scanned.html) |
| 27 | **Response** | Linux | Advanced SSRF, Socket.io exploitation, LDAP | SSRF to internal chat app, extract source code, escalate through LDAP | [HTB](https://www.hackthebox.com/machines/response) |
| 28 | **Derailed** | Linux | Ruby on Rails XSS (username overflow), open() pipe injection | Username buffer overflow triggers XSS, steal admin CSRF token, Ruby open() command injection | [0xdf](https://0xdf.gitlab.io/2023/07/22/htb-derailed.html), [threatninja](https://threatninja.net/hack-the-box-derailed-machine-walkthrough-insane-difficulty/) |
| 29 | **Corporate** | Linux | CSP bypass XSS, cookie theft, Bitwarden PIN brute, Gitea LDAP | Chain XSS past strict CSP to steal auth cookie, brute Bitwarden vault, enumerate Gitea via LDAP | [HTB](https://www.hackthebox.com/machines/corporate) |

## Windows Insane Machines

| # | Machine | OS | Key Techniques | One-Line Summary | Writeup Links |
|---|---------|----|----|------|------|
| 30 | **Minion** | Windows | ICMP exfiltration, PowerShell, IIS | Advanced PowerShell exploitation through restrictive firewall with ICMP tunneling | [HackingArticles](https://www.hackingarticles.in/hack-the-box-minion-walkthrough/) |
| 31 | **Fighter** | Windows | SQLi blacklist bypass, post-exploitation enumeration | Bypass SQL injection blacklists, chain web and post-exploitation for domain compromise | [HTB](https://www.hackthebox.com/machines/fighter) |
| 32 | **Sizzle** | Windows | SMB hash theft, ADCS cert abuse, Kerberoasting, DCSync | Steal NTLM hashes via writable SMB share, abuse certs for Kerberoast to DCSync | [InfoSecWriteups](https://infosecwriteups.com/hack-the-box-sizzle-write-up-62f3464701be) |
| 33 | **Ethereal** | Windows | DNS exfiltration, malicious .lnk files, cert-based AppLocker bypass | Exfiltrate data over DNS, lateral movement via shortcut files, bypass AppLocker with certs | [HTB](https://www.hackthebox.com/machines/ethereal) |
| 34 | **Multimaster** | Windows | Unicode SQLi WAF bypass, .NET reversing, AD exploitation | Bypass WAF with Unicode-encoded SQL injection, reverse .NET for creds, chain AD attacks | [0xdf](https://0xdf.gitlab.io/2020/09/19/htb-multimaster.html), [zweilosec](https://zweilosec.gitbook.io/htb-writeups/windows-machines/insane/multimaster) |
| 35 | **Hathor** | Windows | mojoPortal default creds, ASPX webshell, DLL hijacking 7zip | Upload ASPX webshell through mojoPortal, IIS impersonation, DLL hijack 7zip64.dll | [0xdf](https://0xdf.gitlab.io/2022/11/19/htb-hathor.html), [heartburn](https://heartburn.dev/hack-the-box-walkthroughs-hathor/) |
| 36 | **Sekhmet** | Windows | NodeJS deserialization WAF bypass, ZipCrypto KPA, AppLocker bypass | Deserialize through WAF with unicode, crack ZipCrypto, bypass AppLocker via InstallUtil.exe | [0xdf](https://0xdf.gitlab.io/2023/04/01/htb-sekhmet.html) |
| 37 | **Rebound** | Windows | RID cycling, AS-REP/Kerberoast, RemotePotato0 relay, RBCD, gMSA | Chain AD attacks: RID cycling to Kerberoast to cross-session relay to gMSA password read | [0xdf](https://0xdf.gitlab.io/2024/03/30/htb-rebound.html), [Medium](https://arth0s.medium.com/hackthebox-rebound-write-up-insane-ab8eb3679bff) |
| 38 | **Anubis** | Windows | ADCS writable certificate template, Windows PKI abuse | Exploit writable cert template in Windows PKI to escalate to Domain Admin | [HTB](https://www.hackthebox.com/machines/anubis) |
| 39 | **Absolute** | Windows | Image metadata username enum, AD Kerberos-only attack chain | Extract usernames from image metadata, pure Kerberos exploitation in hardened AD environment | [HTB](https://www.hackthebox.com/machines/absolute) |
| 40 | **Mist** | Windows | CMS path traversal, credential cracking, AD misconfigurations | Traverse CMS paths for backup with hashed creds, chain AD misconfigs to domain compromise | [4xura](https://4xura.com/ctf/htb-writeup-mist/) |
| 41 | **Ghost** | Windows | LDAP injection, Gitea arbitrary file read + RCE, Golden SAML | LDAP injection leaks Gitea creds, chain file read with RCE, craft Golden SAML for domain admin | [0xdf](https://0xdf.gitlab.io/2025/04/05/htb-ghost.html), [Medium](https://medium.com/@rahulhoysala07/hackthebox-labs-ghost-writeup-insane-2e652ce9366c) |
| 42 | **Infiltrator** | Windows | AS-REP roasting, Output Messenger exploitation, BitLocker + NTDS.dit | Roast user creds, infiltrate internal messenger app, decrypt BitLocker volume for NTDS.dit | [HTB](https://www.hackthebox.com/machines/infiltrator) |
| 43 | **University** | Windows | xhtml2pdf RCE (CVE-2023-33733), cert forgery, CVE-2023-36025, unconstrained delegation | Chain PDF export RCE with cert forgery and archive exploit to unconstrained delegation attack | [0xdf](https://0xdf.gitlab.io/2025/08/09/htb-university.html), [Medium](https://medium.com/@shivam21/breaking-the-university-an-advanced-hackthebox-insane-walkthrough-cde0e1ebd8c2) |
| 44 | **Hercules** | Windows | LDAP injection (double URL-encoded), Kerberos-only DC, shadow credentials | Inject into LDAP via SSO form on NTLM-disabled DC, extract AD descriptions, shadow creds + RBCD | [1337sheets](https://www.1337sheets.com/p/hack-the-box-season-nine-htb-hercules-writeup-insane-weekly-october-eighteenth), [cyb3rtr0n](https://cyb3rtr0nian.github.io/posts/hercules-htb/) |
| 45 | **DarkCorp** | Windows | RoundCube XSS + IDOR (CVE-2024-42009), AD multi-host chain | Exploit RoundCube to phish developer emails, pivot through analytics dashboard to AD domain compromise | [Medium](https://medium.com/@rahulhoysala07/hackthebox-darkcorp-writeup-insane-b3c49b86be20), [threatninja](https://threatninja.net/hack-the-box-darkcorp-machine-walkthrough-insane-difficulity/) |

---

**Note on difficulty corrections from user's original list:**
- **TheNotebook** = Medium (not Insane) - JWT key injection, Docker container escape
- **Schooled** = Medium (not Insane) - Moodle XSS + CVE chain
- **BreadCrumbs** = Hard (not Insane) - PHP session manipulation, JWT, SQLi
- **Atom** = Medium (not Insane) - Electron-Builder exploit
- **CarpeDiem** = Hard (not Insane) - VoIP, Docker container escape (CVE-2022-0492)
- **Cerberus** = Hard (not Insane) - Icinga pre-auth RCE, container to Windows pivot
- **Zetta** = Hard (officially, though insane-level difficulty) - FTP IPv6, rsync, PostgreSQL injection
- **DarkZero** = Hard (not Insane) - MSSQL linked servers, cross-forest trust abuse

---

**Total confirmed Insane machines: ~45+**
(New insane machines are released regularly; this list covers all known retired insane machines through early 2026.)
