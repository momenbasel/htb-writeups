# 0xdf HackTheBox Machine Writeups - Complete List
# Source: https://0xdf.gitlab.io/cheatsheets/htb-interactive
# Total: 500 machines
# Last Updated: 2026-04-10

## Statistics
- Total Machines: 500
- By Difficulty: Easy(149), Medium(178), Hard(113), Insane(60)
- By OS: Linux(340), Windows(147), OpenBSD(5), FreeBSD(4), Android(1), Chrome(1), NetBSD(1), Solaris(1)

---

## Easy (149 machines)

| # | Name | OS | Release Date | Key Techniques | URL |
|---|------|----|-----------|----|-----|
| 1 | **Conversor** | Linux | 25 Oct 2025 | burp, burp-repeater, ubuntu, flask, python, source-code, arbitrary-write, directory-traversal | [writeup](https://0xdf.gitlab.io/2026/03/21/htb-conversor.html) |
| 2 | **Expressway** | Linux | 20 Sep 2025 | udp, ike, ike-scan, ike-aggressive, ipsec, vpn, hashcat, tftp | [writeup](https://0xdf.gitlab.io/2026/03/07/htb-expressway.html) |
| 3 | **soulmate** | Linux | 06 Sep 2025 | ubuntu, ffuf, subdomain, php, crush-ftp, feroxbuster, cve-2025-31161, cve-2025-54309 | [writeup](https://0xdf.gitlab.io/2026/02/14/htb-soulmate.html) |
| 4 | **CodeTwo** | Linux | 16 Aug 2025 | linux, ubuntu, python, flask, gunicorn, javascript, sandbox-escape, cve-2024-28397 | [writeup](https://0xdf.gitlab.io/2026/01/31/htb-codetwo.html) |
| 5 | **Editor** | Linux | 02 Aug 2025 | ubuntu, xwiki, ffuf, subdomain, react, wappalyzer, feroxbuster, cve-2025-24893 | [writeup](https://0xdf.gitlab.io/2025/12/06/htb-editor.html) |
| 6 | **Outbound** | Linux | 12 Jul 2025 | assume-breach, ubuntu, netexec, roundcube, cve-2025-49113, deserialization, php, php-deserialization | [writeup](https://0xdf.gitlab.io/2025/11/15/htb-outbound.html) |
| 7 | **Artificial** | Linux | 21 Jun 2025 | ubuntu, tensorflow, feroxbuster, deserialization, crackstation, backrest, restic | [writeup](https://0xdf.gitlab.io/2025/10/25/htb-artificial.html) |
| 8 | **Fluffy** | Windows | 24 May 2025 | assume-breach, windows, active-directory, adcs, netexec, certipy, bloodhound, bloodhound-python | [writeup](https://0xdf.gitlab.io/2025/09/20/htb-fluffy.html) |
| 9 | **Baby** | Windows | 18 Sep 2025 | vulnlab, windows, active-directory, netexec, netexec-ldap-query, password-spray, netexec-change-password, backup-operators | [writeup](https://0xdf.gitlab.io/2025/09/19/htb-baby.html) |
| 10 | **Forgotten** | Linux | 16 Sep 2025 | vulnlab, ubuntu, debian, docker, feroxbuster, limesurvey, docker-mysql, limesurvey-plugin | [writeup](https://0xdf.gitlab.io/2025/09/16/htb-forgotten.html) |
| 11 | **Planning** | Linux | 10 May 2025 | assume-breach, ffuf, subdomain, grafana, nginx, ubuntu, cve-2024-9264, sqli | [writeup](https://0xdf.gitlab.io/2025/09/13/htb-planning.html) |
| 12 | **Lock** | Windows | 21 Aug 2025 | vulnlab, windows, feroxbuster, gitea, gitea-api, swagger, webshell, mremoteng | [writeup](https://0xdf.gitlab.io/2025/08/21/htb-lock.html) |
| 13 | **Nocturnal** | Linux | 12 Apr 2025 | ubuntu, feroxbuster, idor, command-injection, burp, burp-repeater, password-reuse, crackstation | [writeup](https://0xdf.gitlab.io/2025/08/16/htb-nocturnal.html) |
| 14 | **Code** | Linux | 22 Mar 2025 | ubuntu, python, flask, feroxbuster, filter, ffuf, youtube, crackstation | [writeup](https://0xdf.gitlab.io/2025/08/02/htb-code.html) |
| 15 | **Manage** | Linux | 29 Jul 2025 | vulnlab, ubuntu, tomcat, feroxbuster, java-rmi, java-jmx, remote-management-guesser, beanshooter | [writeup](https://0xdf.gitlab.io/2025/07/29/htb-manage.html) |
| 16 | **RetroTwo** | Windows | 22 Jul 2025 | vulnlab, windows, active-directory, netexec, smbclient, microsoft-access, hashcat, bloodhound | [writeup](https://0xdf.gitlab.io/2025/07/22/htb-retrotwo.html) |
| 17 | **Reset** | Linux | 15 Jul 2025 | vulnlab, ubuntu, berkeley-r-commands, feroxbuster, burp, burp-proxy, burp-repeater, php | [writeup](https://0xdf.gitlab.io/2025/07/15/htb-reset.html) |
| 18 | **Dog** | Linux | 08 Mar 2025 | ubuntu, backdrop-cms, feroxbuster, source-code, backdrop-plugin, bee, oscp-like-v3 | [writeup](https://0xdf.gitlab.io/2025/07/12/htb-dog.html) |
| 19 | **VulnEscape** | Windows | 08 Jul 2025 | vulnlab, windows, rdp, netexec, windows-kiosk, kiosk-escape, remote-desktop-plus, perplexity | [writeup](https://0xdf.gitlab.io/2025/07/08/htb-vulnescape.html) |
| 20 | **Data** | Linux | 01 Jul 2025 | vulnlab, grafana, cve-2021-43798, directory-traversal, file-read, grafana2hashcat, docker, docker-exec | [writeup](https://0xdf.gitlab.io/2025/07/01/htb-data.html) |
| 21 | **Retro** | Windows | 24 Jun 2025 | vulnlab, windows, active-directory, netexec, rid-cycle, pre-windows-2000, changepasswd-py, certipy | [writeup](https://0xdf.gitlab.io/2025/06/24/htb-retro.html) |
| 22 | **Titanic** | Linux | 15 Feb 2025 | ubuntu, ffuf, subdomain, flask, feroxbuster, gitea, source-code, docker | [writeup](https://0xdf.gitlab.io/2025/06/21/htb-titanic.html) |
| 23 | **Down** | Linux | 14 Jun 2025 | vulnlab, ubuntu, feroxbuster, ssrf, ffuf, burp, burp-repeater, curl | [writeup](https://0xdf.gitlab.io/2025/06/17/htb-down.html) |
| 24 | **EscapeTwo** | Windows | 11 Jan 2025 | assume-breach, netexec, mssql, smb, windows, active-directory, xlsx, password-spray | [writeup](https://0xdf.gitlab.io/2025/05/24/htb-escapetwo.html) |
| 25 | **UnderPass** | Linux | 21 Dec 2024 | snmp, snmpwalk, daloradius, feroxbuster, default-creds, netexec, mosh | [writeup](https://0xdf.gitlab.io/2025/05/10/htb-underpass.html) |
| 26 | **LinkVortex** | Linux | 07 Dec 2024 | subdomain, ffuf, ghost, git, git-dumper, apache, feroxbuster, cve-2023-40028 | [writeup](https://0xdf.gitlab.io/2025/04/12/htb-linkvortex.html) |
| 27 | **Alert** | Linux | 23 Nov 2024 | ffuf, subdomain, markdown-to-html, feroxbuster, html-injection, xss, phishing, python | [writeup](https://0xdf.gitlab.io/2025/03/22/htb-alert.html) |
| 28 | **Chemistry** | Linux | 19 Oct 2024 | cif, flask, feroxbuster, cve-2024-23346, pymatgen, deserialization, crackstation, python-aiohttp | [writeup](https://0xdf.gitlab.io/2025/03/08/htb-chemistry.html) |
| 29 | **Cicada** | Windows | 28 Sep 2024 | netexec, rid-cycle, password-spray, backup-operators, sebackupprivilege, reg-py, secretsdump, ntds | [writeup](https://0xdf.gitlab.io/2025/02/15/htb-cicada.html) |
| 30 | **Sightless** | Linux | 07 Sep 2024 | ftp, lftp, ftp-tls, feroxbuster, sqlpad, cve-2022-0944, ssti, python-ssti | [writeup](https://0xdf.gitlab.io/2025/01/11/htb-sightless.html) |
| 31 | **Sea** | Linux | 10 Aug 2024 | feroxbuster, wondercms, cve-2023-41425, xss, plugin, hashcat, file-read, command-injection | [writeup](https://0xdf.gitlab.io/2024/12/21/htb-sea.html) |
| 32 | **GreenHorn** | Linux | 20 Jul 2024 | ubuntu, pluck-cms, gitea, pluck-module, webshell, password-reuse, depixalate, pdf | [writeup](https://0xdf.gitlab.io/2024/12/07/htb-greenhorn.html) |
| 33 | **PermX** | Linux | 06 Jul 2024 | ubuntu, ffuf, subdomain, feroxbuster, chamilo, php, cve-2023-31803, webshell | [writeup](https://0xdf.gitlab.io/2024/11/02/htb-permx.html) |
| 34 | **Editorial** | Linux | 15 Jun 2024 | ubuntu, python, flask, ssrf, feroxbuster, ffuf, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2024/10/19/htb-editorial.html) |
| 35 | **BoardLight** | Linux | 25 May 2024 | apache, ubuntu, feroxbuster, ffuf, subdomain, dolibarr, cve-2023-30253, enlightenment | [writeup](https://0xdf.gitlab.io/2024/09/28/htb-boardlight.html) |
| 36 | **Mailing** | Windows | 04 May 2024 | ffuf, feroxbuster, file-read, directory-traversal, lfi, hmailserver, crackstation, cve-2024-21413 | [writeup](https://0xdf.gitlab.io/2024/09/07/htb-mailing.html) |
| 37 | **Usage** | Linux | 13 Apr 2024 | ubuntu, ffuf, subdomain, laravel, sqli, sqlmap, blind-sqli, hashcat | [writeup](https://0xdf.gitlab.io/2024/08/10/htb-usage.html) |
| 38 | **Headless** | Linux | 23 Mar 2024 | debian, flask, python, burp, burp-repeater, xss, feroxbuster, ffuf | [writeup](https://0xdf.gitlab.io/2024/07/20/htb-headless.html) |
| 39 | **Perfection** | Linux | 02 Mar 2024 | ubuntu, ruby, ruby-sinatra, ruby-webrick, ssti, ssti-ruby, feroxbuster, newline-injection | [writeup](https://0xdf.gitlab.io/2024/07/06/htb-perfection.html) |
| 40 | **Crafty** | Windows | 10 Feb 2024 | windows, minecraft, feroxbuster, wireshark, log4shell, log4j, minecraft-client, cve-2021-44228 | [writeup](https://0xdf.gitlab.io/2024/06/15/htb-crafty.html) |
| 41 | **Bizness** | Linux | 06 Jan 2024 | debian, ofbiz, feroxbuster, cve-2023-49070, ysoserial, java, hashcat, ij | [writeup](https://0xdf.gitlab.io/2024/05/25/htb-bizness.html) |
| 42 | **DevVortex** | Linux | 25 Nov 2023 | ubuntu, ffuf, subdomain, joomla, cve-2023-23752, mass-assignment, information-disclosure, joomla-webshell | [writeup](https://0xdf.gitlab.io/2024/04/27/htb-devvortex.html) |
| 43 | **Codify** | Linux | 04 Nov 2023 | ubuntu, nodejs, express, js-vm2, cve-2023-37903, cve-2023-37466, cve-2023-32314, cve-2023-30547 | [writeup](https://0xdf.gitlab.io/2024/04/06/htb-codify.html) |
| 44 | **Analytics** | Linux | 07 Oct 2023 | ffuf, subdomain, feroxbuster, metabase, cve-2023-38646, burp, burp-repeater, docker | [writeup](https://0xdf.gitlab.io/2024/03/23/htb-analytics.html) |
| 45 | **CozyHosting** | Linux | 02 Sep 2023 | ubuntu, java, spring-boot, spring-boot-actuator, feroxbuster, command-injection, bash-ifs, bash-brace-expansion | [writeup](https://0xdf.gitlab.io/2024/03/02/htb-cozyhosting.html) |
| 46 | **Keeper** | Linux | 12 Aug 2023 | request-tracker, default-creds, keepass, cve-2022-32784, dotnet, dotnet-linux, docker, chatgpt | [writeup](https://0xdf.gitlab.io/2024/02/10/htb-keeper.html) |
| 47 | **Sau** | Linux | 08 Jul 2023 | request-baskets, feroxbuster, cve-2023-27163, ssrf, maltrail, command-injection, systemctl, less | [writeup](https://0xdf.gitlab.io/2024/01/06/htb-sau.html) |
| 48 | **Pilgrimage** | Linux | 24 Jun 2023 | debian, git, git-dumper, feroxbuster, cve-2022-44268, image-magick, pngcrush, sqlite | [writeup](https://0xdf.gitlab.io/2023/11/25/htb-pilgrimage.html) |
| 49 | **Broker** | Linux | 09 Nov 2023 | ubuntu, activemq, cve-2023-46604, deserialization, java, nginx, shared-object, ldpreload | [writeup](https://0xdf.gitlab.io/2023/11/09/htb-broker.html) |
| 50 | **Topology** | Linux | 10 Jun 2023 | ubuntu, feroxbuster, ffuf, subdomain, latex, pdftex, file-read, htaccess | [writeup](https://0xdf.gitlab.io/2023/11/04/htb-topology.html) |
| 51 | **PC** | Linux | 20 May 2023 | ubuntu, grpc, grpcurl, sqlite, sqli, sqli-sqlite, pyload, cve-2023-0297 | [writeup](https://0xdf.gitlab.io/2023/10/07/htb-pc.html) |
| 52 | **Wifinetic** | Linux | 13 Sep 2023 | openwrt, wpa, reaver, wps, wps-bruteforce, wash | [writeup](https://0xdf.gitlab.io/2023/09/16/htb-wifinetic.html) |
| 53 | **MonitorsTwo** | Linux | 29 Apr 2023 | ubuntu, cacti, cve-2022-46169, command-injection, metasploit, wfuzz, burp-repeater, burp | [writeup](https://0xdf.gitlab.io/2023/09/02/htb-monitorstwo.html) |
| 54 | **Busqueda** | Linux | 08 Apr 2023 | flask, ubuntu, searchor, feroxbuster, python-eval, command-injection, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2023/08/12/htb-busqueda.html) |
| 55 | **Inject** | Linux | 11 Mar 2023 | ubuntu, file-read, directory-traversal, tomcat, feroxbuster, burp-repeater, burp, spring-cloud-function-spel-injection | [writeup](https://0xdf.gitlab.io/2023/07/08/htb-inject.html) |
| 56 | **Stocker** | Linux | 14 Jan 2023 | ubuntu, ffuf, subdomain, feroxbuster, burp, burp-repeater, chatgpt, express | [writeup](https://0xdf.gitlab.io/2023/06/24/htb-stocker.html) |
| 57 | **Soccer** | Linux | 17 Dec 2022 | ffuf, subdomain, ferobuster, express, ubuntu, tiny-file-manager, default-creds, upload | [writeup](https://0xdf.gitlab.io/2023/06/10/htb-soccer.html) |
| 58 | **TwoMillion** | Linux | 07 Jun 2023 | ffuf, feroxbuster, php, ubuntu, javascript, burp, burp-repeater, api | [writeup](https://0xdf.gitlab.io/2023/06/07/htb-twomillion.html) |
| 59 | **Precious** | Linux | 26 Nov 2022 | subdomain, ffuf, ruby, phusion, passenger, nginx, exiftool, pdfkit | [writeup](https://0xdf.gitlab.io/2023/05/20/htb-precious.html) |
| 60 | **MetaTwo** | Linux | 29 Oct 2022 | wfuzz, php, wordpress, bookingpress, cve-2022-0739, sqli, sqlmap, john | [writeup](https://0xdf.gitlab.io/2023/04/29/htb-metatwo.html) |
| 61 | **Photobomb** | Linux | 08 Oct 2022 | bash, bash-test, feroxbuster, image-magick, command-injection, injection, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2023/02/11/htb-photobomb.html) |
| 62 | **Shoppy** | Linux | 17 Sep 2022 | feroxbuster, nosql-injection, mattermost, nosql-auth-bypass, burp, burp-repeater, nodejs, mongodb | [writeup](https://0xdf.gitlab.io/2023/01/14/htb-shoppy.html) |
| 63 | **Support** | Windows | 30 Jul 2022 | ldapsearch, crackmapexec, smbclient, dotnet, wireshark, reverse-engineering, dnspy, bloodhound | [writeup](https://0xdf.gitlab.io/2022/12/17/htb-support.html) |
| 64 | **RedPanda** | Linux | 09 Jul 2022 | spring-boot, ssti, feroxbuster, wfuzz, filter, thymeleaf, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2022/11/26/htb-redpanda.html) |
| 65 | **Squashed** | Linux | 10 Nov 2022 | feroxbuster, nfs, showmount, x11, xauthority, webshell, screenshare, keepass | [writeup](https://0xdf.gitlab.io/2022/11/21/htb-squashed.html) |
| 66 | **Trick** | Linux | 18 Jun 2022 | smtp, smtp-user-enum, zone-transfer, vhosts, wfuzz, feroxbuster, employee-management-system, sqli | [writeup](https://0xdf.gitlab.io/2022/10/29/htb-trick.html) |
| 67 | **OpenSource** | Linux | 21 May 2022 | upload, source-code, git, git-hooks, flask, directory-traversal, file-read, flask-debug | [writeup](https://0xdf.gitlab.io/2022/10/08/htb-opensource.html) |
| 68 | **Timelapse** | Windows | 26 Mar 2022 | windows, active-directory, crackmapexec, smbclient, laps, zip2john, john, pfx2john | [writeup](https://0xdf.gitlab.io/2022/08/20/htb-timelapse.html) |
| 69 | **Late** | Linux | 23 Apr 2022 | ocr, flask, kolourpaint, tesseract, burp-repeater, ssti, jinja2, payloadsallthethings | [writeup](https://0xdf.gitlab.io/2022/07/30/htb-late.html) |
| 70 | **RouterSpace** | Linux | 26 Feb 2022 | ubuntu, android, apk, feroxbuster, apktool, reverse-engineering, android-react-native, react-native | [writeup](https://0xdf.gitlab.io/2022/07/09/htb-routerspace.html) |
| 71 | **Paper** | Linux | 05 Feb 2022 | feroxbuster, wfuzz, vhosts, wordpress, wpscan, rocket-chat, cve-2019-17671, directory-traversal | [writeup](https://0xdf.gitlab.io/2022/06/18/htb-paper.html) |
| 72 | **Pandora** | Linux | 08 Jan 2022 | feroxbuster, vhosts, snmp, snmpwalk, snmpbulkwalk, mibs, python, python-dataclass | [writeup](https://0xdf.gitlab.io/2022/05/21/htb-pandora.html) |
| 73 | **Mirai** | Linux | 01 Sep 2017 | raspberrypi, feroxbuster, plex, pihole, default-creds, deleted-file, extundelete, testdisk | [writeup](https://0xdf.gitlab.io/2022/05/18/htb-mirai.html) |
| 74 | **Return** | Windows | 27 Sep 2021 | windows, crackmapexec, printer, feroxbuster, ldap, wireshark, evil-winrm, server-operators | [writeup](https://0xdf.gitlab.io/2022/05/05/htb-return.html) |
| 75 | **Antique** | Linux | 27 Sep 2021 | printer, jetdirect, telnet, python, snmp, snmpwalk, tunnel, chisel | [writeup](https://0xdf.gitlab.io/2022/05/03/htb-antique.html) |
| 76 | **Backdoor** | Linux | 20 Nov 2021 | wordpress, wpscan, feroxbuster, exploit-db, directory-traversal, ebooks-download, proc, bash | [writeup](https://0xdf.gitlab.io/2022/04/23/htb-backdoor.html) |
| 77 | **Secret** | Linux | 30 Oct 2021 | jwt, pyjwt, express, feroxbuster, api, source-code, git, command-injection | [writeup](https://0xdf.gitlab.io/2022/03/26/htb-secret.html) |
| 78 | **Driver** | Windows | 02 Oct 2021 | windows, feroxbuster, net-ntlmv2, scf, responder, hashcat, crackmapexec, evil-winrm | [writeup](https://0xdf.gitlab.io/2022/02/26/htb-driver.html) |
| 79 | **GoodGames** | Linux | 21 Feb 2022 | uni-ctf, vhosts, sqli, sqli-bypass, sqli-union, feroxbuster, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2022/02/23/htb-goodgames.html) |
| 80 | **SteamCloud** | Linux | 14 Feb 2022 | uni-ctf, kubernetes, minikube, kubectl, kubeletctl, container | [writeup](https://0xdf.gitlab.io/2022/02/14/htb-steamcloud.html) |
| 81 | **Horizontall** | Linux | 28 Aug 2021 | feroxbuster, source-code, vhosts, strapi, cve-2019-18818, cve-2019-19609, command-injection, burp | [writeup](https://0xdf.gitlab.io/2022/02/05/htb-horizontall.html) |
| 82 | **NodeBlog** | Linux | 10 Jan 2022 | uhc, youtube, python, feroxbuster, nodejs, nosql-injection, payloadsallthethings, xxe | [writeup](https://0xdf.gitlab.io/2022/01/10/htb-nodeblog.html) |
| 83 | **Previse** | Linux | 07 Aug 2021 | execute-after-redirect, burp, burp-repeater, source-code, php, injection, command-injection, path-hijack | [writeup](https://0xdf.gitlab.io/2022/01/08/htb-previse.html) |
| 84 | **BountyHunter** | Linux | 24 Jul 2021 | xxe, feroxbuster, decoder, python, credentials, password-reuse, python-eval, command-injection | [writeup](https://0xdf.gitlab.io/2021/11/20/htb-bountyhunter.html) |
| 85 | **Nunchucks** | Linux | 02 Nov 2021 | uhc, wfuzz, vhosts, feroxbuster, ssti, express, express-nunchucks, capabilities | [writeup](https://0xdf.gitlab.io/2021/11/02/htb-nunchucks.html) |
| 86 | **Explore** | Android | 26 Jun 2021 | android, adb, es-file-explorer, cve-2019-6447, credentials, tunnel | [writeup](https://0xdf.gitlab.io/2021/10/30/htb-explore.html) |
| 87 | **Cap** | Linux | 05 Jun 2021 | pcap, idor, feroxbuster, wireshark, credentials, capabilities, linpeas | [writeup](https://0xdf.gitlab.io/2021/10/02/htb-cap.html) |
| 88 | **Validation** | Linux | 13 Sep 2021 | uhc, cookies, feroxbuster, burp, burp-repeater, sqli, injection, second-order-sqli | [writeup](https://0xdf.gitlab.io/2021/09/14/htb-validation.html) |
| 89 | **Knife** | Linux | 22 May 2021 | php-backdoor, feroxbuster, php-8.1.0-dev, sudo, knife, gtfobins, vim, oscp-like-v2 | [writeup](https://0xdf.gitlab.io/2021/08/28/htb-knife.html) |
| 90 | **Love** | Windows | 01 May 2021 | vhosts, voting-system, searchsploit, feroxbuster, ssrf, burp, webshell, upload | [writeup](https://0xdf.gitlab.io/2021/08/07/htb-love.html) |
| 91 | **Armageddon** | Linux | 27 Mar 2021 | ubuntu, drupal, drupalgeddon2, searchsploit, webshell, upload, hashcat, mysql | [writeup](https://0xdf.gitlab.io/2021/07/24/htb-armageddon.html) |
| 92 | **Spectra** | Chrome | 27 Feb 2021 | chromeos, nano, wordpress, wpscan, wordpress-plugin, credentials, password-reuse, autologon-credentials | [writeup](https://0xdf.gitlab.io/2021/06/26/htb-spectra.html) |
| 93 | **ScriptKiddie** | Linux | 06 Feb 2021 | searchsploit, msfvenom, cve-2020-7384, msfconsole, command-injection, injection, incron, irb | [writeup](https://0xdf.gitlab.io/2021/06/05/htb-scriptkiddie.html) |
| 94 | **Shocker** | Linux | 30 Sep 2017 | feroxbuster, cgi, shellshock, bashbug, burp, cve-2014-6271, gtfobin, oscp-like-v1 | [writeup](https://0xdf.gitlab.io/2021/05/25/htb-shocker.html) |
| 95 | **Delivery** | Linux | 09 Jan 2021 | vhosts, osticket, mattermost, password-reuse, mysql, hashcat, hashcat-rules, oscp-like-v2 | [writeup](https://0xdf.gitlab.io/2021/05/22/htb-delivery.html) |
| 96 | **Blue** | Windows | 28 Jul 2017 | nmap-scripts, smbmap, smbclient, metasploit, ms17-010, eternalblue, meterpreter, impacket | [writeup](https://0xdf.gitlab.io/2021/05/11/htb-blue.html) |
| 97 | **Toolbox** | Windows | 12 Apr 2021 | windows, wfuzz, docker-toolbox, sqli, injection, postgresql, sqlmap, default-creds | [writeup](https://0xdf.gitlab.io/2021/04/27/htb-toolbox.html) |
| 98 | **Laboratory** | Linux | 14 Nov 2020 | gitlab, vhosts, gobuster, searchsploit, cve-2020-10977, deserialization, hackerone, docker | [writeup](https://0xdf.gitlab.io/2021/04/17/htb-laboratory.html) |
| 99 | **Luanne** | NetBSD | 28 Nov 2020 | netbsd, supervisor-process-manager, default-creds, http-basic-auth, burp, feroxbuster, api, lua | [writeup](https://0xdf.gitlab.io/2021/03/27/htb-luanne.html) |
| 100 | **Optimum** | Windows | 18 Mar 2017 | windows, httpfileserver, hfs, searchsploit, cve-2014-6287, nishang, winpeas, watson | [writeup](https://0xdf.gitlab.io/2021/03/17/htb-optimum.html) |
| 101 | **Sense** | FreeBSD | 21 Oct 2017 | pfsense, gobuster, dirbuster, searchsploit, metasploit, command-injection, feroxbuster, cve-2016-10709 | [writeup](https://0xdf.gitlab.io/2021/03/11/htb-sense.html) |
| 102 | **Academy** | Linux | 07 Nov 2020 | ubuntu, php, laravel, vhosts, gobuster, cve-2018-15133, deserialization, metasploit | [writeup](https://0xdf.gitlab.io/2021/02/27/htb-academy.html) |
| 103 | **Beep** | Linux | 15 Mar 2017 | elastix, pbx, dirsearch, searchsploit, lfi, webmin, smtp, svwar | [writeup](https://0xdf.gitlab.io/2021/02/23/htb-beep.html) |
| 104 | **Doctor** | Linux | 26 Sep 2020 | splunk, vhosts, flask, payloadsallthethings, ssti, command-injection, injection, adm | [writeup](https://0xdf.gitlab.io/2021/02/06/htb-doctor.html) |
| 105 | **Omni** | Windows | 22 Aug 2020 | windows-iot-core, sirep, sireprat, powershell-credential, secretsdump, penglab, hashcat, chisel | [writeup](https://0xdf.gitlab.io/2021/01/09/htb-omni.html) |
| 106 | **Buff** | Windows | 18 Jul 2020 | windows, gobuster, gym-management-system, searchsploit, cloudme, chisel, msfvenom, webshell | [writeup](https://0xdf.gitlab.io/2020/11/21/htb-buff.html) |
| 107 | **Tabby** | Linux | 20 Jun 2020 | lfi, php, gobuster, tomcat, host-manager, tomcat-manager, war, msfvenom | [writeup](https://0xdf.gitlab.io/2020/11/07/htb-tabby.html) |
| 108 | **Blunder** | Linux | 30 May 2020 | ubuntu, bludit, cms, searchsploit, github, cewl, bruteforce, python | [writeup](https://0xdf.gitlab.io/2020/10/17/htb-blunder.html) |
| 109 | **Admirer** | Linux | 02 May 2020 | debian, gobuster, robots-text, source-code, adminer, mysql, credentials, sudo | [writeup](https://0xdf.gitlab.io/2020/09/26/htb-admirer.html) |
| 110 | **Remote** | Windows | 21 Mar 2020 | nfs, umbraco, hashcat, nishang, teamviewer, credentials, evil-winrm, oscp-like-v2 | [writeup](https://0xdf.gitlab.io/2020/09/05/htb-remote.html) |
| 111 | **Traceback** | Linux | 14 Mar 2020 | webshell, vim, gobuster, smevk, lua, luvit, ssh, motd | [writeup](https://0xdf.gitlab.io/2020/08/15/htb-traceback.html) |
| 112 | **Sauna** | Windows | 15 Feb 2020 | windows, ldapsearch, ldap, kerberos, seclists, as-rep-roast, getnpusers, hashcat | [writeup](https://0xdf.gitlab.io/2020/07/18/htb-sauna.html) |
| 113 | **Bank** | Linux | 16 Jun 2017 | vhosts, dns, dig, zone-transfer, wfuzz, gobuster, burp, regex | [writeup](https://0xdf.gitlab.io/2020/07/07/htb-bank.html) |
| 114 | **Blocky** | Linux | 21 Jul 2017 | wordpress, java, java-jar, decompile, jd-gui, phpmyadmin, wpscan, ssh | [writeup](https://0xdf.gitlab.io/2020/06/30/htb-blocky.html) |
| 115 | **ServMon** | Windows | 11 Apr 2020 | windows, ftp, nvms-1000, gobuster, wfuzz, searchsploit, directory-traversal, lfi | [writeup](https://0xdf.gitlab.io/2020/06/20/htb-servmon.html) |
| 116 | **Nest** | Windows | 25 Jan 2020 | smb, smbmap, smbclient, crypto, vb, visual-studio, dnspy, dotnetfiddle | [writeup](https://0xdf.gitlab.io/2020/06/06/htb-nest.html) |
| 117 | **Grandpa** | Windows | 12 Apr 2017 | windows-2003, iis, gobuster, webdav, davtest, searchsploit, msfvenom, cve-2017-7269 | [writeup](https://0xdf.gitlab.io/2020/05/28/htb-grandpa.html) |
| 118 | **Arctic** | Windows | 22 Mar 2017 | coldfusion, javascript, searchsploit, jsp, upload, metasploit, directory-traversal, crackstation | [writeup](https://0xdf.gitlab.io/2020/05/19/htb-arctic.html) |
| 119 | **OpenAdmin** | Linux | 04 Jan 2020 | gobuster, opennetadmin, searchsploit, password-reuse, webshell, ssh, john, sudo | [writeup](https://0xdf.gitlab.io/2020/05/02/htb-openadmin.html) |
| 120 | **Traverxec** | Linux | 16 Nov 2019 | nostromo, searchsploit, metasploit, htpasswd, hashcat, ssh, john, gtfobins | [writeup](https://0xdf.gitlab.io/2020/04/11/htb-traverxec.html) |
| 121 | **Lame** | Linux | 14 Mar 2017 | ftp, vsftpd, samba, searchsploit, exploit, metasploit, oscp-like-v1 | [writeup](https://0xdf.gitlab.io/2020/04/07/htb-lame.html) |
| 122 | **Forest** | Windows | 12 Oct 2019 | active-directory, dig, dns, rpc, rpcclient, as-rep-roast, hashcat, winrm | [writeup](https://0xdf.gitlab.io/2020/03/21/htb-forest.html) |
| 123 | **Postman** | Linux | 02 Nov 2019 | webmin, redis, ssh, john, credentials, cve-2019-12840, metasploit, oscp-like-v2 | [writeup](https://0xdf.gitlab.io/2020/03/14/htb-postman.html) |
| 124 | **Heist** | Windows | 10 Aug 2019 | cisco, john, cisco-type-7, smbclient, smbmap, crackmapexec, rpcclient, ipc | [writeup](https://0xdf.gitlab.io/2019/11/30/htb-heist.html) |
| 125 | **Networked** | Linux | 24 Aug 2019 | apache, dirsearch, php, upload, webshell, filter, command-injection, sudo | [writeup](https://0xdf.gitlab.io/2019/11/16/htb-networked.html) |
| 126 | **Haystack** | Linux | 29 Jun 2019 | gobuster, steganography, elasticsearch, ssh, kibana, cve-2018-17246, javascript, lfi | [writeup](https://0xdf.gitlab.io/2019/11/02/htb-haystack.html) |
| 127 | **Safe** | Linux | 27 Jul 2019 | rop, pwntools, bof, python, exploit, keepass, kpcli, john | [writeup](https://0xdf.gitlab.io/2019/10/26/htb-safe.html) |
| 128 | **Writeup** | Linux | 08 Jun 2019 | robots-txt, cmsms, sqli, credentials, injection, pspy, run-parts, perl | [writeup](https://0xdf.gitlab.io/2019/10/12/htb-writeup.html) |
| 129 | **SwagShop** | Linux | 11 May 2019 | magento, gobuster, deserialization, webshell, sudo, oscp-like-v2, oscp-like-v1 | [writeup](https://0xdf.gitlab.io/2019/09/28/htb-swagshop.html) |
| 130 | **Bastion** | Windows | 27 Apr 2019 | smbmap, smbclient, smb, vhd, mount, guestmount, secretsdump, crackstation | [writeup](https://0xdf.gitlab.io/2019/09/07/htb-bastion.html) |
| 131 | **LaCasaDePapel** | Linux | 30 Mar 2019 | vsftpd, searchsploit, python, psy, php, php-disable-functions, certificate, client-certificate | [writeup](https://0xdf.gitlab.io/2019/07/27/htb-lacasadepapel.html) |
| 132 | **FriendZone** | Linux | 09 Feb 2019 | smbmap, smbclient, gobuster, zone-transfer, dns, dig, lfi, php | [writeup](https://0xdf.gitlab.io/2019/07/13/htb-friendzone.html) |
| 133 | **Netmon** | Windows | 02 Mar 2019 | ftp, password-reuse, prtg, command-injection, psexec-py, oscp-plus-v1, oscp-plus-v2 | [writeup](https://0xdf.gitlab.io/2019/06/29/htb-netmon.html) |
| 134 | **Help** | Linux | 19 Jan 2019 | graphql, curl, crackstation, gobuster, helpdeskz, searchsploit, exploit-db, sqli | [writeup](https://0xdf.gitlab.io/2019/06/08/htb-help.html) |
| 135 | **Irked** | Linux | 17 Nov 2018 | searchsploit, exploit-db, hexchat, irc, python, steganography, steghide, ssh | [writeup](https://0xdf.gitlab.io/2019/04/27/htb-irked.html) |
| 136 | **Teacher** | Linux | 01 Dec 2018 | debian, stretch, gobuster, skipfish, hydra, python, cve-2018-1133, crackstation | [writeup](https://0xdf.gitlab.io/2019/04/20/htb-teacher.html) |
| 137 | **Curling** | Linux | 27 Oct 2018 | joomla, searchsploit, webshell, cron, pspy, curl, suid, cve-2019-7304 | [writeup](https://0xdf.gitlab.io/2019/03/30/htb-curling.html) |
| 138 | **Frolic** | Linux | 13 Oct 2018 | smbmap, smbclient, node-red, gobuster, php, playsms, javascript, ook! | [writeup](https://0xdf.gitlab.io/2019/03/23/htb-frolic.html) |
| 139 | **Granny** | Windows | 12 Apr 2017 | webdav, aspx, webshell, meterpreter, windows, ms14-058, local-exploit-suggester, pwk | [writeup](https://0xdf.gitlab.io/2019/03/06/htb-granny.html) |
| 140 | **Devel** | Windows | 15 Mar 2017 | webshell, aspx, meterpreter, metasploit, msfvenom, ms11-046, ftp, nishang | [writeup](https://0xdf.gitlab.io/2019/03/05/htb-devel.html) |
| 141 | **Access** | Windows | 29 Sep 2018 | mdbtools, readpst, mutt, telnet, runas, cached-creds, dpapi, mimikatz | [writeup](https://0xdf.gitlab.io/2019/03/02/htb-access.html) |
| 142 | **legacy** | Windows | 15 Mar 2017 | windows, ms08-067, ms17-010, smb, msfvenom, xp, oscp-like-v1 | [writeup](https://0xdf.gitlab.io/2019/02/21/htb-legacy.html) |
| 143 | **Active** | Windows | 28 Jul 2018 | active-directory, gpp, group-policy-preferences, gpp-decrypt, smb, smbmap, smbclient, enum4linux | [writeup](https://0xdf.gitlab.io/2018/12/08/htb-active.html) |
| 144 | **Jerry** | Windows | 30 Jun 2018 | tomcat, war, msfvenom, java-jar, jsp, oscp-like-v2, oscp-like-v1 | [writeup](https://0xdf.gitlab.io/2018/11/17/htb-jerry.html) |
| 145 | **Bounty** | Windows | 16 Jun 2018 | asp, upload, nishang, lonelypotato, potato, meterpreter, ms10-051, ms16-014 | [writeup](https://0xdf.gitlab.io/2018/10/27/htb-bounty.html) |
| 146 | **Sunday** | Solaris | 28 Apr 2018 | finger, hashcat, sudo, wget, shadow, sudoers, gtfobins, arbitrary-write | [writeup](https://0xdf.gitlab.io/2018/09/29/htb-sunday.html) |
| 147 | **Valentine** | Linux | 17 Feb 2018 | heartbleed, tmux, dirtycow, oscp-like-v2, oscp-like-v1 | [writeup](https://0xdf.gitlab.io/2018/07/28/htb-valentine.html) |
| 148 | **Nibbles** | Linux | 13 Jan 2018 | meterpreter, sudo, cve-2015-6967, oscp-like-v2, oscp-like-v1 | [writeup](https://0xdf.gitlab.io/2018/06/30/htb-nibbles.html) |
| 149 | **Bashed** | Linux | 09 Dec 2017 | php, sudo, cron, oscp-like-v1 | [writeup](https://0xdf.gitlab.io/2018/04/29/htb-bashed.html) |

## Medium (178 machines)

| # | Name | OS | Release Date | Key Techniques | URL |
|---|------|----|-----------|----|-----|
| 1 | **Principal** | Linux | 12 Mar 2026 | ubuntu, spring-boot, pac4j, java, javascript, jwt, jwks, feroxbuster | [writeup](https://0xdf.gitlab.io/2026/03/30/htb-principal.html) |
| 2 | **Browsed** | Linux | 10 Jan 2026 | ubuntu, chrome-extension, feroxbuster, gitea, python, flask, javascript, nginx | [writeup](https://0xdf.gitlab.io/2026/03/28/htb-browsed.html) |
| 3 | **Gavel** | Linux | 29 Nov 2025 | ubuntu, php, git-dumper, source-code, idor, sqli, sqli-php, sqli-pdo | [writeup](https://0xdf.gitlab.io/2026/03/14/htb-gavel.html) |
| 4 | **Barrier** | Linux | 12 Feb 2026 | vulnlab, ubuntu, lft, container, gitlab, python, tomcat, feroxbuster | [writeup](https://0xdf.gitlab.io/2026/03/03/htb-barrier.html) |
| 5 | **Bruno** | Windows | 21 Oct 2025 | vulnlab, windows, active-directory, kerberos, iis, asp-dot-net, ffuf, subdomain | [writeup](https://0xdf.gitlab.io/2026/02/24/htb-bruno.html) |
| 6 | **Giveback** | Linux | 01 Nov 2025 | ubuntu, debian, container, kubernetes, wordpress, php, givewp, wpscan | [writeup](https://0xdf.gitlab.io/2026/02/21/htb-giveback.html) |
| 7 | **Slonik** | Linux | 14 Oct 2025 | vulnlab, nfs, showmount, netexec, netexec-nfs, crackstation, postgresql, tunnel | [writeup](https://0xdf.gitlab.io/2026/02/12/htb-slonik.html) |
| 8 | **Breach** | Windows | 09 Oct 2025 | vulnlab, smb, smbclient, netexec, netexec-rid-brute, netexec-spider-plus, netexec-kerberoast, ntlm-theft | [writeup](https://0xdf.gitlab.io/2026/02/10/htb-breach.html) |
| 9 | **Signed** | Windows | 11 Oct 2025 | assume-breach, windows, mssql, netexec, mssqlclient, xp-dirtree, xp-cmdshell, coerce | [writeup](https://0xdf.gitlab.io/2026/02/07/htb-signed.html) |
| 10 | **Bamboo** | Linux | 07 Oct 2025 | vulnlab, ubuntu, squid, proxychains, foxyproxy, burp, papercut, cve-2023-27350 | [writeup](https://0xdf.gitlab.io/2026/02/03/htb-bamboo.html) |
| 11 | **Job** | Windows | 30 Sep 2025 | vulnlab, windows, netexec, smtp, phishing, libreoffice, feroxbuster, macros | [writeup](https://0xdf.gitlab.io/2026/01/26/htb-job.html) |
| 12 | **Imagery** | Linux | 27 Sep 2025 | xss, flask, python, werkzeug, command-injection, directory-traversal, source-code, crackstation | [writeup](https://0xdf.gitlab.io/2026/01/24/htb-imagery.html) |
| 13 | **HackNet** | Linux | 13 Sep 2025 | debian, django, django-pickle, feroxbuster, ffuf, gpg, gunicorn, hashcat | [writeup](https://0xdf.gitlab.io/2026/01/17/htb-hacknet.html) |
| 14 | **Previous** | Linux | 23 Aug 2025 | ubuntu, nginx, feroxbuster, next-js, wappalyzer, javascript, cve-2025-29927, auth-bypass | [writeup](https://0xdf.gitlab.io/2026/01/10/htb-previous.html) |
| 15 | **Era** | Linux | 26 Jul 2025 | ubuntu, ffuf, subdomain, feroxbuster, idor, source-code, php, hashcat | [writeup](https://0xdf.gitlab.io/2025/11/29/htb-era.html) |
| 16 | **Voleur** | Windows | 05 Jul 2025 | assume-breach, netexec-hosts, active-directory, windows, netexec-krb5, smbclient-py, smbclient-kerberos, office2john | [writeup](https://0xdf.gitlab.io/2025/11/01/htb-voleur.html) |
| 17 | **TombWatcher** | Windows | 07 Jun 2025 | assume-breach, netexec, netexec-hosts, windows, active-directory, feroxbuster, bloodhound, rusthound-ce | [writeup](https://0xdf.gitlab.io/2025/10/11/htb-tombwatcher.html) |
| 18 | **Watcher** | Linux | 02 Oct 2025 | vulnlab, subdomain, ffuf, ubuntu, zabbix, feroxbuster, cve-2024-22120, sqli | [writeup](https://0xdf.gitlab.io/2025/10/09/htb-watcher.html) |
| 19 | **Puppy** | Windows | 17 May 2025 | assume-breach, windows, active-directory, netexec, bloodhound, bloodhound-python, genericwrite, net-rpc | [writeup](https://0xdf.gitlab.io/2025/09/27/htb-puppy.html) |
| 20 | **BabyTwo** | Windows | 25 Sep 2025 | vulnlab, windows, active-directory, netexec, netexec-hosts, smb, netexec-spider-plus, lnk | [writeup](https://0xdf.gitlab.io/2025/09/26/htb-babytwo.html) |
| 21 | **Delegate** | Windows | 11 Sep 2025 | vulnlab, windows, active-directory, netexec, netexec-rid-brute, rid-cycle, credentials, bloodhound | [writeup](https://0xdf.gitlab.io/2025/09/12/htb-delegate.html) |
| 22 | **Environment** | Linux | 03 May 2025 | debian, nginx, laravel, php, feroxbuster, laravel-debug, cve-2024-52301, burp | [writeup](https://0xdf.gitlab.io/2025/09/06/htb-environment.html) |
| 23 | **Media** | Windows | 04 Sep 2025 | vulnlab, windows, feroxbuster, apache, xampp, net-ntlmv2, responder, wax | [writeup](https://0xdf.gitlab.io/2025/09/04/htb-media.html) |
| 24 | **Sendai** | Windows | 28 Aug 2025 | vulnlab, windows, netexec, netexec-hosts, rid-cycle, netexec-rid-brute, password-spray, netexec-change-password | [writeup](https://0xdf.gitlab.io/2025/08/28/htb-sendai.html) |
| 25 | **TheFrizz** | Windows | 15 Mar 2025 | windows, active-directory, domain-controller, netexec, netexec-hosts, gibbon, ferobxbuster, cve-2023-45878 | [writeup](https://0xdf.gitlab.io/2025/08/23/htb-thefrizz.html) |
| 26 | **Phantom** | Windows | 19 Aug 2025 | vulnlab, netexec, netexec-hosts, email-attachment, rid-cycle, netexec-rid-brute, password-spray, kerbrute | [writeup](https://0xdf.gitlab.io/2025/08/19/htb-phantom.html) |
| 27 | **Rainbow** | Windows | 07 Aug 2025 | vulnlab, windows, feroxbuster, burp-proxy, bof, binary-exploitation, x32dbg, x64dbg | [writeup](https://0xdf.gitlab.io/2025/08/07/htb-rainbow.html) |
| 28 | **Build** | Linux | 05 Aug 2025 | vulnlab, ubuntu, lft, gitea, rsync, jenkins, hashcat, jenkins-credentials-decryptor | [writeup](https://0xdf.gitlab.io/2025/08/05/htb-build.html) |
| 29 | **Cypher** | Linux | 01 Mar 2025 | ubuntu, wappalyzer, feroxbuster, java, java-jar, jadx-gui, command-injection, cypher-injection | [writeup](https://0xdf.gitlab.io/2025/07/26/htb-cypher.html) |
| 30 | **Cat** | Linux | 01 Feb 2025 | ubuntu, feroxbuster, php, source-code, git, git-dumper, xss, html-injection | [writeup](https://0xdf.gitlab.io/2025/07/05/htb-cat.html) |
| 31 | **VulnCicada** | Windows | 03 Jul 2025 | vulnlab, windows, active-directory, feroxbuster, netexec, nfs, certenroll, adcs | [writeup](https://0xdf.gitlab.io/2025/07/03/htb-vulncicada.html) |
| 32 | **Backfire** | Linux | 18 Jan 2025 | debian, havoc, cve-2024-41570, ssrf, ssrf-websocket, chatgpt, hardhatc2, docker | [writeup](https://0xdf.gitlab.io/2025/06/07/htb-backfire.html) |
| 33 | **Heal** | Linux | 14 Dec 2024 | ubuntu, ffuf, subdomain, wkhtmltopdf, exiftool, feroxbuster, ruby, ruby-on-rails | [writeup](https://0xdf.gitlab.io/2025/05/17/htb-heal.html) |
| 34 | **Administrator** | Windows | 09 Nov 2024 | assume-breach, active-directory, netexec, evil-winrm, bloodhound, bloodhound-python, bloodhound-ce, genericall | [writeup](https://0xdf.gitlab.io/2025/04/19/htb-administrator.html) |
| 35 | **Certified** | Windows | 02 Nov 2024 | assume-breach, netexec, bloodhound, bloodhound-ce, bloodhound-python, writeowner, adcs, oweredit-py | [writeup](https://0xdf.gitlab.io/2025/03/15/htb-certified.html) |
| 36 | **Unrested** | Linux | 05 Dec 2024 | assume-breach, zabbix, burp, burp-repeater, cve-2024-42327, sqli, cve-2024-36467 | [writeup](https://0xdf.gitlab.io/2025/03/04/htb-unrested.html) |
| 37 | **Instant** | Linux | 12 Oct 2024 | apk, android, feroxbuster, appetize, android-emulation, jadx-gui, subdomain, jwt | [writeup](https://0xdf.gitlab.io/2025/03/01/htb-instant.html) |
| 38 | **Trickster** | Linux | 21 Sep 2024 | subdomain, ffuf, modsecurity, burp, burp-repeater, weppalyzer, git, git-dumper | [writeup](https://0xdf.gitlab.io/2025/02/01/htb-trickster.html) |
| 39 | **Strutted** | Linux | 23 Jan 2025 | upload, java, struts, docker, dockerfile, tomcat, cve-2024-53677, burp | [writeup](https://0xdf.gitlab.io/2025/01/28/htb-strutted.html) |
| 40 | **MonitorsThree** | Linux | 24 Aug 2024 | ffuf, subdomain, feroxbuster, cacti, sqli, sqlmap, crackstation, cve-2024-25642 | [writeup](https://0xdf.gitlab.io/2025/01/18/htb-monitorsthree.html) |
| 41 | **Compiled** | Windows | 27 Jul 2024 | cpp, csharp, git, gitea, flask, python, cve-2024-32002, git-hooks | [writeup](https://0xdf.gitlab.io/2024/12/14/htb-compiled.html) |
| 42 | **Blurry** | Linux | 08 Jun 2024 | debian, ffuf, subdomain, rocket-chat, feroxbuster, clearml, python, cve-2024-24590 | [writeup](https://0xdf.gitlab.io/2024/10/12/htb-blurry.html) |
| 43 | **EvilCUPS** | Linux | 02 Oct 2024 | debian, cups, cve-2024-47176, cve-2024-47076, cve-2024-47175, cve-2024-47177, print-jobs | [writeup](https://0xdf.gitlab.io/2024/10/02/htb-evilcups.html) |
| 44 | **SolarLab** | Windows | 11 May 2024 | windows, flask, feroxbuster, netexec, password-spray, ffuf, reportlab, cve-2023-33733 | [writeup](https://0xdf.gitlab.io/2024/09/21/htb-solarlab.html) |
| 45 | **Runner** | Linux | 20 Apr 2024 | ffuf, subdomain, teamcity, ubuntu, feroxbuster, cve-2023-42793, authentication-bypass, docker | [writeup](https://0xdf.gitlab.io/2024/08/24/htb-runner.html) |
| 46 | **IClean** | Linux | 06 Apr 2024 | ubuntu, flask, feroxbuster, burp, burp-repeater, xss, ssti, crackstation | [writeup](https://0xdf.gitlab.io/2024/08/03/htb-iclean.html) |
| 47 | **WifineticTwo** | Linux | 16 Mar 2024 | ubuntu, openplc, c, flask, flask-unsign, cve-2021-31630, c-reverse-shell, wifi | [writeup](https://0xdf.gitlab.io/2024/07/27/htb-wifinetictwo.html) |
| 48 | **Jab** | Windows | 24 Feb 2024 | windows, jabber, xmpp, openfire, netexec, pidgin, xmpp-console, as-rep-roast | [writeup](https://0xdf.gitlab.io/2024/06/29/htb-jab.html) |
| 49 | **Pov** | Windows | 27 Jan 2024 | subdomain, ffuf, aspx, feroxbuster, viewstate, file-read, directory-traversal, deserialization | [writeup](https://0xdf.gitlab.io/2024/06/08/htb-pov.html) |
| 50 | **Monitored** | Linux | 13 Jan 2024 | nagios, nagiosxi, ldapsearch, snmpwalk, nagios-api, api-fuzz, feroxbuster, burp | [writeup](https://0xdf.gitlab.io/2024/05/11/htb-monitored.html) |
| 51 | **Surveillance** | Linux | 09 Dec 2023 | ubuntu, feroxbuster, craftcms, cve-2023-41892, arbitrary-object-instantiation, image-magick, hashcat, zoneminder | [writeup](https://0xdf.gitlab.io/2024/04/20/htb-surveillance.html) |
| 52 | **Hospital** | Windows | 18 Nov 2023 | windows, ubuntu, netexec, roundcube, upload, feroxbuster, ffuf, burp | [writeup](https://0xdf.gitlab.io/2024/04/13/htb-hospital.html) |
| 53 | **Manager** | Windows | 21 Oct 2023 | windows, ffuf, iis, feroxbuster, netexec, lookupsid, rid-cycle, ldapsearch | [writeup](https://0xdf.gitlab.io/2024/03/16/htb-manager.html) |
| 54 | **Visual** | Windows | 30 Sep 2023 | windows, php, xampp, feroxbuster, visual-studio, csharp, gitea, docker | [writeup](https://0xdf.gitlab.io/2024/02/24/htb-visual.html) |
| 55 | **Builder** | Linux | 12 Feb 2024 | cve-2024-23897, file-read, jenkins, jenkins-cli, youtube, hashcat, bcrypt, jenkins-credentials | [writeup](https://0xdf.gitlab.io/2024/02/12/htb-builder.html) |
| 56 | **Clicker** | Linux | 23 Sep 2023 | ubuntu, ffuf, php, feroxbuster, nfs, source-code, mass-assignment, newline-injection | [writeup](https://0xdf.gitlab.io/2024/01/27/htb-clicker.html) |
| 57 | **Zipping** | Linux | 26 Aug 2023 | ubuntu, php, feroxbuster, zip, file-read, symlink, youtube, python | [writeup](https://0xdf.gitlab.io/2024/01/13/htb-zipping.html) |
| 58 | **Authority** | Windows | 15 Jul 2023 | windows, iis, smb, netexec, smbclient, dig, dns, feroxbuster | [writeup](https://0xdf.gitlab.io/2023/12/09/htb-authority.html) |
| 59 | **Sandworm** | Linux | 17 Jun 2023 | ubuntu, gpg, pgp, feroxbuster, python, flask, ssti, crypto | [writeup](https://0xdf.gitlab.io/2023/11/18/htb-sandworm.html) |
| 60 | **Jupiter** | Linux | 03 Jun 2023 | ffuf, feroxbuster, grafana, postgresql, cve-2019-9193, burp, burp-repeater, pspy | [writeup](https://0xdf.gitlab.io/2023/10/21/htb-jupiter.html) |
| 61 | **Format** | Linux | 13 May 2023 | ffuf, subdomain, debian, feroxbuster, gitea, source-code, php, file-read | [writeup](https://0xdf.gitlab.io/2023/09/30/htb-format.html) |
| 62 | **Aero** | Windows | 28 Sep 2023 | windows, windows11, iis-arr, feroxbuster, themebleed, cve-2023-38146, msstyles, dll | [writeup](https://0xdf.gitlab.io/2023/09/28/htb-aero.html) |
| 63 | **OnlyForYou** | Linux | 22 Apr 2023 | ffuf, subdomain, flask, ubuntu, source-code, file-read, directory-traversal, burp | [writeup](https://0xdf.gitlab.io/2023/08/26/htb-onlyforyou.html) |
| 64 | **Agile** | Linux | 04 Mar 2023 | ubuntu, flask, python, feroxbuster, file-read, werkzeug, werkzeug-debug, flask-debug-pin | [writeup](https://0xdf.gitlab.io/2023/08/05/htb-agile.html) |
| 65 | **Socket** | Linux | 25 Mar 2023 | ffuf, qrcode, python, ubuntu, flask, websocket, python-websockets, pyinstaller | [writeup](https://0xdf.gitlab.io/2023/07/15/htb-socket.html) |
| 66 | **Escape** | Windows | 25 Feb 2023 | crackmapexec, windows, smbclient, mssql, mssqlclient, xp-cmdshell, responder, net-ntlmv2 | [writeup](https://0xdf.gitlab.io/2023/06/17/htb-escape.html) |
| 67 | **Bagel** | Linux | 18 Feb 2023 | python, flask, source-code, file-read, dotnet, websocket, ffuf, reverse-engineering | [writeup](https://0xdf.gitlab.io/2023/06/03/htb-bagel.html) |
| 68 | **Interface** | Linux | 11 Feb 2023 | ubuntu, next-js, feroxbuster, subdomain, api, ffuf, dompdf, php | [writeup](https://0xdf.gitlab.io/2023/05/13/htb-interface.html) |
| 69 | **Investigation** | Linux | 21 Jan 2023 | php, exiftool, feroxbuster, cve-2022-23935, command-injection, youtube, perl, open-injection | [writeup](https://0xdf.gitlab.io/2023/04/22/htb-investigation.html) |
| 70 | **Encoding** | Linux | 28 Jan 2023 | php, file-read, lfi, feroxbuster, wfuzz, subdomain, ssrf, filter | [writeup](https://0xdf.gitlab.io/2023/04/15/htb-encoding.html) |
| 71 | **BroScience** | Linux | 07 Jan 2023 | php, feroxbuster, file-read, directory-traversal, filter, wfuzz, dotdotpwn, psql | [writeup](https://0xdf.gitlab.io/2023/04/08/htb-broscience.html) |
| 72 | **Mentor** | Linux | 10 Dec 2022 | youtube, snmp, fastapi, flask, feroxbuster, snmp-brute, onesixtyone, snmpwalk | [writeup](https://0xdf.gitlab.io/2023/03/11/htb-mentor.html) |
| 73 | **Forgot** | Linux | 12 Nov 2022 | flask, burp, burp-proxy, varnish, cache, cache-abuse, web-cache-deception, feroxbuster | [writeup](https://0xdf.gitlab.io/2023/03/04/htb-forgot.html) |
| 74 | **Awkward** | Linux | 22 Oct 2022 | webpack, vuejs, wfuzz, auth-bypass, jwt, jwt-io, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2023/02/25/htb-awkward.html) |
| 75 | **Ambassador** | Linux | 01 Oct 2022 | feroxbuster, grafana, searchsploit, cve-2021-43798, file-read, directory-traversal, consul, msfconsole | [writeup](https://0xdf.gitlab.io/2023/01/28/htb-ambassador.html) |
| 76 | **UpDown** | Linux | 03 Sep 2022 | ssrf, feroxbuster, wfuzz, subdomain, git, git-dumper, source-code, php | [writeup](https://0xdf.gitlab.io/2023/01/21/htb-updown.html) |
| 77 | **Health** | Linux | 20 Aug 2022 | feroxbuster, laravel, redirect, hook, gogs, ssrf, python, flask | [writeup](https://0xdf.gitlab.io/2023/01/07/htb-health.html) |
| 78 | **Outdated** | Windows | 13 Aug 2022 | windows, domain-controller, crackmapexec, smbclient, cve-2022-30190, folina, swaks, phishing | [writeup](https://0xdf.gitlab.io/2022/12/10/htb-outdated.html) |
| 79 | **Shared** | Linux | 23 Jul 2022 | wfuzz, sqli, sqli-union, sqlmap, burp, burp-repeater, crackstation, pspy | [writeup](https://0xdf.gitlab.io/2022/11/12/htb-shared.html) |
| 80 | **Faculty** | Linux | 02 Jul 2022 | php, feroxbuster, sqli, sqli-bypass, auth-bypass, sqlmap, mpdf, cyberchef | [writeup](https://0xdf.gitlab.io/2022/10/22/htb-faculty.html) |
| 81 | **Scrambled** | Windows | 11 Jun 2022 | kerberos, deserialization, windows, silver-ticket, reverse-engineering, mssql, oscp-like-v2, osep-like | [writeup](https://0xdf.gitlab.io/2022/10/01/htb-scrambled.html) |
| 82 | **StreamIO** | Windows | 04 Jun 2022 | windows, domain-controller, php, wfuzz, vhosts, crackmapexec, feroxbuster, sqli | [writeup](https://0xdf.gitlab.io/2022/09/17/htb-streamio.html) |
| 83 | **Noter** | Linux | 07 May 2022 | ftp, python, flask, flask-cookie, flask-unsign, feroxbuster, wfuzz, source-code | [writeup](https://0xdf.gitlab.io/2022/09/03/htb-noter.html) |
| 84 | **Retired** | Linux | 02 Apr 2022 | feroxbuster, upload, directory-traversal, file-read, filter, bof, wfuzz, ghidra | [writeup](https://0xdf.gitlab.io/2022/08/13/htb-retired.html) |
| 85 | **Catch** | Linux | 12 Mar 2022 | apk, android, feroxbuster, gitea, swagger, lets-chat, cachet, jadx | [writeup](https://0xdf.gitlab.io/2022/07/23/htb-catch.html) |
| 86 | **Undetected** | Linux | 19 Feb 2022 | feroxbuster, php, wfuzz, vhosts, composer, phpunit, cve-2017-9841, webshell | [writeup](https://0xdf.gitlab.io/2022/07/02/htb-undetected.html) |
| 87 | **Meta** | Linux | 22 Jan 2022 | wfuzz, vhosts, feroxbuster, exiftool, composer, cve-2021-22204, command-injection, pspy | [writeup](https://0xdf.gitlab.io/2022/06/11/htb-meta.html) |
| 88 | **Timing** | Linux | 11 Dec 2021 | php, feroxbuster, wfuzz, lfi, directory-traversal, source-code, side-channel, timing | [writeup](https://0xdf.gitlab.io/2022/06/04/htb-timing.html) |
| 89 | **Unicode** | Linux | 27 Nov 2021 | flask, python, jwt-io, feroxbuster, jwt-rsa, open-redirect, filter, waf | [writeup](https://0xdf.gitlab.io/2022/05/07/htb-unicode.html) |
| 90 | **BackendTwo** | Linux | 02 May 2022 | uhc, uvicorn, python, api, json, jq, wfuzz, feroxbuster | [writeup](https://0xdf.gitlab.io/2022/05/02/htb-backendtwo.html) |
| 91 | **Jeeves** | Windows | 11 Nov 2017 | windows, feroxbuster, gobuster, jetty, jenkins, keepass, kpcli, hashcat | [writeup](https://0xdf.gitlab.io/2022/04/14/htb-jeeves.html) |
| 92 | **Backend** | Linux | 12 Apr 2022 | api, json, uvicorn, feroxbuster, wfuzz, swagger, fastapi, python | [writeup](https://0xdf.gitlab.io/2022/04/12/htb-backend.html) |
| 93 | **Inception** | Linux | 02 Dec 2017 | dompdf, feroxbuster, squid, proxychains, wfuzz, container, lxd, php-filter | [writeup](https://0xdf.gitlab.io/2022/04/04/htb-inception.html) |
| 94 | **Shibboleth** | Linux | 13 Nov 2021 | vhosts, wfuzz, feroxbuster, zabbix, ipmi, msfconsole, msfvenom, shared-object | [writeup](https://0xdf.gitlab.io/2022/04/02/htb-shibboleth.html) |
| 95 | **Ransom** | Linux | 15 Mar 2022 | uhc, type-juggling, ubuntu, php, laravel, feroxbuster, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2022/03/15/htb-ransom.html) |
| 96 | **Devzat** | Linux | 16 Oct 2021 | ubuntu, vhosts, wfuzz, devzat, feroxbuster, golang, git, source-code | [writeup](https://0xdf.gitlab.io/2022/03/12/htb-devzat.html) |
| 97 | **Epsilon** | Linux | 07 Feb 2022 | feroxbuster, git, git-dumper, source-code, flask, python, aws, awscli | [writeup](https://0xdf.gitlab.io/2022/03/10/htb-epsilon.html) |
| 98 | **Bolt** | Linux | 25 Sep 2021 | youtube, vhosts, wfuzz, ffuf, docker, docker-tar, feroxbuster, roundcube | [writeup](https://0xdf.gitlab.io/2022/02/19/htb-bolt.html) |
| 99 | **Flustered** | Linux | 31 Jan 2022 | uni-ctf, feroxbuster, wfuzz, vhosts, squid, glusterfs, mysql, foxyproxy | [writeup](https://0xdf.gitlab.io/2022/02/09/htb-flustered.html) |
| 100 | **Forge** | Linux | 11 Sep 2021 | wfuzz, ssrf, feroxbuster, vhosts, filter, redirection, flask, python | [writeup](https://0xdf.gitlab.io/2022/01/22/htb-forge.html) |
| 101 | **LogForge** | Linux | 23 Dec 2021 | uhc, jsp, jsessionid, tomcat, feroxbuster, apache-tomcat-parse, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2021/12/29/htb-logforge.html) |
| 102 | **Writer** | Linux | 31 Jul 2021 | feroxbuster, sqli, injection, auth-bypass, ffuf, sqlmap, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2021/12/11/htb-writer.html) |
| 103 | **Intelligence** | Windows | 03 Jul 2021 | windows, crackmapexec, smbmap, smbclient, smb, dns, dnsenum, ldapsearch | [writeup](https://0xdf.gitlab.io/2021/11/27/htb-intelligence.html) |
| 104 | **Union** | Linux | 22 Nov 2021 | uhc, sqli, filter, waf, feroxbuster, burp, burp-repeater, sqli-file | [writeup](https://0xdf.gitlab.io/2021/11/22/htb-union.html) |
| 105 | **Seal** | Linux | 10 Jul 2021 | wfuzz, vhosts, nginx, tomcat, feroxbuster, gitbucket, off-by-slash, git | [writeup](https://0xdf.gitlab.io/2021/11/13/htb-seal.html) |
| 106 | **Dynstr** | Linux | 12 Jun 2021 | dynamic-dns, no-ip, feroxbuster, dnsenum, command-injection, injection, cyberchef, scriptreplay | [writeup](https://0xdf.gitlab.io/2021/10/16/htb-dynstr.html) |
| 107 | **Jarmis** | Linux | 27 Sep 2021 | ja3, ja3s, jarm, tls, vhosts, ncat, feroxbuster, fastapi | [writeup](https://0xdf.gitlab.io/2021/09/27/htb-jarmis.html) |
| 108 | **Pit** | Linux | 15 May 2021 | centos, udp, snmp, feroxbuster, snmpwalk, seeddms, cve-2019-12744, exploit-db | [writeup](https://0xdf.gitlab.io/2021/09/25/htb-pit.html) |
| 109 | **Schooled** | FreeBSD | 03 Apr 2021 | moodle, feroxbuster, wfuzz, vhosts, cve-2020-25627, cve-2020-14321, moodle-plugin, webshell | [writeup](https://0xdf.gitlab.io/2021/09/11/htb-schooled.html) |
| 110 | **Gobox** | Linux | 30 Aug 2021 | uhc, ubuntu, golang, ssti, feroxbuster, youtube, python, python-cmd | [writeup](https://0xdf.gitlab.io/2021/08/30/htb-gobox.html) |
| 111 | **TheNotebook** | Linux | 06 Mar 2021 | feroxbuster, jwt, jwt-io, upload, webshell, cve-2019-5736, runc, docker | [writeup](https://0xdf.gitlab.io/2021/07/31/htb-thenotebook.html) |
| 112 | **Atom** | Windows | 17 Apr 2021 | xampp, redis, reverse-engineering, portable-kanban, smbmap, smbclient, crackmapexec, feroxbuster | [writeup](https://0xdf.gitlab.io/2021/07/10/htb-atom.html) |
| 113 | **Ophiuchi** | Linux | 13 Feb 2021 | ubuntu, yaml, tomcat, java, java-jar, deserialization, gobuster, marshalsec | [writeup](https://0xdf.gitlab.io/2021/07/03/htb-ophiuchi.html) |
| 114 | **Enterprise** | Linux | 28 Oct 2017 | docker, ubuntu, debian, wordpress, joomla, wpscan, feroxbuster, wordpress-plugin | [writeup](https://0xdf.gitlab.io/2021/06/16/htb-enterprise.html) |
| 115 | **Tenet** | Linux | 16 Jan 2021 | gobuster, vhosts, wordpress, wpscan, php, deserialization, php-deserialization, webshell | [writeup](https://0xdf.gitlab.io/2021/06/12/htb-tenet.html) |
| 116 | **Node** | Linux | 14 Oct 2017 | express, nodejs, feroxbuster, crackstation, john, source-code, password-reuse, bof | [writeup](https://0xdf.gitlab.io/2021/06/08/htb-node.html) |
| 117 | **Ready** | Linux | 12 Dec 2020 | ubuntu, gitlab, cve-2018-19571, ssrf, cve-2018-19585, crlf-injection, burp, redis | [writeup](https://0xdf.gitlab.io/2021/05/15/htb-ready.html) |
| 118 | **Bucket** | Linux | 17 Oct 2020 | s3, aws, awscli, vhosts, wfuzz, upload, webshell, php | [writeup](https://0xdf.gitlab.io/2021/04/24/htb-bucket.html) |
| 119 | **Time** | Linux | 24 Oct 2020 | cve-2019-12384, java, deserialization, json-deserialization, sql, linpeas, systemd, short-lived-shells | [writeup](https://0xdf.gitlab.io/2021/04/03/htb-time.html) |
| 120 | **Passage** | Linux | 05 Sep 2020 | cutenews, webshell, upload, searchsploit, github, source-code, base64, penglab | [writeup](https://0xdf.gitlab.io/2021/03/06/htb-passage.html) |
| 121 | **Sneaky** | Linux | 14 May 2017 | udp, snmp, mibs, gobuster, sqli, injection, auth-bypass, onesixtyone | [writeup](https://0xdf.gitlab.io/2021/03/02/htb-sneaky.html) |
| 122 | **Jewel** | Linux | 10 Oct 2020 | gitweb, git, ruby, rails, gemfile, cve-2020-8164, cve-2020-8165, irb | [writeup](https://0xdf.gitlab.io/2021/02/13/htb-jewel.html) |
| 123 | **Apocalyst** | Linux | 18 Aug 2017 | wordpress, wpscan, gobuster, wfuzz, steghide, passwd | [writeup](https://0xdf.gitlab.io/2021/02/09/htb-apocalyst.html) |
| 124 | **Europa** | Linux | 23 Jun 2017 | vhosts, wfuzz, sqli, injection, sqlmap, preg-replace, cron | [writeup](https://0xdf.gitlab.io/2021/02/02/htb-europa.html) |
| 125 | **Worker** | Windows | 15 Aug 2020 | svn, credentials, password-reuse, vhosts, wfuzz, azure, azure-devops, burp | [writeup](https://0xdf.gitlab.io/2021/01/30/htb-worker.html) |
| 126 | **OpenKeyS** | OpenBSD | 25 Jul 2020 | vim, bsd, openbsd, gobuster, php, auth-userokay, cve-2019-19521, cve-2019-19520 | [writeup](https://0xdf.gitlab.io/2020/12/12/htb-openkeys.html) |
| 127 | **SneakyMailer** | Linux | 11 Jul 2020 | wfuzz, vhosts, gobuster, phishing, swaks, imap, smtp, evolution | [writeup](https://0xdf.gitlab.io/2020/11/28/htb-sneakymailer.html) |
| 128 | **Fuse** | Windows | 13 Jun 2020 | windows, ldap, ldapsearch, rpc, smb, winrm, evil-winrm, crackmapexec | [writeup](https://0xdf.gitlab.io/2020/10/31/htb-fuse.html) |
| 129 | **Cache** | Linux | 09 May 2020 | ubuntu, gobuster, vhosts, javascript, credentials, password-reuse, wfuzz, openemr | [writeup](https://0xdf.gitlab.io/2020/10/10/htb-cache.html) |
| 130 | **Haircut** | Linux | 26 May 2017 | php, upload, command-injection, parameter-injection, webshell, gobuster, curl, filter | [writeup](https://0xdf.gitlab.io/2020/09/10/htb-haircut.html) |
| 131 | **Magic** | Linux | 18 Apr 2020 | sqli, injection, upload, filter, gobuster, webshell, php, mysqldump | [writeup](https://0xdf.gitlab.io/2020/08/22/htb-magic.html) |
| 132 | **Lazy** | Linux | 03 May 2017 | ubuntu, php, gobuster, cookies, python, crypto, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2020/07/29/htb-lazy.html) |
| 133 | **Cascade** | Windows | 28 Mar 2020 | rpc, ldap, ldapsearch, smb, tightvnc, vncpwd, evil-winrm, crackmapexec | [writeup](https://0xdf.gitlab.io/2020/07/25/htb-cascade.html) |
| 134 | **Tenten** | Linux | 22 Mar 2017 | wordpress, wpscan, gobuster, wp-job-manager, cve-2015-6668, python, steganography, steghide | [writeup](https://0xdf.gitlab.io/2020/07/14/htb-tenten.html) |
| 135 | **Book** | Linux | 22 Feb 2020 | ubuntu, gobuster, sql-truncation, sql, xss, lfi, pspy, logrotate | [writeup](https://0xdf.gitlab.io/2020/07/11/htb-book.html) |
| 136 | **Popcorn** | Linux | 15 Mar 2017 | ubuntu, karmic, gobuster, torrent-hoster, filter, webshell, php, upload | [writeup](https://0xdf.gitlab.io/2020/06/23/htb-popcorn.html) |
| 137 | **Monteverde** | Windows | 11 Jan 2020 | windows, active-directory, smb, smbclient, smbmap, rpc, rpcclient, crackmapexec | [writeup](https://0xdf.gitlab.io/2020/06/13/htb-monteverde.html) |
| 138 | **Resolute** | Windows | 07 Dec 2019 | smb, smbmap, smbclient, rpcclient, rpc, password-spray, crackmapexec, evil-winrm | [writeup](https://0xdf.gitlab.io/2020/05/30/htb-resolute.html) |
| 139 | **Obscurity** | Linux | 30 Nov 2019 | python, gobuster, dirsearch, wfuzz, python-injection, command-injection, code-analysis, crypto | [writeup](https://0xdf.gitlab.io/2020/05/09/htb-obscurity.html) |
| 140 | **SolidState** | Linux | 08 Sep 2017 | james, pop3, smtp, bash-completion, ssh, rbash, credentials, directory-traversal | [writeup](https://0xdf.gitlab.io/2020/04/30/htb-solidstate.html) |
| 141 | **Nineveh** | Linux | 04 Aug 2017 | vhosts, gobuster, phpinfo, bruteforce, phpliteadmin, sql, sqlite, searchsploit | [writeup](https://0xdf.gitlab.io/2020/04/22/htb-nineveh.html) |
| 142 | **Mango** | Linux | 26 Oct 2019 | certificate, vhosts, wfuzz, nosql, mongo, injection, nosql-injection, python | [writeup](https://0xdf.gitlab.io/2020/04/18/htb-mango.html) |
| 143 | **Cronos** | Linux | 22 Mar 2017 | dns, nslookup, zone-transfer, dig, gobuster, vhosts, laravel, searchsploit | [writeup](https://0xdf.gitlab.io/2020/04/14/htb-cronos.html) |
| 144 | **Sniper** | Windows | 05 Oct 2019 | commando, gobuster, lfi, rfi, wireshark, samba, log-poisoning, powershell | [writeup](https://0xdf.gitlab.io/2020/03/28/htb-sniper.html) |
| 145 | **Json** | Windows | 28 Sep 2019 | commando, deserialization, dotnet, javascript, deobfuscation, jsnice, gobuster, oauth | [writeup](https://0xdf.gitlab.io/2020/02/15/htb-json.html) |
| 146 | **AI** | Linux | 09 Nov 2019 | gobuster, text2speech, flite, sqli, tomcat, jdwp, jdb, jwdp-shellifier | [writeup](https://0xdf.gitlab.io/2020/01/25/htb-ai.html) |
| 147 | **Bitlab** | Linux | 07 Sep 2019 | bookmark, javascript, obfuscation, webshell, git, gitlab, docker, ping-sweep | [writeup](https://0xdf.gitlab.io/2020/01/11/htb-bitlab.html) |
| 148 | **Craft** | Linux | 13 Jul 2019 | gogs, api, wfuzz, flask, python, python-eval, git, ssh | [writeup](https://0xdf.gitlab.io/2020/01/04/htb-craft.html) |
| 149 | **Wall** | Linux | 14 Sep 2019 | gobuster, hydra, centreon, cve-2019-13024, waf, filter, python, uncompyle6 | [writeup](https://0xdf.gitlab.io/2019/12/07/htb-wall.html) |
| 150 | **Jarvis** | Linux | 22 Jun 2019 | waf, gobuster, sqli, injection, sqlmap, phpmyadmin, cve-2018-12613, python | [writeup](https://0xdf.gitlab.io/2019/11/09/htb-jarvis.html) |
| 151 | **Luke** | FreeBSD | 25 May 2019 | gobuster, credentials, api, nodejs, jwt, wfuzz, ajenti, hydra | [writeup](https://0xdf.gitlab.io/2019/09/14/htb-luke.html) |
| 152 | **Unattended** | Linux | 13 Apr 2019 | gobuster, sqli, sqlmap, nginx, nginx-aliases, lfi, session-poisoning, socat | [writeup](https://0xdf.gitlab.io/2019/08/24/htb-unattended.html) |
| 153 | **Arkham** | Windows | 16 Mar 2019 | gobuster, faces, jsf, deserialization, smb, smbclient, smbmap, luks | [writeup](https://0xdf.gitlab.io/2019/08/10/htb-arkham.html) |
| 154 | **Querier** | Windows | 16 Feb 2019 | windows, smb, smbclient, olevba, macros, vba, mssql, mssqlclient | [writeup](https://0xdf.gitlab.io/2019/06/22/htb-querier.html) |
| 155 | **Chaos** | Linux | 15 Dec 2018 | webmin, gobuster, wordpress, wpscan, imap, openssl, roundcube, wfuzz | [writeup](https://0xdf.gitlab.io/2019/05/25/htb-chaos.html) |
| 156 | **Lightweight** | Linux | 08 Dec 2018 | php, linux, centos, ssh, fail2ban, ldap, tcpdump, wireshark | [writeup](https://0xdf.gitlab.io/2019/05/11/htb-lightweight.html) |
| 157 | **RedCross** | Linux | 10 Nov 2018 | ssh, wfuzz, linux, debian, php, cookies, gobuster, xss | [writeup](https://0xdf.gitlab.io/2019/04/13/htb-redcross.html) |
| 158 | **Vault** | Linux | 03 Nov 2018 | gobuster, php, upload, webshell, ssh, credentials, pivot, qemu | [writeup](https://0xdf.gitlab.io/2019/04/06/htb-vault.html) |
| 159 | **October** | Linux | 20 Apr 2017 | webshell, ubuntu, linux, bof, exploit, upload, aslr, aslr-bruteforce | [writeup](https://0xdf.gitlab.io/2019/03/26/htb-october.html) |
| 160 | **Carrier** | Linux | 22 Sep 2018 | injection, command-injection, bgp-hijack, gobuster, snmp, snmpwalk, pivot, container | [writeup](https://0xdf.gitlab.io/2019/03/16/htb-carrier.html) |
| 161 | **Bastard** | Windows | 18 Mar 2017 | web, drupal, drupalgeddon2, drupalgeddon3, droopescan, dirsearch, windows, searchsploit | [writeup](https://0xdf.gitlab.io/2019/03/12/htb-bastard.html) |
| 162 | **giddy** | Windows | 08 Sep 2018 | sqli, sqlmap, winrm, net-ntlmv2, responder, hashcat, unifivideo, defender | [writeup](https://0xdf.gitlab.io/2019/02/16/htb-giddy.html) |
| 163 | **Ypuffy** | OpenBSD | 15 Sep 2018 | ldap, ssh, ssh-keygen, doas, sudo, certificate, certificate-authority, wireshark | [writeup](https://0xdf.gitlab.io/2019/02/09/htb-ypuffy.html) |
| 164 | **SecNotes** | Windows | 25 Aug 2018 | csrf, second-order-sqli, second-order, smb, wsl, bash.exe, winexe, smbclient | [writeup](https://0xdf.gitlab.io/2019/01/19/htb-secnotes.html) |
| 165 | **Waldo** | Linux | 04 Aug 2018 | docker, php, ssh, rbash, capabilities | [writeup](https://0xdf.gitlab.io/2018/12/15/htb-waldo.html) |
| 166 | **Hawk** | Linux | 14 Jul 2018 | drupal, ftp, openssl, openssl-bruteforce, php, credentials, h2, oscp-plus-v1 | [writeup](https://0xdf.gitlab.io/2018/11/30/htb-hawk.html) |
| 167 | **TartarSauce** | Linux | 12 May 2018 | wordpress, wpscan, php, webshell, rfi, sudo, tar, pspy | [writeup](https://0xdf.gitlab.io/2018/10/20/htb-tartarsauce.html) |
| 168 | **DevOops** | Linux | 02 Jun 2018 | xxe, ssh, git, python-pickle, deserialization, rss | [writeup](https://0xdf.gitlab.io/2018/10/13/htb-devoops.html) |
| 169 | **Olympus** | Linux | 21 Apr 2018 | zone-transfer, xdebug, aircrack-ng, 802-11, ssh, port-knocking, docker, cve-2018-15473 | [writeup](https://0xdf.gitlab.io/2018/09/22/htb-olympus.html) |
| 170 | **Canape** | Linux | 14 Apr 2018 | python, python-pickle, deserialization, couchdb, flask, pip, sudo, cve-2017-12635 | [writeup](https://0xdf.gitlab.io/2018/09/15/htb-canape.html) |
| 171 | **Poison** | FreeBSD | 24 Mar 2018 | log-poisoning, lfi, webshell, vnc, oscp-like-v2, oscp-like-v1 | [writeup](https://0xdf.gitlab.io/2018/09/08/htb-poison.html) |
| 172 | **Stratosphere** | Linux | 03 Mar 2018 | python, struts, cve-2017-9805, cve-2017-5638, mkfifo-shell, forward-shell | [writeup](https://0xdf.gitlab.io/2018/09/01/htb-stratosphere.html) |
| 173 | **Celestial** | Linux | 10 Mar 2018 | nodejs, deserialization, pspy, cron, oswe-like | [writeup](https://0xdf.gitlab.io/2018/08/25/htb-celestial.html) |
| 174 | **Silo** | Windows | 17 Mar 2018 | oracle, odat, sqlplus, nishang, aspx, webshell, volatility, pass-the-hash | [writeup](https://0xdf.gitlab.io/2018/08/04/htb-silo.html) |
| 175 | **Aragog** | Linux | 10 Feb 2018 | xxe, ssh, pspy, wordpress, cron | [writeup](https://0xdf.gitlab.io/2018/07/21/htb-aragog.html) |
| 176 | **Bart** | Windows | 24 Feb 2018 | gobuster, wfuzz, cewl, bruteforce, log-poisoning, php, webshell, nishang | [writeup](https://0xdf.gitlab.io/2018/07/15/htb-bart.html) |
| 177 | **Chatterbox** | Windows | 27 Jan 2018 | msfvenom, meterpreter, achat, autorunscript, nishang, oscp-like-v2, oscp-like-v1 | [writeup](https://0xdf.gitlab.io/2018/06/18/htb-chatterbox.html) |
| 178 | **FluxCapacitor** | Linux | 16 Dec 2017 | waf, wfuzz, sudo | [writeup](https://0xdf.gitlab.io/2018/05/12/htb-fluxcapacitor.html) |

## Hard (113 machines)

| # | Name | OS | Release Date | Key Techniques | URL |
|---|------|----|-----------|----|-----|
| 1 | **DarkZero** | Windows | 04 Oct 2025 | mssql, windows, active-directory, netexec, netexec-hosts, assume-breach, bloodhound, netexec-rid-brute | [writeup](https://0xdf.gitlab.io/2026/04/04/htb-darkzero.html) |
| 2 | **Snapped** | Linux | 23 Mar 2026 | ubuntu, nginx, ffuf, subdomain, feroxbuster, nginx-ui, cryptography, cve-2026-27944 | [writeup](https://0xdf.gitlab.io/2026/04/01/htb-snapped.html) |
| 3 | **Guardian** | Linux | 30 Aug 2025 | ubuntu, subdomain, ffuf, feroxbuster, php, idor, gitea, source-code | [writeup](https://0xdf.gitlab.io/2026/02/28/htb-guardian.html) |
| 4 | **JobTwo** | Windows | 06 Nov 2025 | vulnlab, windows, iis, hmailserver, swaks, macro, vba, phishing | [writeup](https://0xdf.gitlab.io/2026/01/27/htb-jobtwo.html) |
| 5 | **Mirage** | Windows | 19 Jul 2025 | netexec-hosts, netexec, nfs, dig, nslookup, nats, wireshark, claude | [writeup](https://0xdf.gitlab.io/2025/11/22/htb-mirage.html) |
| 6 | **RustyKey** | Windows | 28 Jun 2025 | assume-breach, windows, active-directory, netexec, netexec-hosts, netexec-krb5, bloodhound, rusthound-ce | [writeup](https://0xdf.gitlab.io/2025/11/08/htb-rustykey.html) |
| 7 | **Dump** | Linux | 30 Oct 2025 | vulnlab, debian, feroxbuster, wildcard-injection, injection, parameter-injection, ffuf, command-injection | [writeup](https://0xdf.gitlab.io/2025/11/04/htb-dump.html) |
| 8 | **Store** | Linux | 28 Oct 2025 | vulnlab, cyberchef, upload, feroxbuster, xor-encryption, directory-traversal, file-read, node | [writeup](https://0xdf.gitlab.io/2025/10/30/htb-store.html) |
| 9 | **Certificate** | Windows | 31 May 2025 | windows, active-directory, netexec-hosts, upload, feroxbuster, webshell, php, null-byte | [writeup](https://0xdf.gitlab.io/2025/10/04/htb-certificate.html) |
| 10 | **Race** | Linux | 02 Sep 2025 | vulnlab, grav-cms, feroxbuster, phpsysinfo, password-reset, cve-2024-28116, ssti, twig-ssti | [writeup](https://0xdf.gitlab.io/2025/09/02/htb-race.html) |
| 11 | **Eureka** | Linux | 26 Apr 2025 | ubuntu, java, spring-boot, feroxbuster, spring-boot-heapdump, spring-boot-actuator, visualvm, jdumpspider | [writeup](https://0xdf.gitlab.io/2025/08/30/htb-eureka.html) |
| 12 | **LustrousTwo** | Windows | 31 Jul 2025 | vulnlab, netexec, windows, iis, kerberos-web-auth, feroxbuster, kerbrute, password-spray | [writeup](https://0xdf.gitlab.io/2025/07/31/htb-lustroustwo.html) |
| 13 | **Ten** | Linux | 24 Jul 2025 | vulnlab, ubuntu, apache, feroxbuster, ffuf, subdomain, webdb, directory-traversal | [writeup](https://0xdf.gitlab.io/2025/07/24/htb-ten.html) |
| 14 | **Scepter** | Windows | 19 Apr 2025 | windows, active-directory, nfs, showmount, john, hashcat, hashcat-pem, openssl | [writeup](https://0xdf.gitlab.io/2025/07/19/htb-scepter.html) |
| 15 | **Redelegate** | Windows | 17 Jul 2025 | vulnlab, windows, active-directory, feroxbuster, netexec, netexec-bloodhound, keepass, keepass2john | [writeup](https://0xdf.gitlab.io/2025/07/17/htb-redelegate.html) |
| 16 | **Haze** | Windows | 29 Mar 2025 | windows, active-directory, netexec, splunk, splunk-enterprise, cve-2024-36991, directory-traversal, file-read | [writeup](https://0xdf.gitlab.io/2025/06/28/htb-haze.html) |
| 17 | **Shibuya** | Windows | 19 Jun 2025 | vulnlab, netexec, kerbrute, credentials, windows-imaging, wim, secretsdump, crackstation | [writeup](https://0xdf.gitlab.io/2025/06/19/htb-shibuya.html) |
| 18 | **Checker** | Linux | 22 Feb 2025 | ubuntu, bookstack, laravel, teampass, cve-2023-1545, sqli, hashcat, 2fa | [writeup](https://0xdf.gitlab.io/2025/05/31/htb-checker.html) |
| 19 | **BigBang** | Linux | 25 Jan 2025 | subdomain, wordpress, wordpress-buddyforms, wpscan, cve-2023-26326, phar, php, ssrf | [writeup](https://0xdf.gitlab.io/2025/05/03/htb-bigbang.html) |
| 20 | **Vintage** | Windows | 30 Nov 2024 | assume-breach, active-directory, netexec, evil-winrm, bloodhound, bloodhound-python, bloodhound-ce, kerberos | [writeup](https://0xdf.gitlab.io/2025/04/26/htb-vintage.html) |
| 21 | **BlockBlock** | Linux | 16 Nov 2024 | arch, blockchain, solidity, smart-contract, flask, burp, burp-repeater, html-injection | [writeup](https://0xdf.gitlab.io/2025/03/29/htb-blockblock.html) |
| 22 | **Yummy** | Linux | 05 Oct 2024 | ics-py, jwt, rsa, crypto, feroxbuster, burp, burp-repeater, directory-traversal | [writeup](https://0xdf.gitlab.io/2025/02/22/htb-yummy.html) |
| 23 | **Caption** | Linux | 14 Sep 2024 | python, flask, varnish, cache, feroxbuster, gitbucket, thrift, golang | [writeup](https://0xdf.gitlab.io/2025/01/25/htb-caption.html) |
| 24 | **Lantern** | Linux | 17 Aug 2024 | python, flask, dotnet, blazor, blazor-traffic-processor, feroxbuster, ssrf, skipper-proxy | [writeup](https://0xdf.gitlab.io/2024/11/30/htb-lantern.html) |
| 25 | **Resource** | Linux | 03 Aug 2024 | feroxbuster, ssh, ssh-certificate, phar, webshell, har, bash, bash-glob | [writeup](https://0xdf.gitlab.io/2024/11/23/htb-resource.html) |
| 26 | **Axlle** | Windows | 22 Jun 2024 | windows, subdomain, netexec, feroxbuster, xll, phishing, visual-studio, dll | [writeup](https://0xdf.gitlab.io/2024/11/16/htb-axlle.html) |
| 27 | **Blazorized** | Windows | 29 Jun 2024 | windows, ffuf, subdomain, netexec, blazor, dotnet, burp, burp-proxy | [writeup](https://0xdf.gitlab.io/2024/11/09/htb-blazorized.html) |
| 28 | **Freelancer** | Windows | 01 Jun 2024 | windows, netexec, feroxbuster, django, qrcode, zbarimg, idor, mssql | [writeup](https://0xdf.gitlab.io/2024/10/05/htb-freelancer.html) |
| 29 | **Intuition** | Linux | 27 Apr 2024 | ffuf, subdomain, flask-unsign, flask, python, feroxbuster, xss, xss-cookie | [writeup](https://0xdf.gitlab.io/2024/09/14/htb-intuition.html) |
| 30 | **FormulaX** | Linux | 09 Mar 2024 | ubuntu, express, nodejs, python, socket-io, xss, simple-git, git | [writeup](https://0xdf.gitlab.io/2024/08/17/htb-formulax.html) |
| 31 | **Office** | Windows | 17 Feb 2024 | windows, netexec, joomla, feroxbuster, cve-2023-23752, kerbrute, pcap, wireshark | [writeup](https://0xdf.gitlab.io/2024/06/22/htb-office.html) |
| 32 | **Analysis** | Windows | 20 Jan 2024 | windows, netexec, ffuf, subdomain, feroxbuster, upload, webshell, hta | [writeup](https://0xdf.gitlab.io/2024/06/01/htb-analysis.html) |
| 33 | **Napper** | Windows | 11 Nov 2023 | windows, iis, subdomain, ffuf, hugo, feroxbuster, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2024/05/04/htb-napper.html) |
| 34 | **Appsanity** | Windows | 28 Oct 2023 | tls, ffuf, vhosts, subdomain, windows, aspx, dotnet, feroxbuster | [writeup](https://0xdf.gitlab.io/2024/03/09/htb-appsanity.html) |
| 35 | **Drive** | Linux | 14 Oct 2023 | ubuntu, django, idor, feroxbuster, ffuf, gitea, sqlite, sqli | [writeup](https://0xdf.gitlab.io/2024/02/17/htb-drive.html) |
| 36 | **CyberMonday** | Linux | 19 Aug 2023 | debian, php, laravel, feroxbuster, off-by-slash, nginx, ffuf, git-dumper | [writeup](https://0xdf.gitlab.io/2023/12/02/htb-cybermonday.html) |
| 37 | **Download** | Linux | 05 Aug 2023 | ubuntu, express, cookies, crypto, hamc, sha1, signature, feroxbuster | [writeup](https://0xdf.gitlab.io/2023/11/11/htb-download.html) |
| 38 | **Gofer** | Linux | 29 Jul 2023 | debian, samba, netexec, smbclient, smtp, ffuf, feroxbuster, subdomain | [writeup](https://0xdf.gitlab.io/2023/10/28/htb-gofer.html) |
| 39 | **Intentions** | Linux | 01 Jul 2023 | ubuntu, php, laravel, feroxbuster, image-magick, sqli, second-order, second-order-sqli | [writeup](https://0xdf.gitlab.io/2023/10/14/htb-intentions.html) |
| 40 | **Snoopy** | Linux | 06 May 2023 | ubuntu, linux, bind, dns, feroxbuster, ffuf, subdomain, mattermost | [writeup](https://0xdf.gitlab.io/2023/09/23/htb-snoopy.html) |
| 41 | **Mailroom** | Linux | 15 Apr 2023 | ubuntu, debian, feroxbuster, wfuzz, gitea, subdomain, execute-after-redirect, xss | [writeup](https://0xdf.gitlab.io/2023/08/19/htb-mailroom.html) |
| 42 | **Cerberus** | Windows | 18 Mar 2023 | ttl, wireshark, dig, ffuf, icinga, github, cve-2022-24716, cve-2022-24715 | [writeup](https://0xdf.gitlab.io/2023/07/29/htb-cerberus.html) |
| 43 | **Pollution** | Linux | 03 Dec 2022 | debian, redis, redis-cli, feroxbuster, ffuf, subdomain, mybb, burp | [writeup](https://0xdf.gitlab.io/2023/07/01/htb-pollution.html) |
| 44 | **Flight** | Windows | 05 Nov 2022 | subdomain, crackmapexec, windows, php, apache, feroxbuster, file-read, directory-traversal | [writeup](https://0xdf.gitlab.io/2023/05/06/htb-flight.html) |
| 45 | **Vessel** | Linux | 27 Aug 2022 | ffuf, nodejs, express, feroxbuster, git, git-dumper, express-escape-functions, escape-functions | [writeup](https://0xdf.gitlab.io/2023/03/25/htb-vessel.html) |
| 46 | **Extension** | Linux | 16 Jul 2022 | subdomain, password-reset, laravel, feroxbuster, roundcube, gitea, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2023/03/18/htb-extension.html) |
| 47 | **RainyDay** | Linux | 15 Oct 2022 | ffuf, subdomain, docker, container, feroxbuster, idor, john, chisel | [writeup](https://0xdf.gitlab.io/2023/02/18/htb-rainyday.html) |
| 48 | **CarpeDiem** | Linux | 25 Jun 2022 | feroxbuster, wfuzz, vhosts, php, trudesk, html-file, upload, burp | [writeup](https://0xdf.gitlab.io/2022/12/03/htb-carpediem.html) |
| 49 | **Moderators** | Linux | 06 Aug 2022 | feroxbuster, wfuzz, fuzz, crackstation, filter, burp, burp-repeater, upload | [writeup](https://0xdf.gitlab.io/2022/11/05/htb-moderators.html) |
| 50 | **Seventeen** | Linux | 28 May 2022 | feroxbuster, wfuzz, vhosts, exam-management-system, searchsploit, sqli, boolean-based-sqli, sqlmap | [writeup](https://0xdf.gitlab.io/2022/09/24/htb-seventeen.html) |
| 51 | **Talkative** | Linux | 09 Apr 2022 | wfuzz, jamovi, bolt-cms, feroxbuster, rocket-chat, r-lang, docker, webhook | [writeup](https://0xdf.gitlab.io/2022/08/27/htb-talkative.html) |
| 52 | **Overgraph** | Linux | 30 Apr 2022 | wfuzz, vhosts, feroxbuster, graphql, angularjs, otp, nosql-injection, graphql-playground | [writeup](https://0xdf.gitlab.io/2022/08/06/htb-overgraph.html) |
| 53 | **Acute** | Windows | 12 Feb 2022 | feroxbuster, powershell-web-access, exiftool, meterpreter, metasploit, msfvenom, defender, defender-bypass-directory | [writeup](https://0xdf.gitlab.io/2022/07/16/htb-acute.html) |
| 54 | **Phoenix** | Linux | 05 Mar 2022 | wordpress, wpscan, wp-pie-register, wp-asgaros-forum, sqli, injection, time-based-sqli, sqlmap | [writeup](https://0xdf.gitlab.io/2022/06/25/htb-phoenix.html) |
| 55 | **AdmirerToo** | Linux | 15 Jan 2022 | feroxbuster, vhosts, wfuzz, adminer, cve-2021-21311, ssrf, adminer-oneclick-login, opentsdb | [writeup](https://0xdf.gitlab.io/2022/05/28/htb-admirertoo.html) |
| 56 | **Search** | Windows | 18 Dec 2021 | domain-controller, active-directory, vhosts, credentials, feroxbuster, smbmap, smbclient, password-spray | [writeup](https://0xdf.gitlab.io/2022/04/30/htb-search.html) |
| 57 | **Tally** | Windows | 04 Nov 2017 | windows, sharepoint, mssql, keepass, hashcat, kpcli, crackmapexec, smbclient | [writeup](https://0xdf.gitlab.io/2022/04/11/htb-tally.html) |
| 58 | **Overflow** | Linux | 23 Oct 2021 | ubuntu, cookies, padding-oracle, python, feroxbuster, padbuster, vhosts, sqli | [writeup](https://0xdf.gitlab.io/2022/04/09/htb-overflow.html) |
| 59 | **Altered** | Linux | 30 Mar 2022 | uhc, laravel, php, type-juggling, password-reset, wfuzz, bruteforce, feroxbuster | [writeup](https://0xdf.gitlab.io/2022/03/30/htb-altered.html) |
| 60 | **Hancliffe** | Windows | 09 Oct 2021 | hashpass, nuxeo, uri-parsing, feroxbuster, ssti, java, windows, unified-remote | [writeup](https://0xdf.gitlab.io/2022/03/05/htb-hancliffe.html) |
| 61 | **Object** | Windows | 28 Feb 2022 | uni-ctf, iis, windows, feroxbuster, wfuzz, jenkins, cicd, firewall | [writeup](https://0xdf.gitlab.io/2022/02/28/htb-object.html) |
| 62 | **EarlyAccess** | Linux | 04 Sep 2021 | wfuzz, vhosts, php, laravel, xss, xss-cookies, python, injection | [writeup](https://0xdf.gitlab.io/2022/02/12/htb-earlyaccess.html) |
| 63 | **Pressed** | Linux | 03 Feb 2022 | wordpress, uhc, burp, wpscan, totp, 2fa, xml-rpc, python | [writeup](https://0xdf.gitlab.io/2022/02/03/htb-pressed.html) |
| 64 | **Developer** | Linux | 21 Aug 2021 | youtube, feroxbuster, django, python, crypto, dnspy, ps2exe, xls | [writeup](https://0xdf.gitlab.io/2022/01/15/htb-developer.html) |
| 65 | **Static** | Linux | 19 Jun 2021 | feroxbuster, vpn, openvpn, totp, fixgz, oathtool, ntp, ntpdate | [writeup](https://0xdf.gitlab.io/2021/12/18/htb-static.html) |
| 66 | **Pikaboo** | Linux | 17 Jul 2021 | debian, feroxbuster, off-by-slash, lfi, log-poisoning, perl-diamond-injection, perl, open-injection | [writeup](https://0xdf.gitlab.io/2021/12/04/htb-pikaboo.html) |
| 67 | **Spooktrol** | Linux | 26 Oct 2021 | api, fastapi, python, feroxbuster, reverse-engineering, wireshark, ghidra, burp | [writeup](https://0xdf.gitlab.io/2021/10/26/htb-spooktrol.html) |
| 68 | **Spider** | Linux | 29 May 2021 | flask, python, flask-cookie, payloadsallthethings, ssti, jinja2, injection, sqli | [writeup](https://0xdf.gitlab.io/2021/10/23/htb-spider.html) |
| 69 | **Monitors** | Linux | 24 Apr 2021 | vhosts, wordpress, wpscan, wp-with-spritz, sqli, injection, exploit-db, password-reuse | [writeup](https://0xdf.gitlab.io/2021/10/09/htb-monitors.html) |
| 70 | **Unobtainium** | Linux | 10 Apr 2021 | kubernetes, deb, package, electron, nodejs, lfi, prototype-pollution, command-injection | [writeup](https://0xdf.gitlab.io/2021/09/04/htb-unobtainium.html) |
| 71 | **Proper** | Windows | 13 Mar 2021 | windows, iis, gobuster, ajax, sqlmap, sqli, keyed-hash, sqli-orderby | [writeup](https://0xdf.gitlab.io/2021/08/21/htb-proper.html) |
| 72 | **Breadcrumbs** | Windows | 20 Feb 2021 | gobuster, burp, python, cookies, jwt, upload, webshell, defender | [writeup](https://0xdf.gitlab.io/2021/07/17/htb-breadcrumbs.html) |
| 73 | **Tentacle** | Linux | 23 Jan 2021 | dig, dns, dnsenum, vhosts, kerbrute, kerberos, ntpdate, squid | [writeup](https://0xdf.gitlab.io/2021/06/19/htb-tentacle.html) |
| 74 | **Cereal** | Windows | 21 Nov 2020 | iis, windows, vhosts, wfuzz, feroxbuster, react, dotnet, csharp | [writeup](https://0xdf.gitlab.io/2021/05/29/htb-cereal.html) |
| 75 | **Kotarak** | Linux | 23 Sep 2017 | tomcat, feroxbuster, ssrf, msfvenom, war, container, lxc, ntds | [writeup](https://0xdf.gitlab.io/2021/05/19/htb-kotarak.html) |
| 76 | **Sharp** | Windows | 05 Dec 2020 | portable-kanban, reverse-engineering, dnspy, crypto, crackmapexec, dotnet-remoting, ysoserial.net, deserialization | [writeup](https://0xdf.gitlab.io/2021/05/01/htb-sharp.html) |
| 77 | **Reel2** | Windows | 03 Oct 2020 | windows, gobuster, owa, wallstant, javascript, sprayingtoolkit, phishing, responder | [writeup](https://0xdf.gitlab.io/2021/03/13/htb-reel2.html) |
| 78 | **Feline** | Linux | 29 Aug 2020 | ubuntu, upload, tomcat, deserialization, java, cve-2020-9484, ysoserial, docker | [writeup](https://0xdf.gitlab.io/2021/02/20/htb-feline.html) |
| 79 | **Charon** | Linux | 07 Jul 2017 | gobuster, sqli, injection, command-injection, filter, bash, waf, crackstation | [writeup](https://0xdf.gitlab.io/2021/02/16/htb-charon.html) |
| 80 | **Compromised** | Linux | 12 Sep 2020 | ubuntu, litecart, searchsploit, gobuster, mysql, credentials, php, mysql-udf | [writeup](https://0xdf.gitlab.io/2021/01/23/htb-compromised.html) |
| 81 | **Unbalanced** | Linux | 01 Aug 2020 | squid, http-proxy, foxyproxy, rsync, encfs, john, gobuster, squidclient | [writeup](https://0xdf.gitlab.io/2020/12/05/htb-unbalanced.html) |
| 82 | **Intense** | Linux | 04 Jul 2020 | snmp, snmpwalk, sqli, injection, sqlite, python, burp, bruteforce | [writeup](https://0xdf.gitlab.io/2020/11/14/htb-intense.html) |
| 83 | **Blackfield** | Windows | 06 Jun 2020 | dns, ldap, ldapsearch, crackmapexec, smbmap, smbclient, as-rep-roast, hashcat | [writeup](https://0xdf.gitlab.io/2020/10/03/htb-blackfield.html) |
| 84 | **Travel** | Linux | 16 May 2020 | ubuntu, vhosts, wfuzz, gobuster, wordpress, awesome-rss, simplepie, git | [writeup](https://0xdf.gitlab.io/2020/09/12/htb-travel.html) |
| 85 | **Mantis** | Windows | 16 Sep 2017 | smbmap, smbclient, rcpclient, kerbrute, orchard-cms, gobuster, mssql, mssqlclient | [writeup](https://0xdf.gitlab.io/2020/09/03/htb-mantis.html) |
| 86 | **Quick** | Linux | 25 Apr 2020 | ubuntu, gobuster, vhosts, wfuzz, quic, http3, curl, edgeside-include-injection | [writeup](https://0xdf.gitlab.io/2020/08/29/htb-quick.html) |
| 87 | **Calamity** | Linux | 30 Jun 2017 | gobuster, webshell, scripting, filter, phpbash, steganography, audacity, lxd | [writeup](https://0xdf.gitlab.io/2020/08/27/htb-calamity.html) |
| 88 | **Joker** | Linux | 19 May 2017 | udp, tftp, squid, http-proxy, foxyproxy, hashcat, penglab, gobuster | [writeup](https://0xdf.gitlab.io/2020/08/13/htb-joker.html) |
| 89 | **Oouch** | Linux | 29 Feb 2020 | oauth, ftp, vsftpd, vhosts, csrf, gobuster, api, ssh | [writeup](https://0xdf.gitlab.io/2020/08/01/htb-oouch.html) |
| 90 | **Shrek** | Linux | 25 Aug 2017 | php, gobuster, audacity, steganography, crypto, ssh, ecc, seccure | [writeup](https://0xdf.gitlab.io/2020/07/22/htb-shrek.html) |
| 91 | **ForwardSlash** | Linux | 04 Apr 2020 | ubuntu, php, vhosts, wfuzz, gobuster, burp, burp-repeater, rfi | [writeup](https://0xdf.gitlab.io/2020/07/04/htb-forwardslash.html) |
| 92 | **Patents** | Linux | 18 Jan 2020 | upload, libreoffice, office, xxe, gobuster, docx, custom-folder, sans-holiday-hack | [writeup](https://0xdf.gitlab.io/2020/05/16/htb-patents.html) |
| 93 | **Control** | Windows | 23 Nov 2019 | mysql, http-header, wfuzz, sqli, injection, mysql-file-write, hashcat, powershell-run-as | [writeup](https://0xdf.gitlab.io/2020/04/25/htb-control.html) |
| 94 | **Registry** | Linux | 19 Oct 2019 | wfuzz, vhosts, gobuster, zcat, docker, bolt-cms, searchsploit, api | [writeup](https://0xdf.gitlab.io/2020/04/04/htb-registry.html) |
| 95 | **Scavenger** | Linux | 17 Aug 2019 | whois, sqli, injection, zone-transfer, exim, cve-2019-10149, vhosts, wfuzz | [writeup](https://0xdf.gitlab.io/2020/02/29/htb-scavenger.html) |
| 96 | **Zetta** | Linux | 31 Aug 2019 | ftp-bounce, rfc-2428, ipv6, rsync, credentials, ssh, tudu, syslog | [writeup](https://0xdf.gitlab.io/2020/02/22/htb-zetta.html) |
| 97 | **RE** | Windows | 20 Jul 2019 | vhosts, jekyll, smbclient, smbmap, libreoffice, office, ods, macros | [writeup](https://0xdf.gitlab.io/2020/02/01/htb-re.html) |
| 98 | **Player** | Linux | 06 Jul 2019 | vhosts, ssh, searchsploit, wfuzz, burp, jwt, codiad, bfac | [writeup](https://0xdf.gitlab.io/2020/01/18/htb-player.html) |
| 99 | **Chainsaw** | Linux | 15 Jun 2019 | ftp, solidity, smart-contract, blockchain, python, web3, remix, command-injection | [writeup](https://0xdf.gitlab.io/2019/11/23/htb-chainsaw.html) |
| 100 | **Ellingson** | Linux | 18 May 2019 | werkzeug, python, flask, debugger, ssh, bash, hashcat, credentials | [writeup](https://0xdf.gitlab.io/2019/10/19/htb-ellingson.html) |
| 101 | **Ghoul** | Linux | 04 May 2019 | gobuster, hydra, zipslip, tomcat, docker, ssh, pivot, cewl | [writeup](https://0xdf.gitlab.io/2019/10/05/htb-ghoul.html) |
| 102 | **Holiday** | Linux | 02 Jun 2017 | nodejs, gobuster, dirsearch, burp, xss, filter, sqli, command-injection | [writeup](https://0xdf.gitlab.io/2019/09/11/htb-holiday.html) |
| 103 | **OneTwoSeven** | Linux | 20 Apr 2019 | sftp, tunnel, ssh, chroot, vim, crackstation, php, webshell | [writeup](https://0xdf.gitlab.io/2019/08/31/htb-onetwoseven.html) |
| 104 | **Helpline** | Windows | 23 Mar 2019 | manageengine, servicedesk, default-creds, excel, cve-2017-9362, xxe, responder, cve-2017-11511 | [writeup](https://0xdf.gitlab.io/2019/08/17/htb-helpline.html) |
| 105 | **FluJab** | Linux | 26 Jan 2019 | openssl, wfuzz, cookies, python, scripting, sqli, injection, python-cmd | [writeup](https://0xdf.gitlab.io/2019/06/15/htb-flujab.html) |
| 106 | **Conceal** | Windows | 05 Jan 2019 | snmp, snmpwalk, ike, ipsec, ike-scan, strongswan, iis, gobuster | [writeup](https://0xdf.gitlab.io/2019/05/18/htb-conceal.html) |
| 107 | **Zipper** | Linux | 20 Oct 2018 | zabbix, api, credentials, path-hijack, docker, ltrace, service-hijack, exploit-db | [writeup](https://0xdf.gitlab.io/2019/02/23/htb-zipper.html) |
| 108 | **Dab** | Linux | 14 Jul 2018 | flask, python, nginx, wsgi, memcached, bruteforce, hydra, wfuzz | [writeup](https://0xdf.gitlab.io/2019/02/02/htb-dab.html) |
| 109 | **Oz** | Linux | 01 Sep 2018 | api, sqli, hashcat, ssti, jinja2, payloadsallthethings, docker, container | [writeup](https://0xdf.gitlab.io/2019/01/12/htb-oz.html) |
| 110 | **Reel** | Windows | 23 Jun 2018 | ftp, cve-2017-0199, rtf, hta, phishing, ssh, bloodhound, powerview | [writeup](https://0xdf.gitlab.io/2018/11/10/htb-reel.html) |
| 111 | **Dropzone** | Windows | 19 May 2018 | xp, tftp, mof, wmi, stuxnet, alternative-data-streams, sysinternals | [writeup](https://0xdf.gitlab.io/2018/11/03/htb-dropzone.html) |
| 112 | **Falafel** | Linux | 03 Feb 2018 | wfuzz, sqlmap, sqli, type-juggling, php, upload, webshell, framebuffer | [writeup](https://0xdf.gitlab.io/2018/06/23/htb-falafel.html) |
| 113 | **CrimeStoppers** | Linux | 06 Jan 2018 | php, php-wrapper, lfi, ida, reverse-engineering | [writeup](https://0xdf.gitlab.io/2018/06/03/htb-crimestoppers.html) |

## Insane (60 machines)

| # | Name | OS | Release Date | Key Techniques | URL |
|---|------|----|-----------|----|-----|
| 1 | **WhiteRabbit** | Linux | 05 Apr 2025 | docker, lft, subdomain, ffuf, gophish, uptime-kuma, n8n, stalwart | [writeup](https://0xdf.gitlab.io/2025/12/13/htb-whiterabbit.html) |
| 2 | **DarkCorp** | Windows | 08 Feb 2025 | windows, active-directory, debian, subdomain, ffuf, themesberg, feroxbuster, roundcube | [writeup](https://0xdf.gitlab.io/2025/10/18/htb-darkcorp.html) |
| 3 | **Reaper** | Windows | 26 Aug 2025 | vulnlab, windows, pebear, ghidra, reverse-engineering, bof, pattern-create, x64dbg | [writeup](https://0xdf.gitlab.io/2025/08/26/htb-reaper.html) |
| 4 | **Zero** | Linux | 12 Aug 2025 | vulnlab, ubuntu, feroxbuster, htaccess, htaccess-file-read, python, python-requests, python-paramiko | [writeup](https://0xdf.gitlab.io/2025/08/12/htb-zero.html) |
| 5 | **University** | Windows | 26 Oct 2024 | windows, active-directory, netexec, django, xhtml2pdf, reportlab, cve-2023-33733, container | [writeup](https://0xdf.gitlab.io/2025/08/09/htb-university.html) |
| 6 | **Infiltrator** | Windows | 31 Aug 2024 | windows, active-directory, feroxbuster, netexec, username-anarchy, kerbrute, as-rep-roast, hashcat | [writeup](https://0xdf.gitlab.io/2025/06/14/htb-infiltrator.html) |
| 7 | **Ghost** | Windows | 13 Jul 2024 | windows, active-directory, ubuntu, ghost, subdomain, ffuf, next-js, feroxbuster | [writeup](https://0xdf.gitlab.io/2025/04/05/htb-ghost.html) |
| 8 | **MagicGardens** | Linux | 18 May 2024 | docker-registry, django, feroxbuster, python, flask, qrcode, qrcode-xss, xss | [writeup](https://0xdf.gitlab.io/2025/02/08/htb-magicgardens.html) |
| 9 | **Mist** | Windows | 30 Mar 2024 | windows, active-directory, pluck-cms, cve-2024-9405, pluck-module, webshell, php, amsi | [writeup](https://0xdf.gitlab.io/2024/10/26/htb-mist.html) |
| 10 | **Skyfall** | Linux | 03 Feb 2024 | feroxbuster, ffuf, subdomain, ssrf, minio, nginx-flask-parse, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2024/08/31/htb-skyfall.html) |
| 11 | **Corporate** | Linux | 16 Dec 2023 | ffuf, subdomain, sso, csp, content-security-policy, csp-evaluator, feroxbuster, html-injection | [writeup](https://0xdf.gitlab.io/2024/07/13/htb-corporate.html) |
| 12 | **Ouija** | Linux | 02 Dec 2023 | feroxbuster, burp, burp-proxy, subdomain, gitea, haproxy, cve-2021-40346, request-smuggling | [writeup](https://0xdf.gitlab.io/2024/05/18/htb-ouija.html) |
| 13 | **Rebound** | Windows | 09 Sep 2023 | windows, active-directory, domain-controller, netexec, rid-cycle, lookupsid, kerberoast, kerberoast-without-auth | [writeup](https://0xdf.gitlab.io/2024/03/30/htb-rebound.html) |
| 14 | **RegistryTwo** | Linux | 22 Jul 2023 | ubuntu, ffuf, vhosts, nginx, java, war, feroxbuster, docker | [writeup](https://0xdf.gitlab.io/2024/02/03/htb-registrytwo.html) |
| 15 | **Bookworm** | Linux | 27 May 2023 | ubuntu, nodejs, express, xss, idor, javascript, python, feroxbuster | [writeup](https://0xdf.gitlab.io/2024/01/20/htb-bookworm.html) |
| 16 | **Coder** | Windows | 01 Apr 2023 | windows, smb, netexec, smbclient, adcs, teamcity, reverse-engineering, dotnet | [writeup](https://0xdf.gitlab.io/2023/12/16/htb-coder.html) |
| 17 | **PikaTwoo** | Linux | 04 Feb 2023 | debian, express, feroxbuster, modsecurity, waf, apisix, uri-blocker-apisix, openstack | [writeup](https://0xdf.gitlab.io/2023/09/09/htb-pikatwoo.html) |
| 18 | **Derailed** | Linux | 19 Nov 2022 | ruby, rails, debian, ffuf, idor, xss, wasm, webassembly | [writeup](https://0xdf.gitlab.io/2023/07/22/htb-derailed.html) |
| 19 | **Absolute** | Windows | 24 Sep 2022 | windows, iis, crackmapexec, ldapsearch, dnsenum, feroxbuster, exiftool, username-anarchy | [writeup](https://0xdf.gitlab.io/2023/05/27/htb-absolute.html) |
| 20 | **Sekhmet** | Windows | 10 Sep 2022 | ffuf, subdomain, nodejs, express, feroxbuster, deserialization, json-deserialization, modsecurity | [writeup](https://0xdf.gitlab.io/2023/04/01/htb-sekhmet.html) |
| 21 | **Response** | Linux | 14 May 2022 | linux, ffuf, subdomain, feroxbuster, burp, burp-repeater, burp-proxy, hmac | [writeup](https://0xdf.gitlab.io/2023/02/04/htb-response.html) |
| 22 | **Hathor** | Windows | 16 Apr 2022 | crackmapexec, aspx, mojoportal, default-creds, upload, webshell, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2022/11/19/htb-hathor.html) |
| 23 | **Perspective** | Windows | 19 Mar 2022 | windows, iis, aspx, dotnet, feroxbuster, web.config, shtml, upload | [writeup](https://0xdf.gitlab.io/2022/10/15/htb-perspective.html) |
| 24 | **Scanned** | Linux | 29 Jan 2022 | django, source-code, chroot, jail, sandbox-escape, makefile, ptrace, fork | [writeup](https://0xdf.gitlab.io/2022/09/10/htb-scanned.html) |
| 25 | **Jail** | Linux | 14 Jul 2017 | centos, nfs, feroxbuster, bof, source-code, gdb, peda, pwntools | [writeup](https://0xdf.gitlab.io/2022/05/23/htb-jail.html) |
| 26 | **Brainfuck** | Linux | 29 Apr 2017 | vhosts, wordpress, ubuntu, wpscan, wp-support-plus, crypto, auth-bypass, smtp | [writeup](https://0xdf.gitlab.io/2022/05/16/htb-brainfuck.html) |
| 27 | **Fingerprint** | Linux | 04 Dec 2021 | ubuntu, ubuntu-1804, python, werkzeug, feroxbuster, execute-after-redirect, burp, burp-repeater | [writeup](https://0xdf.gitlab.io/2022/05/14/htb-fingerprint.html) |
| 28 | **Fulcrum** | Linux | 25 Nov 2017 | ubuntu, windows, feroxbuster, api, xxe, burp, burp-repeater, python | [writeup](https://0xdf.gitlab.io/2022/05/11/htb-fulcrum.html) |
| 29 | **Rabbit** | Windows | 31 Mar 2018 | iis, apache, wamp, feroxbuster, owa, exchange, joomla, complain-management-system | [writeup](https://0xdf.gitlab.io/2022/04/28/htb-rabbit.html) |
| 30 | **Fighter** | Windows | 05 May 2018 | iis, vhosts, wfuzz, feroxbuster, sqli, burp, burp-repeater, xp-cmdshell | [writeup](https://0xdf.gitlab.io/2022/04/25/htb-fighter.html) |
| 31 | **Ariekei** | Linux | 18 Nov 2017 | vhosts, wfuzz, youtube, waf, feroxbuster, cgi, shellshock, cve-2014-6271 | [writeup](https://0xdf.gitlab.io/2022/04/20/htb-ariekei.html) |
| 32 | **Toby** | Linux | 06 Nov 2021 | vhosts, wfuzz, wordpress, backdoor, wpscan, gogs, git, source-code | [writeup](https://0xdf.gitlab.io/2022/04/16/htb-toby.html) |
| 33 | **Minion** | Windows | 07 Oct 2017 | windows, asp, aspx, iis, feroxbuster, webshell, wfuzz, ssrf | [writeup](https://0xdf.gitlab.io/2022/04/07/htb-minion.html) |
| 34 | **Stacked** | Linux | 18 Sep 2021 | localstack, feroxbuster, wfuzz, vhosts, docker, docker-compose, xss, burp | [writeup](https://0xdf.gitlab.io/2022/03/19/htb-stacked.html) |
| 35 | **Anubis** | Windows | 14 Aug 2021 | iis, crackmapexec, vhosts, wfuzz, feroxbuster, ssti, xss, certificate | [writeup](https://0xdf.gitlab.io/2022/01/29/htb-anubis.html) |
| 36 | **PivotAPI** | Windows | 08 May 2021 | windows, active-directory, exiftool, as-rep-roast, getuserspns, hashcat, mssql, mssqlclient | [writeup](https://0xdf.gitlab.io/2021/11/06/htb-pivotapi.html) |
| 37 | **Sink** | Linux | 30 Jan 2021 | gitea, haproxy, gunicorn, request-smuggling, localstack, aws, aws-secretsmanager, aws-kms | [writeup](https://0xdf.gitlab.io/2021/09/18/htb-sink.html) |
| 38 | **CrossFitTwo** | OpenBSD | 20 Mar 2021 | openbsd, feroxbuster, burp, websocket, sqli, injection, vhosts, unbound | [writeup](https://0xdf.gitlab.io/2021/08/14/htb-crossfittwo.html) |
| 39 | **Attended** | OpenBSD | 19 Dec 2020 | smtp, stmp-user-enum, swaks, phishing, vim, cve-2019-12735, vim-modelines, firewall | [writeup](https://0xdf.gitlab.io/2021/05/08/htb-attended.html) |
| 40 | **APT** | Windows | 31 Oct 2020 | ipv6, rpc, ioxidresolver, active-directory, domain-controller, crackmapexec, hashcat, secretsdump | [writeup](https://0xdf.gitlab.io/2021/04/10/htb-apt.html) |
| 41 | **CrossFit** | Linux | 19 Sep 2020 | ftp-tls, openssl, wfuzz, vhosts, gobuster, xss, javascript, xmlhttprequest | [writeup](https://0xdf.gitlab.io/2021/03/20/htb-crossfit.html) |
| 42 | **RopeTwo** | Linux | 27 Jun 2020 | pwn, python, c, javascript, v8, d8, gef, pwngdb | [writeup](https://0xdf.gitlab.io/2021/01/16/htb-ropetwo.html) |
| 43 | **Laser** | Linux | 08 Aug 2020 | ubuntu, jetdirect, pret, printer, crypto, python, proto3, grpc | [writeup](https://0xdf.gitlab.io/2020/12/19/htb-laser.html) |
| 44 | **Dyplesher** | Linux | 23 May 2020 | memcached, gobuster, gogs, git, git-dumper, memcached-binary, memcached-auth, memcached-cli | [writeup](https://0xdf.gitlab.io/2020/10/24/htb-dyplesher.html) |
| 45 | **Multimaster** | Windows | 07 Mar 2020 | wfuzz, waf, filter, unicode, sqlmap, tamper, hashcat, crackmapexec | [writeup](https://0xdf.gitlab.io/2020/09/19/htb-multimaster.html) |
| 46 | **Fatty** | Linux | 08 Feb 2020 | java, ftp, update-alternatives, java-jar, wireshark, procyon, javac, directory-traversal | [writeup](https://0xdf.gitlab.io/2020/08/08/htb-fatty.html) |
| 47 | **PlayerTwo** | Linux | 14 Dec 2019 | vhosts, gobuster, wfuzz, twirp, proto3, api, totp, signing | [writeup](https://0xdf.gitlab.io/2020/06/27/htb-playertwo.html) |
| 48 | **Rope** | Linux | 03 Aug 2019 | directory-traversal, format-string, pwntools, bruteforce, pwn, python, ida, aslr | [writeup](https://0xdf.gitlab.io/2020/05/23/htb-rope.html) |
| 49 | **Bankrobber** | Windows | 21 Sep 2019 | mysql, smb, gobuster, cookies, xss, csrf, sqli, injection | [writeup](https://0xdf.gitlab.io/2020/03/07/htb-bankrobber.html) |
| 50 | **Smasher2** | Linux | 01 Jun 2019 | exploit, auth-bypass, logic-error, python, reference-counting, kernal-driver, mmap, reverse-engineering | [writeup](https://0xdf.gitlab.io/2019/12/14/htb-smasher2.html) |
| 51 | **Kryptos** | Linux | 06 Apr 2019 | gobuster, php, burp, mysql, wireshark, hashcat, rc4, crypto | [writeup](https://0xdf.gitlab.io/2019/09/21/htb-kryptos.html) |
| 52 | **Fortune** | OpenBSD | 09 Mar 2019 | certificate, certificate-authority, sslyze, command-injection, burp, burp-repeater, firewall, python | [writeup](https://0xdf.gitlab.io/2019/08/03/htb-fortune.html) |
| 53 | **CTF** | Linux | 02 Feb 2019 | ldap, ldap-injection, second-order, second-order-ldap-injection, python-cmd, python, totp, stoken | [writeup](https://0xdf.gitlab.io/2019/07/20/htb-ctf.html) |
| 54 | **Hackback** | Windows | 23 Feb 2019 | wfuzz, jq, gophish, php, php-disable-functions, aspx, rot13, javascript | [writeup](https://0xdf.gitlab.io/2019/07/06/htb-hackback.html) |
| 55 | **Sizzle** | Windows | 12 Jan 2019 | gobuster, smbmap, smbclient, smb, ftp, regex, regex101, responder | [writeup](https://0xdf.gitlab.io/2019/06/01/htb-sizzle.html) |
| 56 | **BigHead** | Windows | 24 Nov 2018 | windows, 2k8sp2, gobuster, wfuzz, phpinfo, dirsearch, nginx, github | [writeup](https://0xdf.gitlab.io/2019/05/04/htb-bighead.html) |
| 57 | **Ethereal** | Windows | 06 Oct 2018 | pbox, credentials, injection, hydra, python, shell, dns-c2, firewall | [writeup](https://0xdf.gitlab.io/2019/03/09/htb-ethereal.html) |
| 58 | **Reddish** | Linux | 21 Jul 2018 | node-red, nodejs, tunnel, php, redis, rsync, wildcard, docker | [writeup](https://0xdf.gitlab.io/2019/01/26/htb-reddish.html) |
| 59 | **Mischief** | Linux | 07 Jul 2018 | ipv6, snmp, snmpwalk, enyx, command-injection, hydra, filter, facl | [writeup](https://0xdf.gitlab.io/2019/01/05/htb-mischief.html) |
| 60 | **Smasher** | Linux | 09 Jun 2018 | bof, pwntools, timing-attack, padding-oracle, aes, directory-traversal | [writeup](https://0xdf.gitlab.io/2018/11/24/htb-smasher.html) |
