# IppSec HTB Video Index - Complete Reference

> The most comprehensive index of IppSec's HackTheBox video walkthroughs.
> Data sourced from [ippsec.rocks](https://ippsec.rocks) dataset, GitHub, and community resources.
> Last updated: 2026-04-10

## Stats

| Category | Count |
|----------|-------|
| HTB Machine Walkthroughs | 432 |
| UHC (Ultimate Hacking Championship) | 12 |
| HTB Sherlocks (DFIR) | 7 |
| VulnHub Machines | 4 |
| Tutorials / Methodology / Special | 61 |
| HTB Academy Modules | 17 |
| **Total Unique Content** | **533** |
| Total Searchable Entries (timestamps) | 9,245 |

## Key Resources

| Resource | URL |
|----------|-----|
| YouTube Channel | [youtube.com/ippsec](https://youtube.com/ippsec) |
| Searchable Video Index | [ippsec.rocks](https://ippsec.rocks) |
| GitHub | [github.com/IppSec](https://github.com/IppSec) |
| Dataset JSON (raw) | [dataset.json](https://github.com/IppSec/ippsec.github.io/blob/master/dataset.json) |
| Contributions Page | [ippsec.rocks/contributions](https://ippsec.rocks/contributions/) |

## IppSec's Tools & Repos

| Tool | Stars | Description |
|------|-------|-------------|
| [parrot-build](https://github.com/IppSec/parrot-build) | 234 | Ansible playbooks to build IppSec's Parrot OS pentesting VM |
| [forward-shell](https://github.com/IppSec/forward-shell) | 166 | Forward shell for firewall evasion via mkfifo named pipes |
| [ippsec.rocks](https://github.com/IppSec/ippsec.github.io) | 153 | Searchable index of all IppSec YouTube videos |
| [PowerSiem](https://github.com/IppSec/PowerSiem) | 126 | PowerShell SIEM for analyzing Sysmon events |
| [evil-cups](https://github.com/IppSec/evil-cups) | 43 | CUPS exploitation tool (CVE-2024-47076 chain) |
| [ctf-scripts](https://github.com/IppSec/ctf-scripts) | 21 | Scripts created during CTF competitions |
| [Jarmis](https://github.com/IppSec/Jarmis) | 8 | JARM TLS fingerprint analysis |

## Most Demonstrated Tools (across all videos)

| Tool | Appearances | Category |
|------|-------------|----------|
| nmap | 415 | Recon/Scanning |
| gobuster | 135 | Web Directory Fuzzing |
| docker | 107 | Containers |
| bloodhound | 95 | AD Analysis |
| burpsuite | 73 | Web Proxy |
| sqlmap | 67 | SQL Injection |
| ffuf | 66 | Web Fuzzing |
| hashcat | 62 | Password Cracking |
| wfuzz | 56 | Web Fuzzing |
| ghidra | 55 | Reverse Engineering |
| linpeas | 49 | Linux PrivEsc |
| impacket | 48 | AD/Network |
| chisel | 46 | Pivoting/Tunneling |
| metasploit | 45 | Exploitation |
| crackmapexec | 36 | AD/Network |
| wireshark | 35 | Packet Analysis |
| john | 33 | Password Cracking |
| burp | 28 | Web Proxy |
| ansible | 28 | Automation |
| gdb | 27 | Debugging |
| pspy | 26 | Process Monitor |
| certipy | 24 | AD CS |
| evil-winrm | 23 | Windows Remote |
| kerbrute | 22 | Kerberos |
| ysoserial | 21 | Java Deser |
| wpscan | 21 | WordPress |
| pwntools | 19 | Binary Exploit |
| responder | 16 | LLMNR Poison |

## Most Demonstrated Vulnerability Types

| Vulnerability | Appearances |
|---------------|-------------|
| SQL Injection | 101 |
| LFI (Local File Inclusion) | 98 |
| XSS (Cross-Site Scripting) | 97 |
| RCE (Remote Code Execution) | 89 |
| SSRF (Server-Side Request Forgery) | 65 |
| JWT Attacks | 53 |
| Command Injection | 51 |
| XXE (XML External Entity) | 38 |
| SSTI (Server-Side Template Injection) | 37 |
| Deserialization | 32 |
| File Upload Bypass | 28 |
| CSRF | 21 |
| Buffer Overflow | 15 |
| IDOR | 14 |
| ASREPRoasting | 11 |
| Log4j/Log4Shell | 10 |
| Directory Traversal | 9 |
| Race Condition | 9 |
| Shellshock | 9 |
| Pickle Deserialization | 8 |
| Kerberoasting | 6 |
| RFI | 6 |
| Type Juggling | 4 |
| PrintNightmare | 4 |
| Heartbleed | 4 |

---

## HTB Machines by Difficulty

### Easy (69 machines)

<details>
<summary>Click to expand Easy machines</summary>

#### Academy [Linux]
- Start of nmap
- Adding academy to our host file, then taking a look at the web page
- Discovering a weird port (33060), attempting to enumerate it manually
- Discovering admin.php from our gobuster results
- Playing with having spaces in usernames, then seeing roleid in the parameter

#### Access [Windows]
- Begin of recon: ftp, telnet, IIS 7.5
- Downloading all files off an FTP Server with WGET
- Examining the "Access Control.zip" file.
- Cracking a zip file with John
- Creating a wordlist for cracking the zip (strings of the mdb file)

#### Active [Windows]
- Begin of recon
- Poking at DNS - Nothing really important.
- Examining what NMAP Scripts are ran.
- Lets just try out smbclient to list shares available
- Using SMBMap to show the same thing, a great recon tool!

#### Admirer [Linux]
- Doing nmap quickly by not running scripts to get open ports, then using that output to run scripts.
- Checking out the webserver, discovering robots.txt
- Running gobuster on the admin-dir with the extensions txt and php
- Finding credentials.txt within that admin-dir
- Logging into FTP to discover the web directory source

#### Arctic [Windows]
- Enumerate with nmap
- Going to the webpage
- Using SearchSploit to find ColdFusion Exploits
- Attempt to exploit through MSF. Debug why it failed.
- Setting up a Burp Redirect listener

#### Armageddon [Linux]
- Start of the box, showing a quick way to nmap
- Looking at web page
- Looking for Drupal Scanners
- Showing how I would fingerprint opensource apps if there was no scanner
- Using DroopeScan to scan the site

#### Backdoor [Linux]
- Start of nmap
- Starting WPSCAN
- There's no index.php in wp-content/plugins/, which lets us find a vulnerable plugin (eBook Download 1.1)
- Playing with the eBook Download LFI
- Doing a full nmap portscan

#### Bastion [Windows]
- Begin of recon
- Using SMBClient to view open shares, discover /Backups
- Mount the SMB Share
- Playing with SMBMap which is a bit more automated but write files!
- Checking out files in the /Backups share

#### Blue [Windows]
- Start of Recon
- Finding NMAP Scripts (Probably a stupid way)
- Running Safe Scripts - Not -sC, which is default.
- Listing NMAP Script Categories (Prob a really stupid way)
- Really Cool Grep (Only show matching -oP)

#### Blunder [Linux]
- Start of NMAP
- Discovering install.php, which says bludit is being installed.
- Looking for exploits searchsploit, everything requires Auth
- Attempting a login and noticing the CSRF Tokens
- Looking for exploits online that haven't made it to SearchSploit yet

#### Bounty [Windows]
- Begin of recon
- Gobuster, using -x aspx to find aspx pages
- Playing with a file upload form, seeing what can be uploaded
- Using Burp Intruder to automate checking file extensions
- Finding a way to execute code from file upload in ASPX (web.config)

#### BountyHunter [Linux]
- Running nmap, doing all ports and min-rate
- Poking at the website to discover a static site
- Starting up a gobuster to do some recon in the background
- Discovering log_submit, and finding out it is vulnerable to XXE (XML Entity Injection)
- Verified it is vulnerable to XXE, attempting to extract a file

#### Buff [Windows]
- Introduction
- Begin of nmap and poking at the website
- Checking when an image was uploaded to the server with wget and exiftool
- Contact.php discloses the software Gym Management Software is being used.  Examining the exploit
- Editing the Python Exploit to force everything through a proxy, so we can examine what the exploit does.

#### Cap [Linux]
- Start of nmap and doing some recon against FTP
- Having trouble finding a release date, using WGET and examining metadata to see how old a page is
- Examining the web applicaiton
- Testing and finding the IDOR Vulnerability
- Examining the PCAP Downloaded through the IDOR Vulnerability to find FTP Creds

#### Curling [Linux]
- Begin of Recon
- Running Cewl to generate a wordlist
- Finding secret.txt in the HTML Source, which happens to be the password
- Runninh JoomScan so we have something running in the background
- Checking the manifest to get the Joomla Version

#### Delivery [Linux]
- Starting with nmap
- Enumerating the website to see links to the HelpDesk and Mattermost
- Attempting to enumerate the version of osTicket
- Searchsploit json output shows the date
- No exploits found, lets open a new ticket and see it gives us a way to update the ticket via email

#### Devel [Windows]
- Going over NMAP
- Anonymous FTP + File Upload
- Exploit Suggestor
- Getting Root

#### Doctor [Linux]
- Start of Nmap
- Poking at the website and doing Gobuster/SQLMap In the BG
- Registering an account and enumerating the new features, looking for XSS
- Testing if the box will click links, discovering Curl reaches back to us
- Finding command injection in the URL, finding a way to execute commands with spaces

#### Driver [Windows]
- Start of nmap
- Quickly testing SMB, then using CME to get a hostname of the box
- Testing out the website, discovering admin:admin logs us in. Running gobuster with HTTP Auth
- The website allows us to write to a file share. Going over SCF Files and how we can use them to steal NTLMv2 Hashes by having an external icon
- Using hashcat to crack the NTLMv2 Hash

#### Explore [Linux]
- Start of nmap
- Weird SSH Banner saying its Banana Studio, google tells us this is Android
- Doing a script scan against all open ports, and googling what each open port is
- Port 59777, brings us to ES File Explorer which has an exploit out
- Running the ES File Explorer exploit with getDeviceInfo to confirm it works

#### Forest [Windows]
- Running NMAP and queuing a second nmap to do all ports
- Using LDAPSEARCH to extract information out of Active Directory
- Dumping user information from AD via LDAP then creating a wordlist of users
- Creating a custom wordlist for password spraying with some bashfu and hashcat
- Using CrackMapExec to dump the password policy of Active Directory using a null authentication, then doing a Password Spray

#### Frolic [Linux]
- Begin of Recon, until around 13 minutes gathering information to avoid rabbit holes
- Using nc/ncat to verify a port is open (-zv)
- Doing gobuster across man of the sub directories
- Examining /admin/ - Examine the HTML Source because login is not sending any data
- Discover some weird text encoding (Ook), how I went about decoding it

#### Granny and Grandpa [Windows]
- Heads up.  The pivot idea, was a pretty big fail.  Should of prep'd more but was short on time.  Enjoy watching me struggle, if you wanted to see the 
- Nmap Results (Discovery of WebDav)
- HTTP PUT Upload Files
- MSFVenom Generate aspx payload
- User Shell Returned

#### Haystack [Linux]
- Begin of Recon find Elastic Search on 9200
- Checking the exif data in the image, nothing interesting, but showing FF changes some metadata when downloading (foresnic tip)
- Navigating to port 9200 and seeing the Elastic Search JSON Response
- Searching Elastic Search Documentation to see how to make queries
- Using /_cat/indices to see the "tables" withing ES

#### Heist [Windows]
- Begin of recon
- Logging into the webpage as guest and viewing attachments
- Examining the cisco type 7 passwords, using  ciscot7
- Decrypting the MD5Crypt password using Hashcat
- Using CrackMapExec to perform a SMB password spray with users/credentials we have

#### Help [Linux]
- Begin of recon
- Running gobuster to find /support
- Searching for a way to find version of HelpdeskZ
- Reading over the File Upload exploit script to see it requires server time
- Uploading a PHP Reverse Shell Script

#### Horizontall [Linux]
- Start of nmap, examining the page discovering its all static with no user input
- Examining the source code of the website
- Running the javascript through a beutifier so we can easily read this, and finding another web endpoint
- Going to api-prod.horizontall.htb, running gobuster and examining the endpoints
- Navigating to /admin brings us to a STRAPI login, searching for exploits and finding an RCE

#### Irked [Linux]
- Last video was missing about 2 minutes and cut off at 31:35.  Sorry, was an extremely busy week and didn't get to verify everything was good.
- Begin on Recon
- Starting a full nmap scan
- Discovery of IRC
- Manually looking at IRC

#### Jerry [Windows]
- Introduction, nmap
- Clicking around in Tomcat
- Playing around with HTTP Authentication
- Bruteforcing tomcat default creds with Hydra and seclists
- Sending hydra through a proxy to examine what is happening

#### Knife [Linux]
- Start of nmap
- Running GoBuster before we start poking at the site
- Discover the x-powered-by header says its a weird php version, going to google
- Finding a blog post about php-8.1.0-dev being backdoored
- Looking at the backdoor

#### Love [Linux]
- Running nmap against all ports
- Attempting to enumerate the initial web page (Voting System)
- Nmap finished, checking staging.love.htb from the SSL Certificate
- Finding an SSRF Vulnerability in the file scanner
- Having trouble using WFUZZ to fuzz all ports

#### Luanne [Linux]
- Introduction
- Starting nmap, using min-rate to speed up things and explaining why I don't normally show this
- Doing basic recon on /, noticing authentication isn't required everywhere find robots.txt
- Taking a look at port 9001, searching for default credentials
- Once logged into Supervisord, we can examine processes see HTTP is using LUA

#### MetaTwo [Linux]
- Introduction
- Start of nmap, attempting to login with FTP then going to the website
- Running WPScan with enumerate all plugins in aggressive mode
- Taking a look at the site while WPScan runs and finding a plugin (BookingPress-Appointment-Booking) and finding an exploit
- Replacing the NONCE in the exploit to get it working

#### Nest [Windows]
- Showing why we should run NMAP as root or sudo.
- Running nmap to see only SMB is open, start a full port scan and move on
- Enumerating SMB (Port 445) with CrackMapExec, SMBClient, and SMBMap to explore how each program works
- Running SMBClient to mount the share
- Installing CIFS-Utils so we can mount SMB and run commands like find against the share

#### Netmon [Windows]
- Begin of Recon
- Searching for good files to view via FTP
- Nothing really found, searching for where PRTG creation file is
- Backup configuration found!
- Logging in by incrementing the password from 2018 to 2019

#### Networked [Linux]
- Begin of recon
- Looking at the website, checking source, robots.txt, etc
- Using GoBuster with PHP Extensions as HTTP Header said it had PHP Enabled
- Writing a simple PHP Code Execution script and trying to upload it
- Discovery of backup.tar, examining timestamps between downloading with wget/firefox

#### Nibbles [Linux]
- Start of Recon
- Finding hidden directory via Source
- Downloading NibbleBlog to help us with finding version information
- Identifying what vresion of NibblesBlog is running
- Using SearchSploit to find vulnerabilities

#### Omni [Linux]
- Begin of nmap
- Finding out this is Windows IOT
- Showing the BlackHat paper on Hacking Windows IOT
- Trying SirepRAT out against this box
- Finally getting code execution witht he SirepRAT tool, trying to run powershell

#### OpenAdmin [Linux]
- Running GoBuster to discover /music/, checking the page to try to find out what it is.
- Going to login reveals this is OpenNetAdmin version 18.1.1, searchsploit isn't updated and fails to find the correct exploit
- Showing what to do when an web exploit script gives HTML
- Finding the correct exploit script, setting it to go through burpsuite
- Failing to get a reverse shell for a bit because of bad characters (explained at end, we needed to URL Encode it).

#### Optimum [Windows]
- Go to HTTPFileServer
- Explanation of Vulnerability
- Testing the Exploit
- Getting rev tcp shell with Nishang
- Shell returned

#### Pandora [Linux]
- Start of nmap
- Using nmap to scan NMAP
- Doing a SNMPWalk talking about SNMP Mibs and how to install them, then using snmpbulkwalk to speed up the scan
- Finding all the unique fields in our SNMPWalk with grep, sort, and uniq.  Which helps find fields of value
- SNMP Allowed us to view running processes on a box, a password was in the argument so we can ssh in

#### Paper [Linux]
- Start of nmap
- Checking out what version of Centos is running
- Running Feroxbuster and GoBuster
- Noticing a X-Backend-SErver header that leaks the virtual host Office.Paper
- Showing my favorite nmap script Banner-Plus

#### Pivoting Update: Granny and Grandpa [Windows]
- Really wanted to show people this method of pivoting, but ran into issues last video.  This video doesn't explain any exploits, just uses plink.exe to
- If you wanted to see the explanations behind exploits check out the original video: https://www.youtube.com/watch?v=ZfPVGJGkORQ
- Apologies for any confusion/wasted time.

#### Postman [Linux]
- Begin of nnmap scan
- Checking out the website, trying to identify what technology runs the site
- Nmap scan finished, start more recon (GoBuster and full nmap port scan)
- Trying to find out when the website was stood up with exiftool
- Full nmap showed the REDIS port, initial poking

#### Precious [Linux]
- Introduction
- Start of nmap
- Checking out the web page and finding command injection in the URL
- Space appears to be a bad character with command injection. Normal tricks like brace expansion or IFS don't work.
- Trying IFS to be a space but the trailing character makes it difficult

#### Previse [Linux]
- Start of nmap
- Running GoBuster, discovering the redirects have filesizes
- Showing the Execute After Read vulnerability (EAR) by using BurpSuite to hit / and discovering the page
- Using grep to show us only what we want (oP)
- Using BurpSuite to intercept the response to the request so we can disable the redirect (EAR). Then using the webform to create an account (IDOR)

#### Remote [Windows]
- Begin of nmap, enumerate ftp, and smb
- Taking a look at the website to discover umbraco
- Examining NFS with showmount
- Discovering umbraco.sdf on NFS is a database and contains the admin password
- Logging into umbraco and discovering the unauthenticated RCE

#### Safe [Linux]
- Begin of nmap
- Discovering MyApp in the HTML Source
- Examining MyApp on port 1337
- Opening myapp up in Ghidra
- Testing out the buffer overflow

#### Sauna [Windows]
- Running Nmap
- Poking at SMB with CrackMapExec, SMBMap, and RPCClient to get nothing
- Checking out the web page
- Playing with user input in the website and getting an error "HTTP VERB used is not allowed"
- Copying names from the website

#### ScriptKiddie [Linux]
- Running nmap
- Using Firefox Developer Tools to inspect the page and see its a Python webserver
- Fuzzing parameters with ffuf to see if anything sticks out
- Ffuf isnt giving expected output, lets send the request to BurpSuite to find out we are missing a HTTP Header
- Adding the Content-Type header to ffuf and finally fuzzing special characters

#### Secret [Linux]
- Start of nmap talking about seeing two ports having the same HTTP Banner
- Checking out the webpage to discover source code and some docs
- Always RTFM, Playing with the API to Register a user, login, and check out privilege level.
- Renaming our burp repeater tab by just double clicking on the number
- Trying to login with a name instead of email

#### Sense [Linux]
- Star of Recon
- Getting banned and Pivoting to verify
- Logging into PFSense
- Manually Exploiting PFsense
- Using Metasploit to exploit

#### ServMon [Windows]
- Start of NMAP
- Using SMBClient to search for open shares (None)
- Checking out the web page, some light fuzzing on login and examining how the language selection works
- Taking a Screenshot on Parrot and pasting it into Cherry Tree (Shift+PrintScreen)
- Checking out FTP and downloading the two txt files

#### Shocker [Linux]
- If you want some more details about the actual ShellShock exploit, check out the Beep Video.
- Begin Nmap, OS Enum via SSH/HTTP Banner
- Viewing CGI Script
- Begin NMAP Shellshock
- Debugging Nmap HTTP Scripts via Burp

#### Shoppy [Linux]
- Start of nmap
- Taking a look at the web page
- Discovering it is NodeJS based upon the error message [MasterRecon]
- Performing NoSQL boolean injection (mongodb) to bypass authentication
- Working payload for the NoSQL Injection.

#### Soccer [Linux]
- Introduction
- Start of nmap, assuming the web app is NodeJS based upon a 404 message
- Running Gobuster and discovering Tiny File Manager
- Looking for the source code and finding a default password of admin@123
- Navigating to uploads and attempting to upload a php shell to the website

#### Spectra [Linux]
- Nmaping the box
- Checking out the web pages, discovering Wordpress
- Getting the username of wordpress by looking at the blog post author
- Running WpScan with Plugins-detection
- Finding an open directory on the testing site, accessing a backup

#### Sunday [Linux]
- Begin of NMAP Discovery of Finger
- Enumerating Finger with Finger-User-Enum
- Nmap'ing all port quickly by lowering max-retries
- Adding an old Key Exchange Alogorithm to SSH
- Showing Hydra doesn't work, then using Patator

#### Support [Windows]
- Start of nmap
- Running CrackMapExec to enumerate open file share and downloading a custom DotNet Executable
- Showing that we can run DotNet programs on our linux machine (will show how I configured this at the end of the video)
- Using Wireshark to examine DNS Requests when running this application
- Using Wireshark to examine the LDAP Connection and discover credentials being send in cleratext

#### Swagshop [Linux]
- Begin of recon
- Examining the web page to find Magento, noticing /index.php/ mod-rewrite misconfig and old copyright
- Whoops should of done apt search magescan, either way this package is not in Kali
- Running MageScan to scan the website
- Finding an open configuration file (app/etc/local.xml)

#### Tabby [Linux]
- Start of Nmap
- Taking a look at the web page
- Discovering Megahosting.HTB and adding it to /etc/hosts
- Playing with news.php and explaining the logic of LFI
- Discovering it is a file_get_contents(), which means we can skip all our "RCE Tests" as it won't execute PHP Code

#### Teacher [Linux]
- Begin of recon
- Poking around at the website to identify what techologies it utilizes
- Discovering something odd about images/5.png
- Downloading 5.png to discover it is a text file with a portion of a password
- Finding a place to login (/moodle), attempt to enumerate valid usernames

#### Timelapse [Windows]
- Start of nmap
- Enumerating the file server
- Cracking the zip file with John
- Cracking the pfx file (PKCS12) with John
- Extracting the certificate and key from the pfx file

#### Traceback [Linux]
- Checking the web page, then running a SecList wordlist for CommonBackdoors
- GoBuster returned smevk.php
- Attempting to guess the password, get in with admin:admin
- Running script prior to my reverse shell to log the output... I forget to check this again but it did work!
- Reading note.txt which hints at finding a LUA File, using find to hunt for files

#### Traverxec [Linux]
- Running nmap against the box, port 80 is running a unique webserver (nostromo)
- Lets check out the website before we throw any exploits
- Launching metasploit then exploting Nostromo but sending the exploit through burpsuite to see what it is doing
- Code Execution worked, for some reason the proxies command didn't work the first time
- Explaining why the script does a GET request before throughing an exploit (Exploit Verification)

#### Trick [Linux]
- Introduction
- Start of nmap
- Poking at the DNS Server and discovering its hostname when querying itself
- Using dig to show the reverse lookup aswell, then perform a zone transfer with axfr
- Just showing dnsrecon to bruteforce a range of IP's, not really relavent to this but figured I'd show it

#### TwoMillion [Linux]
- Start of nmap, scanning all ports with min-rate
- Browsing to the web page and taking a trip down memory lane with the HackTheBox v1 page
- Attempting to enumerate usernames
- Solving the HackTheBox Invite Code Challenge
- Sending the code to JS-Beautify

#### Valentine [Linux]
- Start of Recon, identifying end of life OS from nmap
- Running vulnerability scripts in nmap to discover heartbleed
- (In video on Blue, I go a bit more in NMAP Scripts. https://www.youtube.com/watch?v=YRsfX6DW10E)
- Going to the HTTP Page to see what it looks like
- Begin of Heartbleed - Grabbing Python Module

#### Writeup [Linux]
- Start of recon identifying a debian box based upon banners
- Taking a look at the website, has warnings about DOS type attacks.
- Discovering the /writeup/ directory in robots.txt
- Checking the HTML Source to see if there's any information about what generated this page.  Discover CMS Made Simple
- CMS Made Simple is an opensource product. Search through the source code to discover a way to identify version information.

</details>

### Medium (65 machines)

<details>
<summary>Click to expand Medium machines</summary>

#### Agile [Linux]
- Description timestamps will be populated later today.

#### Ambassador [Linux]
- Start of nmap
- Discovering Grafana and seeing it is ~2 years old
- Looking for exploits
- Manually performing the exploit
- Looking for interesting files, extracting Grafana config which lets us log in

#### Arkham [Windows]
- Begin of Recon
- Checking the WebPages
- Examining /userSubscribe.faces, to discover potential deserialization
- Exploring javax.faces.ViewState
- Googling around to see what an unencrypted serialized object should look like

#### Atom [Windows]
- Start of nmap
- Running RPCDump which shows if this is vulnerable to PrintNightmare (Exploit it later)
- Examining the webpage
- Explaining why i use lowercase wordlists on against Windows Webservers
- Listing shares with smbclient to find an open share

#### Awkward [Linux]
- Introduction
- Start of nmap
- Taking a look at the web page, finding users on the site, and using FFUF to VHost Enumeration due to talking about a store
- Fingerprinting the websites, dev looks to be PHP and the main page appears to be Vue
- Exploring the vue app in Firefox Dev Tools, discovering some routes in the webpack which lead to an API

#### Bagel [Linux]
- Introduction
- Start of nmap
- Taking a look at the web page
- Looking for LFI, then exploring /proc to find where the application is and extracting the source code
- Taking a look at the Python Source Code and discovering port 5000 is the dotnet application and uses websockets

#### Bart [Windows]
- Begin Recon, Windows IIS/OS Mapping and GoBuster
- Explanation of Virtual Host Routing
- Developers name exposed in HTML Source, also discover /monitor
- Enumerating Username in PHP Server Monitor: Challenge Watch Sense to und
- erstand CSRF and write an automated bruteforcer

#### Bastard [Windows]
- Sherlock was fixed, should no longer report the false negative https://github.com/rasta-mouse/Sherlock/commit/ceb49f5b54be54effbada47fa3198abf744af390
- If you wanted to do this with MSF -- Watch the Arctic Video and use the exploit shown in the video.  If it doesn't work, try changing the payload with

#### Bolt [Linux]
- Start of nmap
- Examining the SSL Certificate to find alternative names
- Discovering PassBolt, but looks like we need an email to login to passbolt
- Checking the bolt.htb and finding a link to download a custom docker image
- Extracting the docker image and viewing the docker layers

#### Book [Linux]
- Begin of Recon
- Enumerating the login page
- Creating an account, identifying what fields are unique
- Logged into the page, examining functionality starting with the download.php file
- Playing with the search field

#### BroScience [Linux]
- Start of nmap
- Finding some vulnerable-looking parameters
- Testing some basic things for LFI, finding a WAF blocking ../.  Double encoding it to get passed
- Start of writing a script to abuse this LFI and crawl/download all the php source
- Making the script recursive, so it will check pages downloaded for new links

#### Bucket [Linux]
- Start of nmap discovering the HTTP Site bucket.htb
- Poking at the website, using the developer console to discover s3.bucket.htb
- Using curl to view HTTP Headers and discovering amazon
- Oh god... I forgot to edit the URL in this gobuster! Actually created a feature request in GoBuster to fix this mistake from happening.
- Installing AWS CLI

#### Cache [Linux]
- Running NMAP and checking out the page
- Author page contains a hint to do some type Domain Brute Forcing
- The Login form won't go to burpsuite, lets check out javascript
- Doing VirtualHost (VHOST) Bruteforcing with GoBuster to discover hms.htb
- Discovering OpenEMR, running searchsploit, attempting to find the version of it

#### Cascade [Windows]
- Begin of nmap
- Enumerating RPC to identify usernames
- Setting up a bruteforce and creating a custom wordlist with hashcat
- Enumerating LDAP with LDAPSEARCH
- Discovering the cascadeLegacyPwd LDAP Attribute which has a password

#### Catch [Linux]
- Start of nmap, going over some standard cookies and knowing the web technology behind it
- Checking what the main webpage is, discovering an APK File
- Analysing the APK file with JADX-GUI
- Searching for strings, finding some tokens
- Looking at the Gitea API to discover how to use our token

#### Chatterbox [Windows]
- Begin of Recon
- Start of aChat buffer Overflow: Finding the exploit script with Searchsploit
- Begin of replacing POC's Calc Shellcode with what is generated from MSFVenom
- Correction: Payload Size wrong, should be 3,xxx -- look at "Payload Size" I accidentally highlighted the size of the python file.
- Whoops, erased too much out of POC.  Lets correctly replace the shellcode this time and get a shell.

#### Devzat [Linux]
- Start of nmap
- Poking at the SSH Chat Application
- Running a VHOST Scan and discovering pets.devzat.htb
- Discovering pets.devzat.htb doesn't have a 404 and is a golang webserver
- Fuzzing the user input on pets

#### Dynstr [Linux]
- Start of nmap discovering the distribution of Ubuntu based upon SSH Headers
- Looking at the WebPage and discovering credentials
- Checking No-IP's documentation for updating Dynamic DNS Names
- Using Curl to create a dynamic DNS Name
- Testing for Command Injection

#### Encoding [Linux]
- Introduction
- Start of nmap
- Checking out the API Documentation
- Interacting with the API Server
- Showing the file_url, parameter and showing we can access local files

#### Escape [Windows]
- Introduction
- Start of nmap
- Examining SSL Certificates and seeing "sequel-DC-CA", which hints towards there being a Certificate Authority
- Using CrackMapExec to enumerate file shares
- Accessing the Public Share, downloading a PDF File and finding credentials in it, using CME again and using CME to test smb, winrm, and mssql

#### Faculty [Linux]
- Start of nmap
- Testing login of the webapp, finding SQL Injection to bypass it
- Running gobuster with our cookie so it has access to any authenticated page
- Examining the course edit functionality and discovering how the page tells us if our update was a success
- Explaning the dangerous thing with update injections, we accidentally changed EVERY row.

#### Forge [Linux]
- Running nmap finding a filtered port with some open ones
- Running GoBuster to always have something running in the background
- Playing with the Upload Form
- Playing with the Upload from URL to see what library connects back to us (SSRF)
- The Upload From URL has a blacklisted address, playing with it to discover what is blacklisted

#### Forgot [Linux]
- Introduction
- Start of nmap
- Talking about Varnish, then looking at the website
- Poking at the Forgot Password functionality and showing we can enumerate valid users
- Discovering a username in the HTML Source

#### Fuse [Windows]
- Begin of nmap, see a Active Directory server with HTTP
- Gathering usernames from the website
- Using KerBrute to enumerate which users are valid
- Using Cewl to generate a password list for brute forcing
- Using Hashcat to generate a password list for brute forcing

#### Giddy [Windows]
- Begin of intro
- Examining port 80 and 443
- Using gobuster to discover directories
- /remote discovered, nothing to do here
- /mvc discovered

#### Health [Linux]
- Start of nmap
- Taking a look at the website
- Testing the webhook to see the app will send us information about a web page
- Trying to access port 3000, getting blocked by a filter trying to include 127.0.0.1 and 0x7f000001
- Playing with the webhook to see if it will send us the entire page

#### Intelligence [Windows]
- Start of nmap, discover Active Directory and a web server
- Doing some common checks against a Domain Controller
- Discovering PDF's with filenames based upon the date
- Building a customized wordlist based upon the date with the date command
- Downloading the PDF's with wget and then examining metadata

#### Interface [Linux]
- Introduciton
- Start of nmap, navigating to the page and identifying the framework based upon 404
- Playing around looking at javascript source, not getting anything
- Playing around with prd.m.rengering-api.interface.htb... I'm guessing file not found is the webserver, not actual code.
- Showing the difficulty of dirbusting API Servers

#### Investigation [Linux]
- Introduction
- Start of nmap
- Start of gobuster
- Discovering an upload form, looking for where things get uploaded
- The upload gives us ExifTool output, including the version number to show it is vulnerable to CVE-2022-23935

#### Jeeves [Windows]
- Begin of Enumeration
- Avoiding the Rabbit Hole on port 80 (IIS)
- Begin of Jenkins
- Using Jenkins Script Console (Groovy) to gain code execution
- Reverse TCP Shell via Nishang

#### Jewel [Linux]
- Introduction
- Start of nmap, going into why it needs sudo
- Checking Phusion Passenger version
- Downloading the source code from port 8000 (GitWeb)
- Using Brakeman to analyze the source code to the RAILS App

#### JSON [Windows]
- Start of recon, NMAP
- Using SMBClient to look for OpenShares
- Examining the HTTP Redirect on the page
- Attemping default credentials
- Running GoBuster with PHP Extensions

#### Magic [Linux]
- Starting GoBuster on the root and images
- Finding Auth Bypass via SQL Injection on login then throwing it to SQLMap
- Creating a basic PHP Shell, then attempting to upload it
- Grabbing the magic bytes off a JPG, then prepending it to our shell
- File uploaded, hunting for an LFI and doing more SQLMap

#### Mango [Linux]
- Start of nmap and examining the HTTPS Certificate to get a potential hostname
- Doing light testing on the HTTPS Site for SQL Injection, then sending to SQLMap.  Using --force-ssl to make SQLMAP do HTTPS instead of HTTP
- Playing with analytics.php and some light testing to see if we could do SSRF.  Put it on the backburner and move on.
- Testing the logon prompt on the HTTP Site, playing with SQL Injection and starting another SQLMap
- Going over NoSQL Injection

#### Mentor [Linux]
- Start of Nmap
- Enumerating for virtual hosts with ffuf to find the api.mentorquotes.htb page
- Talking about FastAPI, attempting to utilize the endpoints but Authentication is required. Create an account
- Logging into the endpoint, discovering how to send authentication to the endpoints.  Don't really gain anything
- Using ffuf to search for extra endpoints and discover /admin/ but can't do anything

#### Meta [Linux]
- Introduction
- Start of nmap
- Running a VHOST enumeration scan
- Discovering the Metaview application which is an image upload
- Attempting to exploit the file upload, uploading non images.

#### Monteverde [Windows]
- Begin of recon
- Using rpcclient with null authentication and dumping active directory users
- Building a password list with hashcat --stdout (Forest Video does it better)
- CrackMapExec shows SABatchJobs:SABatchJobs are valid credentials
- Using SMBMap to list contents of directories

#### Noter - Cracking Flask Cookies and performing MySQL Raptor Exploit on Modern Distro RCE [Linux]
- Start of nmap
- Registering an account
- Enumerating valid usernames based upon error message
- Using ffuf to match regex to enumerate valid usernames
- Poking at the web applicaiton trying IDOR/SSTI and failing

#### Obscurity [Linux]
- Quick rant about Security through Obscurity and why it can be good
- Begin of nmap'ing the box
- Checking out the webpage, GoBuster giving weird errors, try WFUZZ
- Taking a deeper look at the website while we have some recon running
- Wfuzz found nothing hunting for /$directory/SuperSecureServer.py

#### OpenKeyS [Linux]
- Introduction
- Begin of nmap
- Nmap shows it is BSD, going over some command differences
- Running GoBuster to find other PHP Scripts
- Looking at the includes directory and finding source code

#### OpenSource [Linux]
- Start of nmap
- Identifying a Docker exists based upon the Python Version in NMAP + SSH Version [MasterRecon]
- Navigating to the website downloading the source code available, there is a git folder switching branches
- Discovering a vulnerability in the os.path.join command, if we prefix our path with a slash it will overwrite the entire path
- Attempting to upload a malicious cron, docker isn't running cron so it doesn't work

#### Ophiuchi [Linux]
- Start of nmap, looking at release date of tomcat
- Starting a bruteforce of /manager login to run in the background
- Playing with the YAML Parser, sending special characters leads to a stack trace showing the library
- Testing a YAML Deserialization payload for Snake YAML
- Start of weaponizing the payload

#### Outdated [Windows]
- Running nmap
- Running CrackMapExec to enumerate the share
- Talking about a common misconception about "Null SMB Authentication"
- Downloading a PDF off the open share
- Using SWAKS to send an emailw ith a link to see if anything clicks it

#### Passage [Linux]
- Start of nmap
- Identifying this is likely Ubuntu Xenial
- Attempting basic SQL Map
- Failing to find a way to enumerate CuteNews version
- Looking over an exploit script from SearchSploit

#### Photobomb [Linux]
- Start of nmap
- Discovering this is a ruby Sinatra Web App based upon error message
- Discovering credentials in javascript
- Examining the HTTP Request to resize images and discovering an RCE
- Getting a reverse shell

#### Pit [Linux]
- Intro the important thing about this box is recon
- Start of nmap discovering an nginx server header
- The SSL Certificate leaks an important hostname
- Running an SNMPWalk which has a bunch of important information, notably the HTML Directory
- Discovering the SeedDms51x Directory, trying to enumerate version (Failing)

#### Querier [Windows]
- Begin of Reocn
- Using SMBMap to enumerate fileshares
- Discovering an Excel Macro File
- Using olevba to extract macro from the document to discover credentials
- Using MSSQLClient.py from Impacket to log into the SQL Server

#### Ready [Linux]
- Start of nmap discovering gitlab
- Registering for an account, then finding the version
- Searching the GitLab commit history to see the patch changing how localhost is verified
- Using the import repo from URL feature to force the server to make a request
- Attempting SSRF Attacks with Gopher

#### Resolute [Windows]
- Talking about my switch to Parrot
- Begin of nmap, discovering it is likely a Windows Domain Controller
- Checking if there are any open file shares
- Using RPCClient to enumerate domain users (enumdomusers)
- Using CrackMapExec to dump the PasswordPolicy

#### Schooled [Linux]
- Intro FreeBSD Box
- Start of nmap explaining why versions are useful
- Discovering hostname on the box, then adding it to our host file
- Using GoBuster to bruteforce virtual hosts and discovering moodle
- Searching Moodle on github to find a way to identify Moodle Version

#### Scrambled [Windows]
- Start of nmap
- Viewing the website and discovering NTLM is disabled
- Using Kerbrute to enumerate valid users and then password spray with username
- Bad analogy comparing Kerberos works with TGT/TGS and Movie Theater Tickets
- Using Impacket's GetTGT Script to get Ticket Granting Ticket as Ksimpson and exporting KRB5CCNAME so Impacket uses it

#### Seal [Linux]
- Begin of nmap
- Browsing to the website and doing some light fuzzing
- Adding the uri_hex (url encoder) to our wfuzz to fuzz special characters
- Taking a look at port 8080, discovering gitbucket and registering an account
- Exploring the infra repository on gitbucket, going over its Ansible Scripts

#### SecNotes [Windows]
- Begin of recon
- Checking out the website
- Using wfuzz to enumerate usernames
- Logging in with an account we created
- Checking out Change Password and noticing it does this poorly

#### Shibboleth [Linux]
- Running NMAP
- The footer talks about BMC, explaining why I jumped to IPMI when reading this
- Running a Virtual Host (VHOST) Scan with Wfuzz to try and find a domain that points to an ILO
- Talking about IPMI
- Running Metasploit to dump the IPMI Hash and then crack it with hashcat

#### Silo [Windows]
- Begin of recon
- Begin of installing SQLPlus and ODAT (Oracle Database Attack Tool)
- Bruteforcing the SID with ODAT
- Holy crap, this is slow lets also do it with Metasploit
- Bruteforcing valid logins with ODAT

#### SneakyMailer [Linux]
- Start of nmap
- Poking a the websites
- Starting gobusters in the background while we look at the site
- Grabbing a list of emails off of the website
- Using SWAKS to mass email users with a link

#### Sniper [Windows]
- Begin of Nmap scans
- Checking out the website and running a few GoBuster dir searches
- Examining Links on the blog page and discover a LFI Vulnerability in the LANG Parameter
- Discovering .. is a bad character, working around it by starting the path with a slash
- Testing RFI via SMB, then failing to steal a hash and use impackets SMBServer

#### StreamIO - Manually Enumerating MSSQL Databases, Attacking Active Directory, and LAPS [Windows]
- Start of nmap, discovering it is an Active Directory Server and hostnames in SSL Certificates
- Running Feroxbuster and then cancelling it from navigating into a few directories
- Examining the StreamIO Website
- Finding watch.stream.io/search.php and
- Fuzzing the search field with ffuf by sending special characters to identify odd behaviors

#### Tenet [Linux]
- Start of nmap
- Discovering wordpress, fixing our host file
- Running wpscan to enumerate wordpress via aggressive mode
- Manually enumerating wordpress users by listing blog posts by author
- Discovering Sator.php, then using GoBuster to discover hidden backups to find Sator.php.bak

#### TheNotebook [Linux]
- Start of nmap
- Checking out the webpage, trying to identify the language running the page
- Exploring how Add Note works and testing SSTI/SQL/XSS
- Checking out the cookie to see how the JWT is encoded
- JWT.IO shows the JWT is RS256 and there's a URL for the privKey

#### Undetected [Linux]
- Start of nmap
- Taking a look at the website
- Running gobuster against store.djewelry.htb and discovering a vendor directory that has phpunit
- Exploiting phpunit to get a shell on the box
- Shell recieved on the box as www-data

#### Unicode [Linux]
- Start of nmap
- Registering and logging in and examining what a regular user can do
- Playing with the file upload capability
- Discovering there is a JWT in our HTTP Request, examining it to see it is RS256 and has a claim
- Explaining how we are going to exploit the Claim Misuse vulnerability in this JWT

#### UpDown [Linux]
- Start of nmap
- Testing the webhook, examining the request the server makes
- Trying other URL Wrappers to see how the application behaves
- Finding the .git sub directory, running git-dumper to extract source code
- Finding and explaining the LFI Vulnerability

#### Worker [Windows]
- Start of nmap
- Checkign out the open SVN Port
- Adding the discovered domains to /etc/hosts and checking out the websites
- Some grep magic to show only what we want, which is URLS
- Using GoBuster to see if there are any more more VHOSTS

#### Writer [Linux]
- Start of nmap
- Discovering admin login page, running SQLMap and discovering it is SQL Injectable
- Testing for SQL Injections in the username and password, discovering injection in the username
- The adminsitrative interface lets us upload images, failing to upload a PHP Shell
- Using the SQL Union Injection to extract source code via Load_file, then creating a python script to automate it

</details>

### Hard (62 machines)

<details>
<summary>Click to expand Hard machines</summary>

#### Acute [Windows]
- Start of nmap, the Server Header changes based upon DNS
- Navigating to the website, discovering the "New Starter Form" which has some key information like a welcome password and username convention
- Password spraying the Powershell Web Access (PSWA), discovering a valid credential but wrong host, word document had another host which is valid for e
- Playing around in the PSWA
- Looking at hidden files, discovering c:\utils\desktop.ini which states its a directory that is excluded by AV

#### AdmirerToo [Linux]
- Start of nmap, discovering a webserver and filtered port
- Discovering a hostname in the 404 not found message in the mailto section
- Gobuster VHOST Discoery finds the subdomain db.admirer-gallery.htb which is adminer. Playing with the application and raw SQL Commands
- Trying to write files with INTO OUTFILE, also testing the secure file priv default directory for MySQL which is the most reliable
- Going to google and finding this version of adminer is vulnerable to a SSRF, but having trouble with this because the login for adminer is different

#### Blackfield [Windows]
- Start of nmap
- Enumerating fileshares with SMBClient and CrackMapExec, highlighting some picky syntax
- Mounting the profiles$ directory so we can build a username list
- Using Kerbrute to enumerate valid usernames
- Running GetNPUsers to perform an ASREP Roast

#### Breadcrumbs [Windows]
- Start of nmap
- Poking at the website
- Quickly testing for SQL Injection and coming up with nothing
- Creating an account and checking what regular users can do
- Using BurpSuite Sequencer to identify low entropy within login cookies

#### Calamity [Linux]
- Blog Post: https://reboare.github.io/lxd/lxd-escape.html
- Begin of recon
- admin.php discovered, finding the pw
- Getting Code Execution
- Finding out why Reverse Shells weren't working

#### Carpediem [Linux]
- Nmap the box, examining server banners
- Checking out the website, doesn't seem like anything special
- Using Ffuf to perform a virtual host scan to discover other subdomains and find portal
- Discover the Motorcycle Store Portal. Trying to play with a potential LFI but deciding it may be a rabbit hole
- Stop of examining rabbit hole.

#### Cereal [Windows]
- Start of nmap, showing having valid hostnames will give more information
- Error message on source.cereal.htb leaks a path
- Showing .git doesn't exist in DirectyList but does in Raft
- Using Git-Dumper to download the .git directory and view the source
- Looking at Git History shows where deserialization happens and a hard coded JWT

#### Compromised [Linux]
- Start of nmap, discover web and ssh.  Discover litecart, fail to find a way to identify version
- Running GoBuster to find the backup directory
- Examining the tar archive
- Talking about the unix time being 32-bit timestamps but tar did not keep entire timestamp
- Using find with printf to sort files by modified time

#### Conceal [Windows]
- Begin of recon
- Checking SNMP with snmpwalk
- Discovering a Hashed PSK (MD5) in SNMPWalk, searching the internet for a decrypted value
- Getting more SNMP Information with snmp-check
- Going over UDP Ports discovered by snmp-check

#### Control [Windows]
- Begin of nmap
- Checking out the webpage, notice an IP in the comments and run GoBuster to discover /uploads/.  Run GoBuster on /uploads/ looking for PHP files
- Begin fuzzing Proxy Headers with wfuzz to access admin.php
- Using Python's netaddr to generate an IP List based upon subnet, discovering X-Forwarded-For: 192.168.4.28 allows access to admin.php
- Having BurpSuite automatically add the x-forwarded-for header to our requests

#### CrimeStoppers [Linux]
- Begin of Recon: Getting ubuntu version
- Navigating to the CrimeStoppers Page
- First Hint - Read The Source!
- 2nd Hint - No SQL Databases and playing with the upload form
- 3rd Hint - Setting Admin cookie to 1 to see whiterose.txt

#### Dab [Linux]
- Begin of the box
- Checking the HTTP Ports out
- Using wfuzz to bruteforce a login on port 80
- Begin examining port 8080, use wfuzz to bruteforce a cookie
- Using wfuzz to enumerate the WAF and determine bad characters

#### Developer [Linux]
- Start of nmap
- Examining the web page, noticing every URL with admin gets redirected to a django login
- Creating an account and looking at the page to discover CTF Challenges
- CHALLENGE 1: Phished List, a protected excel spreadsheet. Remove protection to see hidden cells
- Submitting a writeup, discovering an old version of Firefox talks to us

#### DropZone [Windows]
- Start of Recon
- TFTP Enumeration - Identifying configuration and OS information
- Finding a path to code execution
- Examining PSExec Metasploit Module
- Using irb within metasploit to print a powershell payload

#### EarlyAccess [Linux]
- Start of nmap, adding earlyaccess.htb to the hostfile
- Registering an account to see what features are enabled to regular users
- Discovering bad characters of username are only checked upon registration, not changing it from the profile page
- Testing the Contact Forms for XSS by sending a message to ourself
- Using document.location javascript to steal cookies

#### Ellingson [Linux]
- Begin of recon, examining website seeing the "Hackers" Theme
- Discovering a Flask/Werkzeug Debug page (Patreon Hack of 2015)
- Demoing how this is fixed now, with Werkzeug requiring a pin code
- Testing if we can connect back to our host with ping or curl (cannot)
- Dropping a SSH Key via python since we cannot reverse shell

#### Extension [Linux]
- Start of nmap, then discovering a laravel app
- Laravel app uses Ziggy which exposes a list of all the routes
- Finding the /management/dump endpoint but we keep getting page expired (missing some headers)
- Using ffuf to brute-force the management/dump endpoint
- Dumping a list of users and then cracking them

#### Falafel [Linux]
- *Note: RationalLove was patched after I did this box.  So mistakenly thought it was still vulnerable.  Enjoy the fails/confusion!
- Begin of Recon
- Bruteforcing valid users
- Manually finding SQL Injection
- Using --string with SQLMap to aid Boolean Detection

#### Feline [Linux]
- Start of nmap digging into Version numbers of applications
- Finding Tomcat is an old version
- Checking out the web page
- Playing with the file upload, uploading an EICAR to test virus scanning
- Finding if we put a directory or nothing for filename we get an error message

#### Flight [Windows]
- Introduction
- Start of Nmap
- Playing with the web page, but everything is static doing a VHOST Bruteforce to discover school.flight.htb
- Discovering the view parameter and suspecting File Disclosure, testing by including index.php and seeing the source code
- Since this is a Windows, try to include a file off a SMB Share and steal the NTLMv2 Hash of the webserver then crack it

#### Flujab [Linux]
- Begin of Recon
- Adding DNS Names to /etc/hosts
- Using Aquatone to take HTTP Screenshots of a bunch of pages
- Start of looking at FreeFlujab.htb
- Looking at HTTP Cookies we send

#### ForwardSlash [Linux]
- Begin of Nmap
- Running Gobuster to Bruteforce the pages and subdomains to find backup.forwardslash.htb
- Registering an account and examining the functions to signed in users
- Playing with the ProfilePicture.php to discover we can do file inclusion
- Testing for RFI

#### Ghoul [Linux]
- Begin of Recon, notice multiple SSH Host Keys
- Discovering the HTTPD Website has a PHP Script, Run SQLMap and update gobuster to find PHP
- Moving onto enumerating TOMCAT, default password (admin:admin) logs in and attempting to discover framework via google images
- Discovering that this TOMCAT page allows the ability to upload images and zips
- Explaining the ZipSlip Vulnerability

#### Hancliffe [Linux]
- Start of nmap
- Identifying it is a windows box via ping and looking at its TTL, and running Gobuster with a lowercase wordlist since windows is not case sensitive.
- Looking at HashPass to see it just generates static passwords based upon Name/Website/Master Password
- Identifying a JSESSIONID cookie given when accessing /maintenance/ which enables a weird path traversal vuln [MasterRecon]
- Identifying the Nuxeo application and searching for the web vulnerability

#### Helpline [Windows]
- Begin of Recon
- Checking the ManageEngine Page
- Running Searchsploit to see potential exploits
- Enumerating valid usernames via AjaxDomainServlet
- Logging in with guest:guest

#### Holiday [Linux]
- Articles Mentioned:
- https://ictf.cs.ucsb.edu/pages/the-2016-2017-ictf-ddos.html
- https://thehackerblog.com/poisoning-the-well-compromising-godaddy-customer-support-with-blind-xss/index.html
- NMAP Scan and Review
- GoBuster and identify User Agent based Routing

#### Intense [Linux]
- Begin of nmap
- Examining the Message, pointing out the endpoint does not need authentication
- Using FFUF to fuzz the API End Point and show importence of Content-Type
- Starting SQLMAP then manually fuzzing this application
- SQLite Boolean Injection, with CASE IF/THEN/ERROR

#### Kotarak [Linux]
- For the unintentional method, I'm just downloading a file versus doing it live on the box because I wanted to save doing it live for another video.
- A really good SSRF Presentation: https://www.youtube.com/watch?v=D1S-G8rJrEk
- Start of nmap
- Accessing port 60000
- Manually enumerating ports on localhost via SSRF

#### Mantis [Windows]
- Start of nmap
- Poking at a rabbit hole (8080)
- GoBuster to find hidden directory
- Finding SQL Creds in hidden directory
- Using dbeaver to enumerate database

#### Monitors [Linux]
- Start of nmap
- Looking at the webste, getting a VirtualHost and then navigating to the page and confirming Wordpress
- The wp-content/plugins directory doesn't have an index, don't even need to use wpscan
- Testing the LFI with the plugin
- Using wpscan to enumerate wordpress users

#### OneTwoSeven [Linux]
- Begin of recon
- Examining the webpage
- Discoving SFTP Credentials on the web page
- Playing with the SFTP Server
- Discoving the SymLink command to break out of home directory

#### Oouch [Linux]
- Start the box checking out nmap, seeing an FTP Server with a file hinting at OAUTH
- Poking at the login for the flask application (Port 5000)
- Playing with the Change Password fied, made a mistake which puts me down a rabbit hole
- Checking the Contact page, seeing we get banned with a XSS Attempt but someone will click URL's if we send them
- Creating an account on Authorization.oouch.htb

#### Overflow [Linux]
- Start of nmap
- Taking a look at the website
- Examining the AUTH Cookie and talking about why its unique
- Running FeroxBuster, talking about why I started using it
- Examining the length of the cookie with various usernames to discover the cookie length changes

#### Oz [Linux]
- Start of the box
- Attempting GoBuster but wildcard response gives issue
- Start of doing wfuzz to find content
- Manually testing SQLInjection
- Running SQLMap and telling it exactly where the injection is

#### Patents [Linux]
- Begin of nmap, there's a weird 8888 port.
- Looking at the website, downloading a docx
- Finally running GoBuster, doing the raft wordlist because it has "UpdateDetails"
- Running GoBuster against the "release" directory to get release notes and researching XML and DocX
- Adding an XXE Payload into our Word Document: customXml/item1.xml

#### Phoenix [Linux]
- Start of nmap
- Taking a look at the SSL Certificates and website to find blog/forum
- Running WPScan, explaining why i like aggressive scanning
- Finding public vulnerability in Asgaros Forms (Blind Time Based SQLi)
- Running SQLMap to confirm the injection

#### Pikaboo [Linux]
- Start of nmap
- Discovering the webserver is apache, despite nmap saying it is nginx
- Every request with /admin gets a 401, indication that nginx location may not end with /
- Doing the nginx lfi to grab apache server-stats and leak the /admin_staging/ directory
- Running gobuster in /admin_staging/ to discover more php scripts

#### Player [Linux]
- Begin of recon, wireshark nmap to see how it identified the hostname.  The way this box is configured apache is placing the hostname when the "Host: "
- Starting a bunch of automated tools. Nmap all ports, and gobuster to discover VHOST (virtual hosts) and files.
- Checking dev.player.htb and identify the framework (Codiad) is being leaked in some javascript
- Checking chat.player.htb, nothing really here just hints at source code disclosure on other domains
- Checking staging.player.htb, sending an email leaks some interesting files

#### Pollution [Linux]
- Introduction
- Start of nmap
- Checking out the site, discovering an email (collect.htb) and setting up gobuster
- Discovering forum.collect.htb which is running MyBB, someone uploaded a Burp history file which contains API Information
- Manually examining the BurpSuite Backup File, and discovering it contains full HTTP Requests

#### Proper [Windows]
- Start of nmap and checking the website
- Looking at the web console which shows the page making a request to Products-Ajax.php then playing with the parameters
- If the hash parameter is missing the application errors and leaks the secret key and identifying how it signs
- Using SQLMaps Eval parameter to automate the secure hash generation (Calculated Parameter Bypass)
- Logging into the application with a password from the database and discovering a LFI

#### Quick [Linux]
- Begin of Nmap, examining the page and running gobuster
- Identifying some extra care
- Adding portal.quick.htb to the host file so we can resolve hostname
- Trying to identify if the web application will tell us if an account is valid
- Building an email list based upon clients and then running wfuzz to try and identify valid emails

#### RainyDay [Linux]
- Introduction
- Start of nmap
- Identifying this page is built with flask based upon a 404 page
- Looking at /api/
- Showing a weird bug in python where you cannot run int() on a string that is a float

#### RE [Windows]
- Begin of Recon
- Creating an entry in /etc/hosts for reblog.htb (found on webpage)
- Reading each blog post and taking notes
- Poking at SMB to see MALWARE_DROPBOX
- Digging into why SMBMAP says READ_ONLY.  Don't get anywhere but its an impacket thing?

#### Reel [Windows]
- Begin of Nmap
- Examining the anonymous FTP Directory and discovering email addresses in Meta Data
- Manually enumerating valid email addresses via SMTP
- Creating a "Canary Document" in Word to ping back to our server when a word document is opened
- Generating a malicious RTF Document (CVE-2017-0199)

#### Reel2 [Windows]
- Start of NMAP
- Gobuster using a case insensitive wordlist because windows
- Checking out the application on port 8080, wallstant
- OWA Discovering the Exchange version based upon login interface
- OWA How the "User Enumeration" of Exchange may work... It's time based

#### Registry [Linux]
- Begin of Recon, discovering hostname in SSL Certificate
- Running GoBuster against Registry.htb and Docker.Registry.htb to discover CA Certificate in /install/
- /v2/ on Docker.Registry.HTB requires login, guessing admin:admin and then looking into the Docker Registry API
- Manually downloading a Blob off the Registry and extracting it to reveal files
- A bit more elegant way to do this, configure Docker to use this registry by adding the CA to our Docker SSL Cert Store.  Then downloading the Bolt-Ima

#### Scavenger [Linux]
- Begin of Recon
- Discovering an SQL Injection inside of the WhoIs Service
- Identifying we can perform DNS Zone Transfers with dig axfr (aquatone is the application i mention to take screenshots)
- Explaining the SQL Union Injection
- Dumping information out of Information_Schema via the SQL Union Injection

#### Search [Linux]
- Start of nmap
- Using Kerbrute to identify valid users
- Finding credentials for Hope.Sharp in an image on the website
- Showing Kerbrute paswordspray silently fails when time is out of sync
- Having troubles running the Python Bloodhound Ingestor, a digestmod error

#### Seventeen [Linux]
- Start of nmap
- Taking a look at the website
- Showing some differences between Ffuf and Wfuzz
- Finding a known exploit against the Exam Reviewer Management System
- Explaining the boolean injection then running SQLMap

#### Sharp [Windows]
- Start of nmap
- Running CrackMapExec to discover null authentication and an open share
- Running Spider_Plus with CME then JQ to parse the output
- Looking into KanBan
- Using smbclient to download files

#### Shrek [Linux]
- Examining the Web Page
- Finding /uploads/ Directory
- Finding /secret_area_51/ Directory
- Using Audacity to find Steg in Audio
- FTP With Creds revealed from Steg

#### Spider [Linux]
- Start of nmap
- Adding spider.htb to our host file so we can access the domain name
- Playing with the registration of the website and examining the cookie
- Putting a bunch of bad characters for our username and discovering odd behaviors
- Dumping the configuration via SSTI, can't do a complex SSTI due to username limit

#### Static [Linux]
- Start of nmap
- Noticing there is weird behavior on /vpn, it doesn't direct to the folder /vpn/ probably reverse proxy [MasterRecon]
- Corrupted GZIP, using zcat to view it and fixgz to repair
- Building a Python Script to generate TOTP for MFA (the NTPDate failed because i didn't use -q.  Nmap would have worked with -sV)
- Talking about things I would be monitoring for on Login Forms [Detection]

#### Talkative [Linux]
- Start of nmap
- Taking a look at websites, making note of all login prompts (bolt, rocketchat)
- Start of looking at Jamovi, using the Rj Editor to execute code and get a reverse shell
- Using cat to send files over the network to our box and viewing the bolt-administration document
- Taking a credential from the document and logging into Bolt CMS

#### Tally [Windows]
- Start of NMAP
- Begin of Sharepoint/GoBuster (Special Sharepoint List)
- Manually browsing to Sitecontent (Get FTP Creds)
- Mirror FTP + Pillage for information, Find keypass in Tim's directory and crack it.
- Mounting/Mirroring ACCT Share with found Creds and finding hardcoded SQL Creds

#### Tentacle [Linux]
- Running nmap and giving it capabilities so we don't need to use sudo
- Discovering an email on the SQUID Page
- Running GetNPUsers since Kerberos is running, end up getting a hash we can't crack
- Attempting to enumerate DNS, coming up with nothing
- Using GoBuster to bruteforce DNS Names

#### Travel [Linux]
- Start of recon, discovering a bunch of hostnames in a cert
- Running wpscan against blog.travel.htb
- Running the raft-large-files.txt against blog-dev.travel.htb to discover the git repo
- Using git-dumper to download the git repo
- Examining the git project to discover what it is and where its installed on the webserver

#### Unbalanced [Linux]
- Introduction
- Start of nmap
- Setting Squid up to do a portscan while we work on something else
- Poking at RSYNC and seeing we can download encrypted config backups
- Examining files downloaded from RSYNC, specifically looking at entropy to validate encryption

#### Unobtainium [Linux]
- Start of nmap
- Downloading and installing the deb package with dpkg, then fixing the host file
- Running wireshark when examining the unobtainium application then examining the HTTP Requests
- Proxying the unobtainium app through Burpsuite by creating a new proxy listener and updating the host file
- Playing with the LFI on /todo and discovering we can only cause errors or include files in the local directory

#### Vessel [Linux]
- Introduction talking about how this box is about finding CVE's and building an exploit based upon exploit
- Start of nmap
- Running gobuster and showing the importance of using multiple wordlists.
- Attempting to register an account, which shows the endpoint /api/register but /api/ returns a 404
- Showing that raft-small-words wordlist won't discover .git but commons.txt will because commons has .git/HEAD

#### Zetta [Linux]
- Begin of NMAP, then examining FTP to see the banner leak time and IPv6 compatibility.
- Running GoBuster so we always have recon running in the background
- Examining the Web Page to see it has some usernames and FTP Creds
- Logging into FTP and testing basic things like downloading/uploading files
- Ran out of things to test. Run NMAP on all ports, then look into things we don't know.

#### Zipper [Linux]
- Start of NMAP
- Signing into Zabbix as Guest
- Getting potential usernames from inside Zabbix and guessing creds
- Running Searchsploit and looking for vulnerabilties
- Analyzing the "API" Script from SearchSploit as we have API Creds

</details>

### Insane (39 machines)

<details>
<summary>Click to expand Insane machines</summary>

#### Absolute [Windows]
- Start of nmap discovering Active Directory (AD)
- Using wget to mirror the website, then a find command with exec to run exiftool and extract all user names in metadata
- Using Username Anarchy to build a wordlist of users from our dump and then Kerbrute to enumerate valid ones
- Building Kerbrute from source to get the latest feature of auto ASREP Roasting
- Kerbrute pulled the wrong type of hash, using the downgrade to pull etype 18 of the hash

#### Anubis [Windows]
- Start of nmap, getting hostname and
- Discovering the Server Header changes for virtualhost, probably navigating to a different box/container/etc [MasterRecon]
- Getting a good SSTI Fuzz String then identifying this string causes an error on the webserver. Removing parts of the string until we see the type of S
- Playing with ASP Code in this SSTI or ASP Code Injection... Not sure what the vulnerability is
- Getting a VBScript One Liner to execute code and then getting a reverse shell

#### APT [Windows]
- Start of nmap and poking at the webserver
- Looking into MSRPC, showing MSF info overflow which is why I had historically ignored it
- Poking at RPC with Impacket's RPCMap
- Converting a RPC Script to get IPv6 address from Python2 to Python3
- Using nmap to scan the IPv6 Address

#### Ariekei [Linux]
- Explaining VM Layout
- Poking at Virtual Host Routing (Beehive & Calvin)
- Fixing GoBuster to find /cgi-bin/
- Enumerating WAF (Web Application Firewall), to see how it detects Shellshock
- Using VirtualHostRouting to navigate to Calvin.htb.htb

#### Attended [Linux]
- Showing a tmux keybinding to
- Setting up an IPTables rule to log new connections
- Using SWAKS to send an email
- Starting up a python SMTP Server so we can see the email coming back to us
- Finding a VIM RCE and verifying it works by using ping

#### BankRobber [Windows]
- Begin of nmap, discover XAMPP
- Running GoBuster while we poke at the website
- Registering an account then seeing what new functions are avaialble
- Attempting to transfer money and discovering XSS
- Basic Cross Site Scripting worked, check cookies to see HttpOnly is false then do a basic XSS to steal cookies

#### Bighead [Windows]
- Begin of Nmap
- Pulling important information from the website
- Discovering DNS Names, adding stuff to /etc/hosts
- Odd behavior with code.bighead.htb, redirects us to 127.0.0.1; change that with Burp
- Using wfuzz to dirbust, with the ability to see HTTP Codes (hunting for 418)

#### Brainfuck [Linux]
- Start of WP Hacking
- Logged into WP
- Login to SuperSecretForum
- Cracking the SSH Key
- Begin of getting root.txt (RSA Cracking)

#### Crossfit [Linux]
- Installing Obsidian which lets us take notes in Markdown format
- Running nmap to see FTP over SSL and it has certificates
- Using openssl to grab the SSL Certificate from FTP
- Going over the web page extracting emails, people, and user input locations
- Installing flameshot, which helps us take better screenshots

#### Crossfit2 [Linux]
- Start of nmap and poking at website.  Browser Developer Window shows WebSockets + Hostname
- Setting up full portscan and gobuster while we poke at the box, to always have recon running
- Ussing ffuf to fuzz for emails (Forgot to set header here, we look at it later)
- Playing with the websockets in BurpSuite, discovering SQL Injection
- Creating a python program to aid our SQL Injection

#### CTF [Linux]
- Support me on Patreon! https://patreon.com/ippsec
- Start of Recon, discovering CentOS Version via HTTPD Version
- Checking out the HTTP Page
- Checking out login.php
- Identifying a Secure Token is used, most likely STOKEN

#### Dyplesher [Linux]
- Start of the box, running nmap with all ports.
- Using a Google Image Search to map icons with applications
- Manually fuzzing test.dyplesher.htb to check if there's any easy vulns
- Running NMAP Scripts against the results of our full port scan with awk and ORS
- Discovering a .git repo exposed on the website, using git-dumper to download it

#### Ethereal [Windows]
- Begin of Recon, Downloading FTP and inspecting websites
- Recap of what we saw on the recon. Limited pages that provide paths for exploitation, Server Hostname, and FTP
- Sending MD5Hashes to VirusTotal to get file age
- Downloading PasswordBox sourcecode to examine pbox.dat and discover a password manager.
- Use Hydra to try to bruteforce ethereal.htb:8080, find blind command injection in page by running various ping commands but no way to view output.

#### Fatty [Linux]
- Using wget to recursively download files off an annonymous FTP Server
- Attempting to execute the Java Thick Client, then switching to Java version 8 and trying again
- Seeing the Thick Client makes some DNS Requests, make the DNS Request resolve and attempt to intercept with Burp
- BurpSuite failed us, using SOCAT to forward the traffic and exploring the Thick Client features
- Using CFR to decompile a Java JAR File then VS Studio Code to analyze the source

#### Fighter [Windows]
- Begin of Recon Nmap, Identify OS Version, Check out Page to find hostname is streetfighterclub.htb.
- Using GoBuster and WFUZZ to identify: members.streetfighterclub.htb and members.streetfighterclub.htb/old/login.asp
- Begin poking around the members.streetfighterclub.htb page - Find SQL Injection
- Boolean injection to force the query to return "valid login".  Play with logins to find it always returns to "Service not available"
- Testing Union Injections for easy exfil of data

#### Fingerprint [Linux]
- Start of nmap, checking websites seeing old copyrights
- Discovering the HTTP Redirect on /login is pretty big, so its likely an EAR Vulnerability
- Discovering a LFI that enables us to read source code, chaining it with the proc directory and using wfuzz to discover additional python files
- While our wfuzz runs testing against a login endpoint to discover an XSS in another webapp
- Going over the Python Source code

#### Fortune [Linux]
- Begin of recon
- Exploring the web page on port 80
- Using wfuzz to do a special character fuzz to identify odd behavior and discover command injection
- Creating a hotkey in Burpsuite to send requests in repeater pane
- Start of creating a python program to automate this

#### Fulcrum [Linux]
- Begin of Recon
- XXE Detection on Fulcrum API
- XXE Get Files
- XXE File Retrieval Working
- Lets Code a Python WebServer to Aid in XXE Exploitation

#### HackBack [Windows]
- Begin of Recon, discovery of an HTTP API that has a few commands
- Using JQ to parse json output, use NetStat/Proc to find GoPhish
- Logging into GoPhish with default creds admin:gophish, finding DNS Names
- Discovery of Obfuscated JavaScript Deobfuscating it to find a hidden section
- Using wfuzz to bruteforce the password for webadmin.php

#### Jail [Linux]
- Recon - NMAP
- Recon - Getting Linux Distro
- Recon - GoBuster
- Analyzing Jail.c source
- Begin Binary Exploitation

#### Kryptos [Linux]
- Begin of Recon
- Examining login request while GoBuster runs
- Noticing weird behavior by modifying db parameter in login request
- Finding what the Error numbers mean. (SQL Error Codes)
- Testing if we can trick the application into authentication against us

#### Laser [Linux]
- Running nmap
- Discovering port 9100, and poking at it with nmap/pret
- Got access to the printer via PRET, dumping print jobs
- Running ENT to see the entropy is 7.99 which means it is probably encrypted... Then doing the same thing in Cyber Chef
- Discovering the encryption algorithm via inspecting variables on the printer. Then dumping the memory of the printer to get the AES Key and trying to 

#### Minion [Windows]
- Every time I saw CSRF, I means SSRF.
- Begin of Recon
- Start of GoBuster
- Finding a SSRF
- Passing arguments to cmd.aspx via SSRF

#### Mischief [Linux]
- Begin of NMAP
- Extra nmaps, SNMP and AllPorts
- Playing with OneSixtyOne (SNMP BruteForce)
- Looking at SNMPWalk Output
- Installing SNMP Mibs so SMPWalk is readable

#### Multimaster [Windows]
- Begin of nmap, going over what videos show KRB/LDAP/SMB enumeration
- Checking out the web page, finding an API that allows us to search employees
- Extracting usernames from the database using the above API
- Using wfuzz to fuzz this endpoing and discover there's a WAF that blocks us on BruteFoce and special characters
- Sending wfuzz to burpsuite so we can see why the page is giving us an HTTP 415 (hint: Its content-type!)

#### Nightmare [Linux]
- Edit: Whoops forgot @stefano_118 helped create this machine!
- Start of Recon
- /documents and /secret rabbit hole enumeration
- Using wfuzz on the /secret rabbit hole to find argument for download.php
- Begin of Web Application Enumeration, some XSS Found

#### Nightmarev2  - Speed Run/Unintended Solutions [Linux]
- Original Video with In-Depth Explanations of Intended Solution: https://youtu.be/frh-jYaUvrU
- End of intro, Start of nmap
- Playing with Second-Order Union Injection
- Dumping all users
- Converting SFTP Exploit from 64bit to 32bit

#### Perspective [Linux]
- Start of nmap
- Looking at the website, looks like there's different behavior for extensions
- Registering and logging into an account
- An unintended way to login, IDOR within the Forgot Password logic, can change usernames
- Uploading a new product, test XSS, File Upload

#### PivotAPI [Windows]
- Start of nmap, downloading files over FTP
- The contents of all the PDF's don't really help. Using exiftool to extract authors.
- Using Kerbrute to bruteforce valid users and getting ASREP Hash. It is ETYPE 18, which hashcat doesn't support. Use downgrade to generate ETYPE 23 and
- Going into what ETPE Means
- Using CrackMapExec to dump a list of file shares, then using Spider_Plus plugin to dump files

#### Rabbit [Windows]
- Begin of Recon (nmap, setting hostname, dns, nmap, ipv6)
- Checking websites (80,443,8080)
- Attempting to enumerate users of OWA-2010 (Fails)
- Checking out Joomla Version (/administrator/manifets/files/joomla.xml)
- Using SearchSploit with (Complain Management System)

#### Reddish [Linux]
- Begin of Recon (Port Scans)
- Reverse Image Searching an favicon to get application used
- NODE-RED: Reverse Shell Returned
- NODE-RED: Running IP and Port Scans to identify lateral movement targets
- Downloading Chisel (Go Program for Tunnels).

#### Response [Linux]
- Start of nmap
- Discovering the /status/ page which gives us some information on how to use the Proxy
- Start of coding our own proxy
- Downloading the source code to the chat application
- Modifying our proxy to forward all requests to chat.reponse.htb and adding a webserver to it

#### Rope2 [Linux]
- Start of nmap
- Checking out the webpages, find Gitlab and Page about a custom chrome
- Viewing the Git log for the custom v8 javascript project and finding the vulnerability
- Finding an XSS in Contact Us
- Using the banners to find what version of Ubuntu the target is using

#### Scanned - Escaping and Exploiting Chroot Based Jails via Unprotected File Descriptor [Linux]
- Start of nmap
- Using MSFVenom to upload a reverse shell to identify what the malware sandbox looks like
- Examining the source code of the sandbox
- Creating a program in C to see the size of an unsigned long
- Creating a program to replace the output of the trace program and exfil data via the return register on the webapp

#### Sink [Linux]
- Start of nmap, finding version of gunicorn is from 2019
- Enumerating the Gitea version (the 404 error page shows it)
- Trying to find the Gitea version another way (HTTP Files)
- Downloading jquery.js, grabbing the md5, then using VirusTotal to get an idea when it was released
- Looking at the second website (Running on gunicorn)

#### Sizzle [Windows]
- Begin of Recon
- Checking the web interfaces
- Discovering there is a Certificate Authority
- Taking a look at LDAP
- Examining SMB to find shares

#### Smasher2 [Linux]
- Begin of Recon
- Using Wireshark to see why Nmap said HTTP 403
- Running GoBuster to identify /backup
- Performing a DNZ Zone Transfer with dig axfr
- Manually playing with the login form to hunt for SQL Injection

#### Stacked [Linux]
- Start of Nmap
- Start of gobuster to enumerate VHOST and Files
- Showing how I like to find the needles in a haystack when it comes to parsing lots of data.
- Using google reverse image search to try to identify what a logo means
- Hunting for XSS, putting unique URL's in all fields (check for a callback later)

#### Toby [Linux]
- Start of nmap
- Discovering backup.toby.htb and discovering GOGS
- Discovering a backup project in toby-admin, which is wordpress
- Downloading and running php malicious file scanner and finding a backdoor in the web code
- Finding the backdoor in comment.php and finding out its packed a bunch of times. Using a loop to get it back to the original code.

</details>

### Untagged (197 machines)

<details>
<summary>Click to expand Untagged machines</summary>

#### Academy Intro 
- Academy URL: https://academy.hackthebox.eu
- Accessing Academy
- Talking about Paths
- Talking about what a Cube is
- Showing all the modules and tiers

#### Administrator 
- Introduction, assumed breach box
- Start of nmap
- Checking out what the credentials we are given go to, see WinRM but it doesn't give us much
- Running python bloodhound as olivia
- Looking at the json output manually to discover non-default groups

#### Aero 
- Introduction
- Start of nmap
- Looking for Windows Exploits around Themes and discovering ThemeBleed (CVE-2023-38146)
- Creating a DLL that exports VerifyThemeVersion and then compiling from Linux
- Showing the exports of the DLL to confirm it is there, then hiding the ReverseShell export

#### AI 
- Begin of Recon
- Taking a look at the page, noticing the site is PHP, running GoBuster to find other PHP Files.
- Playing with the File Upload, failing to identify how uploaded files are stored
- Investigating PHP Files that GoBuster found, discovering intelligence.php
- Searching for Text to Speach programs (create WAV Files)

#### Alert 
- Introduction
- Start of nmap
- Enumerating the Link_Share for Directory Traversal, coming up with nothing
- Discovering XSS in the Contact Us Form
- Playing with the XSS, we keep getting extra URL Encoded data turns out its not XSS but instead the admin is clicking links

#### Analysis 
- Introduction
- Start of nmap
- Discovering the internal.analysis.htb subdomain
- Talking about why I want to run FeroxBuster here and showing the menu so we can stop crawling non-interesting directories (ex: js, css, img)
- Discovering list.php in users and fuzzing parameters

#### Analytics 
- Introduction
- Start of nmap
- Discovering Metabase, noticing the HTTP Headers are different. Checking TTL just to see if it decrements from the main web page.
- Searching for an exploit for metabase, then enumerating version
- Manually exploiting Metabase by pulling the setup-token, then getting injection on the /setup/validate endpoint through the JDBC Driver

#### Apocalyst 
- Enumeration Start
- WPScan Start
- Directory Scanning with GoBuster
- Examining WPScan Output
- Bruteforcing with WPScan

#### AppSanity 
- Introduction
- Start of nmap, showing 5985 isn't in the top1000 so doing a full port scan
- Taking a look at the MedDigi website
- Taking a look at the Signup Request seeing AcctType
- Changing the AcctType to 2 and getting a different privilege

#### Aragog 
- Start of Recon
- Notice SSH configured for Pub Key Only.  Hint at what to grab later!
- Grabbing test.txt off ftp server via anonymous auth
- Determining if I want to go down the "Exploit VSFTPD" rabbit hole
- Viewing test.txt and hosts.php

#### Artificial 
- Introduction
- Start of nmap
- Looking at Upload Modules, can see the version of python/tensorflow looking for a way to get RCE in tensorflow h5 files
- Using docker to run the tensorflow, mounting our cwd in the docker to make it easy to copy files from the docker image
- Shell returned, looking at the database to get a password hash and cracking it to get another user

#### Authority 
- Introduction
- Start of nmap
- Taking a look at the website
- Using NetExec to search for file shares and discovering the Development share is open. Using smbclient to download everything
- Exploring the Ansible Playbooks in the Development Share to discover encrypted passwords (ansible vault)

#### Axlle 
- Introduction
- Start of nmap
- Looking at what an XLL Is
- Finding a skeleton xll payload, then compiling it on Linux
- Shell returned, grabbing the NTLMv2 Hash of our user with responder

#### Backfire 
- Introduction
- Start of nmap
- Showing Havoc adding the X-HAVOC true header on GET/POST requests on its HTTP Hosting Service
- Seraching CVEDetails finding CVE-2024-41570 which is a SSRF
- Some quick C2 talk before we dive into the SSRF

#### Bank 
- Nmap Results
- DNS Enumeration
- HTTP VirtualHost Routing
- DirSearch (Web Enumeration)
- HTTP Redirect Vulnerability

#### Beep 
- Watch me fail my way to victory as I exploit beep 4 different ways.  Next time I try to exploit something multiple ways, I'll probably split it up in 
- Method 1: LFI + Password
- Method 2: Turning LFI into RCE
- Method 3: Code exec via call
- Method 4: Shellshock

#### BigBang 
- Introduction
- Start of nmap
- Discovering BuddyForms on Wordpress, manually discovering the version (before this we ran WPSCAN aswell)
- Finding a BlogPost showing a File Disclosure Vulnerability in BuddyForms and they used a Phar Deserialization trick to get RCE but this doesn't work o
- Playing with the File Disclosure, using a PHP Filter Chain to prepend GIF89a to our file and show we can trick the magic byte trick

#### Bitlab 
- Begin of recon
- Taking a loot at the webserver and seeing a GitLab signin page
- Using wget and exiftool to check metadata on files on the server to see when stuff was uploaded
- Running gobuster, explaining why we need the Wildcard flag on this box for this tool to work
- Finding the /help directory which has some javascript that contains the password to GitLab

#### Bizness 
- Introduction
- Start of nmap
- Seeing JSESSIONID and NGINX trying the off by slash exploit to get access to /manager, doesn't work here
- Dirbusting with FFUF because the lack of 404's messed with gobuster
- Discovering the OfBiz Version, looking for exploits

#### Blazorized 
- Introduction
- Start of nmap
- Examining the website looking for interesting functionality
- The check updates page loads a unique DLL and puts a JWT in the request
- Opening Blazorized.Helpers.Dll with ilSpy to discover a hardcoded JWT

#### BlockBlock 
- Introduction
- Start of nmap
- Registering an account and discovering the chat, examining source and seeing a database solidity contract
- Testing for XSS, discovering it within the username
- The /api/info page exposes the JWT, which lets us exfiltrate it even if HTTPONLY is set

#### Blocky 
- The STTY command I messed up was simply `stty rows ## cols ##`
- Begin Recon with Reconnoitre
- Examining findings from Reconnoitre
- Decompiling java Jar Files with JAD
- Using JD-GUI

#### Blurry 
- Introduction
- Start of nmap, then gobuster to do a vhost scan
- Enumerating RocketChat version by looking at the version of Meteor it uses
- Registering for a RocketChat Account then reading the chat to get information about ClearML
- Logging into ClearML, looking at the project to see some scripts which are running

#### Boardlight 
- Introduction
- Start of nmap
- Running a VHOST Scan to discover CRM Subdomain
- Discovering Dolibarr is running at version 17.0.0 which is vulnerable to CVE-2023-30253
- Discovering default credentials of admin:admin work then running the exploit

#### Bookworm 
- Introduction
- Start of nmap
- Discovering a potential XSS in the Notes field of an order. Content Security Policy (CSP) blocks us, because JS cannot be on the same page. Looking fo
- Finding out we can upload anything we want to the avatar. This should allow us to bypass the CSP in the book edit field
- Confirmed XSS on the page, checking if there's an IDOR Vulnerability that allows us to add notes to other people's items by creating a second account

#### Broker 
- Start of nmap
- Logging into ActiveMQ with admin:admin and then failing to use the exploit from 2016
- Doing a full nmap scan, then running script scans on the open ports
- Finding a page that talks about CVE-2023-46604, the latest activemq exploit
- Pulling down an exploit payload for this exploit, it is golang

#### Builder 
- Introduction
- Start of nmap
- Looking at Jenkins Advisory 3314 (CVE-2024-23897), which has a File Read vulnerability in the CLI. Then downloading the Jar
- Explaining the Vulnerability with a quick demo
- Creating a really nasty bash script to fuzz many of the Jenkins Paramaters to see which produce the most number of lines

#### Busqueda 
- Introduction
- Start of the nmap
- Copying the request in burpsuite to a file so we can use FFUF to fuzz
- Just testing for SSTI
- Found two bad characters, putting a comment after a bad character to see where it is failing

#### Canape 
- Start of Recon, nmap and poking around the website
- Dirbusting a site that always respond 200
- Switching to a different Wordlist (SecLists/Discovery/Web/Common)
- Discovery of .git - Poking around to clone it and download
- Downloaded .git, examining commit history

#### Caption 
- ** See Pinned Comment for Root Shell.
- Introduction
- Start of nmap
- If you want to learn more about Varnish check out Forgot
- Looking at the Git Repo, discovering the Infra stack HAProxy, Varnish, Flask

#### Carrier 
- Begin of Recon
- Checking out the Web Page
- Doing UDP/GoBuster Scans
- Running SNMPWalk and then logging into web interface
- Reading the tickets on the web page

#### Cat 
- Introduction
- Start of nmap
- Taking a look at uploads at the website starting with upload functionality
- Discovering .git directory, using git-dumper to grab the source and examining the code behind upload to see it is likely not vulnerable
- Testing for XSS in username, getting admin cookie upon submitting a cat to the site

#### Celestial 
- Begin of Recon
- Looking at the web application and finding the Serialized Cookie
- Googling for Node JS Deserialization Exploits
- Start of building our payload
- Examining Node-Serialize to see what the heck _$$ND_FUNC$$_ is

#### Cerberus 
- Introduction
- Start of nmap
- Looking at the TTL of Ping to see its 127, then making a request to the webserver and seeing it is 62
- Showing DNS is listening on Cerberos and exposing the 172.16.22.0/24 network
- Looking at Icinga, testing default credentials

#### Certificate 
- Introduction
- Start of nmap
- Checking out the website and registering a user
- Discovering upload functionality, that lets us upload PHP Files. Explaining what a Null Byte will may do in a zip file
- Using BurpSuite to manipulate the hex and add a Null Byte in the filename shell.php..pdf, so when unzipped it becomes shell.php

#### Certified 
- Introduction
- Start of nmap discovering only Active Directory (AD) Related ports
- Running Certipy both with and without the vulnerable flag
- Outputting Certipy to JSON and then writing a JQ Query that will show us non-default users that can enroll certificates
- Explaining the JQ Query that will take the list, filter out specific words, then show us items that still have an item

#### Chainsaw 
- Begin of recon
- Downloading and analyzing the files off the anonymous FTP Directory
- Looking into solidity to see what these files are about
- The full portscan finished, trying to find out what port 9810
- Recommended reading to understand blockchain fundamentals

#### Chaos 
- Begin of recon
- Starting up GoBuster then editing /etc/hosts to add the hosts in nmap
- Going over the website
- Discovering a wordpress instance (/wp/ form goBuster)
- Finding webmail credentials from a wordpress Protected Post

#### Charon 
- Rabbit Hole - Searching for SuperCMS
- Running enumeration in the background (GoBuster)
- Rabbit Hole - SQLMap Blog SinglePost.php
- Finding PHP Files in /cmsdata/ (GoBuster)
- Manual Identification of SQL Injection

#### Checker 
- Introduction
- Start of nmap
- Enumerating version of Bookstack by the HTML Source, it's part of the CSS Include
- Enumerating Teampass version by looking at github, discovering changelog.txt
- Looking at vulnerabilities in Teampass finding an SQLInjection on cvedetails

#### Chemistry 
- Introduction shorter than normal since I did this blind
- Start of nmap
- Looking at the webpage, see CIF Analyzer
- Finding an exploit script, testing out with ping and getting a ping
- Having trouble getting a reverse shell, end up curling a file

#### Cicada 
- Introduction
- Start of nmap
- Running NetExec discovering an open share (HR), which contains a password for new hires
- Using NetExec to list accounts via RID Brute Force and explaining how it works under the hood with RPCLient
- Some VIM-Fu to convert the NetExec output to show only a list of users and performing a password spray

#### Clicker 
- Introduction
- Start of nmap and discovering NFS, which is hosting source code to the webserver
- Showing off the NFSClient Golang binary by Mubix, does not work here because NFS is Read-only
- Viewing the website for the first time, so we have an idea of what source code we are looking at
- Looking at the source code, Snyk doesn't give us anything

#### Code 
- Introduction
- Start of nmap
- Navigating to the page and discovering we can run Python Code but there is a filter blocking certain words
- Walking through filter evasion with python, showing loaded classes
- Calling popen to run a command

#### CodePartTwo 
- Introduction
- Start of nmap
- Website is opensource, taking a look at the source code
- The website uses js2py and the version running is vulnerable to CVE-2024-28397, which is a sandbox escape
- Shell returned on the website, dumping the SQLite database to get Marco's password

#### Coder 
- Introduction
- Start of nmap
- Exploring the file share
- Finding Encrypter.exe, which is a dotnet encrypter.  Discovering the seed is based upon time, modifying it to decrypt using metadata from the encrypte
- The encrypted file was a Keepass Database, looking into it and seeing credentials and a uthenticator backup

#### Codify 
- Introduction
- Start of nmap
- Playing with the Javascript Editor, discovering filesystem calls are blocked
- Discovering the sandbox is vm2, going to github discovering it is discontinued with known security issues
- Getting code execution, then a reverse shell

#### Compiled 
- Introduction
- Start of nmap
- Entering our IP Address into the website and viewing the request within NC to see the useragent (git/2.45.0.windows.1)
- Going over CVE-2024-32002 which is a RCE within Git on case insensitive file systems
- Creating the malicious git project

#### Corporate (FIXED) 
- Sorry for the double upload. The last 45 seconds were missing from the first video.
- Introduction
- Start of nmap
- Playing with the Agent Chat, discovering we can send HTML then testing for XSS then seeing CSP (Content Security Policy) Stops us
- Testing for the ability to perform redirection via HTML via meta refresh

#### CozyHosting 
- Introduction
- Start of nmap
- Identify JSESSIONID with nginx, but nginx appears to be configured correctly
- Googling the error message to identify the page uses SpringBoot, using a SpringBoot wordlist to find actuators!
- Using the Sessions Actuator and seeing a session for kanderson, logging in to get to the admin interface

#### Craft 
- Begin of recon
- Checking out the HTTPS Certificate for potential hostnames
- Looking at api.craft.htb, appears to be some type of Documentation for the REST API
- Looking at gogs.craft.htb, no known exploits but there is some source code!
- Checking out the Git Issues, seeing Dinesh put a JWT Token in a comment. Checking the token out

#### Crafty 
- Introduction
- Start of nmap
- Doing a full nmap scan, then scanning the minecraft ports with scripts to discover minecraft version
- Discovering this minecraft version is vulnerable to Log4j
- Extracting Java Version/Class Path/etc via Log4j

#### CriticalOps 
- HackTheBox is running a Bug Bounty themed CTF, HackTheSystem June 27-29 2025. These challenges are all based on real bug bounty reports. There are two
- HackTheSystem - Bug Bounty CTF: https://ctf.hackthebox.com/event/details/hack-the-system-bug-bounty-ctf-2508
- HackTheSystem Teaser Playground: https://ctf.hackthebox.com/event/details/hack-the-system-bug-bounty-ctf-playground-2509
- NovaEnergy Challenge w/ 0xdf:   https://www.youtube.com/watch?v=Ru5toDyKNjg
- Introduction

#### CyberMonday 
- Introduction
- Start of nmap, playing with the webapp discovering it is Laravel PHP App
- Discovering /assets is a redirect to /assets/, indicator of the Nginx off by slash [MasterRecon]
- Using the Nginx off by slash to download .env and .git to get the source code to the app
- Start of code analysis

#### Cypher 
- Introduction
- Start of nmap
- Sending a single quote in login and causing an error that has a stack trace tied to it, can see the cypher query it is running
- Forcing the Cypher Query to return true creating an authentication bypass in cypher queries
- Also showing we can exfiltrate data through out of band injection with LOAD CSV in cypher queries

#### DarkCorp 
- Introduction
- Start of nmap
- Discovering the Contact Us form lets us send emails anywhere, also leaks the bcase user to the recipient
- Discovering RoundCube Version and finding it is vulnerable to XSS, testing it against ourself with the contact us form
- Building a XSS CSRF Payload that will exfil all emails in the inbox

#### Derailed 
- Start of nmap
- Looking at the HTTP Headers, discovering Cross Origin and rails
- Testing the Clip Notes functionality for SSTI/XSS
- Using FFUF to fuzz all Clip Notes to see if there's an IDOR Vulnerability
- Looking at how the site is build, discovering Web Assembly

#### DevOops 
- Start of Recon
- Start of GoBuster
- Looking at /upload, testing with a normal XML File
- Valid XML File created, begin of looking for XML Entity Injection XXE
- XXE Returns a a local file off the server

#### Devvortex 
- Start of nmap
- Discovering dev.devvortex.htb is a Joomla Page, showing JoomScan and enumerating version manually through manifests
- Looking for Joomla Exploits for version 4.2.6, discovering a way to view application config as an unauthenticated user
- Start of deep dive into the exploit, looking at commits on the day the advisory said this was patched
- Showing the fix just shows it is a mass assignment vulnerability, looking at how this works

#### Dog 
- Introduction
- Start of nmap, discovering an open .git directory
- Using git-dumper to download the source code and discovering MySQL credentials
- Trying to enumerate usernames but running into bruteforce protection in the login and reset password functionality
- Looking for other ways to enumerate users, finding BackDropScan which shows another endpoint which is unprotected

#### Down 
- Start of nmap
- Entering our IP Address in the "Is it Down" and see the server makes a curl back to us, trying command injection
- Could not do Command Injection, trying Argument Injection
- Bypassing the filter that requires the URL to start with http://  by using a space and then using file:// to get file disclosure
- Reading the source of index.php, discovering it has a hidden mode that lets us swap curl for netcat

#### Download 
- Introduction
- Start of nmap
- Playing with the download file functionality, discovering the UUID is the file on disk and not column in database by prepending a slash
- Finding a File Disclosure vulnerability, extracting application source code, getting source code of the app
- Start of signing our own cookies, examining the sig cookie to discover it is 40 bytes which is likely sha1

#### Drive 
- Introduction
- Start of nmap
- [MasterRecon] Examining CSRF Cookie to discover it is likely Django
- Using FFUF to bruteforce ID's of uploaded files, can discover valid ID's but not view the ID itself
- Accidentally deleting something important when FUZZING, always be careful of what you are doing with tools

#### Editor 
- Introduction
- Start of nmap
- Noticing the docs link which directs us to xwiki which discloses its version, searching for vulnerabilities
- Looking into XWIKI CVE-2025-24893
- Got Code Execution, getting a reverse shell now

#### Editorial 
- Introduction
- Start of nmap
- Discovering the webserver is likely running Flask
- Discovering a SSRF in the request to publish books, showing we could leak the servers IPv6 Address but its not too useful here
- Using FFUF to fuzz all open ports on localhost to discover port 5000 is open which is an API Server

#### Enterprise 
- Begin of recon
- Finding the vulnerable Wordpress Plugin
- Exploiting lcars plugin
- Logging into WP and Getting Reverse Shell
- Wordpress RevShell Returned

#### Environment 
- Introduction
- Start of nmap
- Discovering that Laravel is running based upon 404 page (or cookie)
- Running GoBuster, adding 403 to the ignore list of codes and discovering /upload
- Laravel running in DEBUG mode, so the error page gives verbose info. Searching for CVE's for Laravel 11.30.0

#### Era 
- Introduction
- Start of nmap
- Discovering the file subdomain
- Bruteforcing files to find login.php
- Bruteforcing ID's on the download functionality, discovering two other files

#### EscapeTwo 
- Introduction
- Start of nmap
- Doing some low-priv AD recon with NetExec (SMB, MSSQL, User Dump, Shares, Bloodhound, etc)
- Looking at the Spider_Plus output and seeing two interesting excel files
- Cannot open the Excel, unzipping it to look at the files manually and discover the SA password to MSSQL

#### Eureka 
- Introduction
- Start of nmap
- Discovering the default 404 page of Springboot, then using GoBuster with a Springboot wordlist to show actuator endpoint
- Showing a good blog post about Actuator Misconfigurations
- Downloading the heapdump, while that downloads, showing Nuclei will show this with default options

#### Europa 
- Image in the intro is an XKCD comic if you didn't immediately recognize it as XKCD check out https://xkcd.com
- Recon with Sparta
- Enumerating SSL Certificate
- Manually View SSL Certificate
- VirtualHostRouting Explanation

#### EvilCUPS 
- Introduction
- Start of nmap
- Examining the CUPS Management Interface on TCP Port 631
- EvilSocket's blog, explaining the four CVE's and how they are utilized in our attack chain
- Showing the GHSA Advisory that had the initial POC that I had trouble getting working

#### Fluffy 
- Introduction
- Start of nmap
- Running NXC with the credentials we are given and kerberoasting
- Running Rusthound, still not finding all that much
- Looking at file shares, discovering a PDF on a writable share that states the server is vulnerable to CVE-2025-24071

#### Flux Capacitor 
- Begin of recon
- Wiresharking NMAP to identify fingerprint
- Checking the WebPage
- Finding /sync and why web browser has a 403
- Using wfuzz to find what arguments /sync takes

#### Format 
- For some reason, the last video got stuck encoding on YT's side and was 360p. Reuploaded and it worked the second time.
- Introduction
- Start of nmap
- Downloading source code from gitea
- Examining the website via browser to see what it does

#### FormulaX 
- Introduction
- Start of nmap
- Examining the Change Password functionality
- Discovering XSS In the Contact Form
- Building an XSS Cradle that manipulates the DOM to load an external JS file

#### Freelancer 
- Introduction
- Start of nmap
- Discovering the website is Django, Wappalyzer tells us but also talking about how we could manually identify with the help
- Creating an account, discovering we need to activate it, using Forgot Password to activate it
- There is a QR Code that lets users login by scanning it, looking at the URL it appears there could be an IDOR

#### FriendZone 
- Begin of Recon
- Running SMBMap to identify and crawl file shares
- Downloading creds.txt from an smb share and checking FTP/SMB
- Checking the webpage and grabbing potential DNS Names for the box
- Using dig to perform a DNS Zone Transfer to obtain additional host names

#### Ghost 
- Start of nmap
- Taking a look at all the websites
- Showing why you should be careful when enumerating VHOSTS, also using gobuster in DNS mode since there are multiple web services and a DNS Server
- Discovering LDAP Injection in intranet page
- Showing how our LDAP Injection is boolean injection which lets us enumerate data in LDAP

#### GiveBack 
- Introduction
- Start of nmap
- Adding the API Key to our WPScan
- Discovering a POC for the GiveWP plugin and getting a shell
- Looking at the WP Database, not getting much information

#### Gofer 
- Introduction
- Start of nmap
- Running gobuster to discover the proxy.gofer.htb subdomain
- Enumerating SMB to find a note which gives an email address to send a malicious document to and hints at HTTP Methods being filtered
- Discovering the proxy.gofer.htb domain responds differently to POST vs GET requests, then gobustering setting our method to POST

#### Greenhorn 
- Introduction
- Discovering Pluck CMS, getting the version then looking for exploits
- Finding Pluck's password in Gitea (iloveyou1)
- Logging into pluck and uploading a php shell as a module
- Shell returned on the box

#### Guardian 
- Introduction
- Start of nmap
- Discovering the portal.guardian.htb sub domain, there is a PDF here that shows the default password. Failing to enumerate valid accounts.
- Using FFUF to Bruteforce all accounts with the default password of GU1234
- Logging into the application, doing some quick notes of what functionality is exposed

#### Hacknet 
- Introduction
- Start of nmap
- Looking at Wappalyzer's technologies folder to see how it is detecting Django (csrfmiddlewaretoken)
- Showing Nuclei doesn't crawl any pages when it tried to detect tech
- Signing up for the site, playing with SSRF

#### HackTheBox UniCTF 2022  Talk - Variable is what you make of It 
- Introduction
- Hacking is an Art
- The "Flow Chart" Problem most People Make
- Keep is Simple, don't go straight to the reverse shell
- Ask Simple Questions, Start of Fuzzing

#### Haircut 
- Exploiting exposed.php
- Getting Shell
- Screen Privesc

#### Hathor 
- Start of nmap
- Navigating to the page
- Discovering the forgot password feature enables people to enumerate valid users
- Finding the default credentials for mojo portal and then logging in as admin
- Uploading an ASPX Webshell but finding out the aspx extension is blacklisted

#### Hawk 
- Begin nmap, discover FTP, Drupal, H2, and its Ubuntu Beaver
- Checking FTP Server for hidden files
- Examining encrypted file, discovering encrypted with OpenSSL and likely a block cipher
- Creating a bunch of files varying in length to narrow likely ciphers down.
- Encrypting all of the above files and checking their file sizes

#### Haze 
- Introduction
- Start of nmap
- Discovering splunk is version 9.2.1 from port 8089 and searching CVE Databases to find CVE-2024-36991
- Looking at how the File Disclosure works in CVE-2024-36991
- Extracting Splunk Secrets to get a username and password

#### Headless 
- Introduction
- Start of nmap
- Examining the cookie, measuring entropy with ent
- Testing the Contact Support form, putting HTML in the message triggers Hacking Attempt Detected
- Examining the /dashboard, playing with the cookie to see if we can view it

#### Heal 
- Introduction
- Start of nmap
- Discovering the version of LimeSurvey running by comparing the git with what is running
- Finding a File Disclosure in the export functionality of the RAILS App
- Using the File Disclosure to find the root by searching for Gemfile, then exporting the SQLite database

#### Hospital 
- Introduction
- Start of nmap
- Analyzing the TTL to see that the Linux Host is likely a Virtual Machine. Also Docker is not at play since it decremented
- Attacking the PHP Image Upload Form, discovering we can upload phar files
- Uploading a php shell, discovering there are disabled functions blocking system

#### iClean 
- Introduction
- Start of nmap
- Taking a look at the website
- Testing the Get a Quote feature for XSS
- Weaponizing the img src xss test by adding fetch to attempt to exfil the cookies

#### Imagery 
- Introduction
- Start of nmap
- Viewing the Flask Cookie with Flask-Unsign
- Discovering the Report Bug endpoint which is vulnerable to XSS and HTTP Only is false allowing us to steal cookies
- Another way to discover XSS, look at JavaScript in PageSource which leaks a lot of information

#### Inception 
- Start of Recon + Finding dompdf
- PHP Wrappers + Failed testing for RCE
- Writing Python Program to automate file disclosure bug
- Finding WebDav Configuration + Uploading Files for RCE
- Modifying Sokar's Forward Shell (PTY over HTTP)

#### Infiltrator 
- Introduction
- Start of nmap
- Using grep against a HTML Page to extract usernames, then username anarchy to build a userlist and kerbrute to find valid users
- Kerbrute automatically will ASREP Roast but outputs in the stronger hash that hashcat doesn't crack. Using downgrade to get the weaker hash
- Using NXC with our creds to dump a list of users and see a password in the description

#### Inject 
- Introduction
- Start of nmap
- Trying to identify the technology running the webapp, 404 page reveals it is likely tomcat
- Running Gobuster, then checking out the page
- Uploading an image and discovering an file disclosure vulnerability

#### Instant 
- Introduction
- Start of nmap
- Taking  look at the web application and fingerprinting the framework
- Using Jadx to decompile the APK File, then using grep to look for domains and discovering swagger
- Looking at the source code of the APK File and finding a hard-coded secret that allows us to make API Requests

#### Intentions 
- Introduction
- Start of nmap
- Looking at the login request, guessing it is Laravel based upon XSRF being in cookie and header
- Playing with updating genre and viewing feed to discover an error
- Opening up SQL Fiddle to explain what I think is going on, its using FIND_IN_SET

#### Intuition 
- Introduction
- Start of nmap
- Discovering the application is flask based upon 404 page, showing Werkzeug source to show where the error comes from
- Noticing the cookie is odd but since input is escaped, it doesn't look that insecure
- Discovering XSS in the Report Submission form and stealing cookies and get a moderator cookie

#### Jab 
- Introduction
- Start of nmap
- Opening Pidgin to register with the Jabber Server then look at chatrooms
- Opening the XMPP Console so we can copy users to build the username list
- Running Kerbrute against the users to get a few ASREP Roast Hashes

#### Jarvis 
- Begin of Recon
- Running Gobuster and examining the web page
- Room.php is the only page that accepts user input, basic testing for SQL Injection
- Using wfuzz to fuzz for special characters then getting our IP Banned :(
- Unbanned, running wfuzz again and examining unique responses

#### Joker 
- Port Enumeration
- UDP Port Review
- TFTP Enumeration
- Cracking Squid PW
- FoxyProxy Setup

#### Jupiter 
- Introduction
- Using gobuster to enum
- Discovering Raw SQL in the HTTP Request, doing some enumeration to discover it is PostreSQL
- Looking at the PostgreSQL Copy command, which allows for running commands, getting a shell
- Got a shell as the PostgreSQL user

#### Keeper 
- Introduction
- Start of box
- Checking out Request Tracker, login with default creds
- Finding a password in the users description on RT
- Googling how to get keepass passwords from memory

#### Laboratory 
- Start of nmap, looking at SSL Certificates to get a hostname
- Examining the website
- Getting git.Laboratory.htb out of the certificate and checking that host
- Registering for a GitLab Account then poking at gitlab
- Getting the GitLab Version and finding a Vulnerability

#### LaCasaDePapel 
- Start of nmap
- Attempting to execute an VSFTPD Backdoor via MSF
- Discovering the backdoor opened 6200, discovering a weird shell
- Lets figure out what just happened
- Triggering the backdoor without Metasploit

#### Lantern 
- Start of nmap
- Discovering the Skipper Proxy header, discovering an SSRF CVE
- Using FFUF with this SSRF to scan local ports, discover port 5000. Using BurpSuite to add the proxy as our header and discover an internal web service
- Discovering an SQLite Injection
- Dumping the SQLite Table Schema from our injection, then grabbing data to get the password

#### Late 
- Time stamps will be added tonight

#### Lazy 
- Basic Web Page Discovery
- Examining Cookies - Pt1 (Burp Sequencer)
- Fuzzing Usernames (2nd Order SQL Injection)
- Examining Cookies - Pt2
- Cookie Bitflip

#### LightWeight 
- Begin of recon, Nmap
- Taking the CentOS Apache Version to find major version
- Running GoBuster with a Common-PHP-Files wordlist.
- Enumerating Ldap with ldapsearch
- Discovery of Password Hashes within ldap information

#### LinkVortex 
- Introduction
- Start of nmap
- Discovering the Forgot Password lets us enumerate valid emails
- Using ffuf to enumerate subdomains via virtual host
- Discovering .git on the dev subdomain, using git-dumper to download the repo

#### Luke 
- Begin of Recon
- Checking FTP to get a note
- Going to each of the three websites
- Running Gobuster on port 80/3000
- Taking notes of all the login pages (forgot Ajenti)

#### MagicGardens 
- Introduction
- Start of nmap
- Discovering the website is built with Django via Wappalyzer or the 404 page
- Looking at the Subscription Page, discovering we can change the hostname of the payment processor which is like a SSRF Vulnerability
- Making a request to the Payment Processor to see how it responds, building a flask app to mimic the behavior changing the denied message to approved

#### Mailing 
- Introduction
- Start of nmap, discovering potential username convention from SSL Certificate
- Checking out the website
- Examining the request being made to download the PDF and talking about how Metadata can leak if it came from disk or the webapp
- Discovering File Disclosure in the download script

#### Mailroom 
- Introduction
- Start of nmap, discovering two different OS's
- Running Gobuster to bruteforce VHOST
- Discovering XSS but nothing we can really do with it
- Enumerating Gitea, discovering a repo with some source code

#### Manager 
- Introduction
- Start of Nmap
- Checking out the website, deciding there isn't much of interest here
- Running Kerbrute with a userlist to identify valid users
- Showing what Kerbrute is doing with NetExec

#### Mirage 
- Introduction
- Start of nmap
- Exploring NFS which is odd on a Windows Box
- Mounting the share with NFSv3, so we can spoof UID's to read any file we want
- Using NSUpdate to create a DNS Record for nats-svc.mirage.htb

#### Mirai 
- Examining some odd behavior. Nmap different result than browser.
- Getting to /admin and testing for Zone Transfer
- Testing SSH Default Raspberry Pi Creds
- Escalate to root 'sudo su'
- Recovering the deleted root.txt

#### Mist 
- Introduction
- Start of nmap which contains pluck version
- Looking into CVE-2024-9405 which is a File Disclosure vulnerability
- Discovering a backup password, cracking it, then uploading a malicious plugin
- RCE Obtained, defender is blocking reverse shell, obfuscating the command to bypass

#### Moderators 
- Start of nmap, then going over the website
- Examining all the pages on the blog
- Looking at the report parameter, doing some light testing for SQL Injection before moving on to IDOR
- Using ffuf to bruteforce all reports matching upon a word (phrase) on the page
- Attempting to figure out if the md5sum in the logs URL is random by submitting the hash to crackstation

#### Monitored 
- Introduction
- Start of nmap
- Examining the webpage, not finding much
- Checking out SNMP, discovering its open with the default community string. Installing MIBS so we can make sense of the data
- The process list is in SNMP, explaining how to read this data

#### MonitorsThree 
- Introduction
- Start of nmap
- Examining Forgot Password to discover we can enumerate usernames and discover an SQL Error
- Showing why union injections aren't going to help us, then showing SQLMap
- Start of talking about error injection

#### MonitorsTwo 
- Start of nmap
- Discovering Cacti version and finding a vulnerability
- Sending the payload from the description, discovering we need to set the X-FORWARDED-FOR
- Incrementing Host_ID and Local_Data_Ids and discovering different output
- Discovering with local_data_ids set to 6 and host_id set to 1, we can get code execution

#### Napper 
- Introduction
- Start of nmap, showing -vv will cause the output to contain TTL
- Checking out the website
- Doing a VHOST Bruteforce to discover the internal domain and discovering credentials on a blog post
- Checking out the NAPListener blog post, which gives us a way to enumerate for the NAPLISTENER Implant

#### Nineveh 
- Begin Recon (NMAP)
- GoBuster HTTP + HTTPS
- Accessing Pages
- Using Hydra against HTTP + HTTPS Web Forms
- Logging into HTTP and hunting for vulns

#### Nocturnal 
- Introduction
- Start of nmap
- Running gobuster to find PHP Files
- Uploading a file and playing with the file upload functionality
- Playing with the username variable, discovering we can list files of other users

#### Node 
- Begin of NMAP
- GoBuster (Fails)
- Screw GoBuster, BurpSpider FTW
- Examing Routes File to find more pages
- Finding Credentials and downloading backup

#### October 
- Twitter @ippSec
- Low Priv: Default Account + File Upload
- PrivEsc: Return to LibC + ASLR Bruteforce
- Pulling up Web Page.
- Searchsploit

#### Office 
- Introduction
- Start of nmap
- Testing the XAMPP PHP Vulnerability, which doesn't work
- Getting the Joomla Version from the manifest, then exploiting CVE-2023-23752 to get the MySQL Password (same as devvortex)
- Using KerBrute to bruteforce valid usernames and then NetExec to spray the MySQL Password to get DWOLFE's password

#### Olympus 
- Begin of Recon, nmap filtered explanation
- Begin of initial DNSRecon, hunting for a domain name
- Web page enumeration, finding xdebug in header
- Installing xdebug plugin in Chrome to show its use
- Getting a reverse shell on the first docker (Icarus)

#### OnlyForYou 
- Introduction
- Start of nmap
- Discovering beta.only4you.htb
- Downloading the source, scanning with Snyk and discovering a File Disclosure vuln
- Demonstrating that os.path.join in python will do unexpected things if a path begins with slash

#### Ouija 
- Introduction
- Start of nmap
- Fuzzing the API port port 3000 with ffuf
- Discovering the Gitea Domain and seeing a repo which discloses HA Proxy 2.2.16 is in use
- Exploring CVE-2021-40346 an integer overflow in HA Proxy which enables HTTP Smuggling

#### Outbound 
- Introduction
- Start of nmap
- Logging into RoudnCube with the assume breach credentials, getting the version and searching for exploits
- Running the CVE-2025-49113 POC to get a shell on the box
- Taking a step back and just examining the payload for the POC and talking about the attack a little

#### PC 
- Introduction
- Start of nmap
- Googling the port number, and reading more about gRPC
- Install GRPCurl so we can access the gRPC interface
- Enumerating the grpc interface

#### Perfection 
- Introduction
- Start of nmap
- Discovering the Weighted Grade Calculator which we will exploit
- Using FFUF to enumerate all bad characters and discovering we can't send any symbols
- Quick bash one liner with JQ to URL Encode each line of our wordlist

#### PermX 
- Introduction
- Start of nmap
- Using FFUF to fuzz for virtual hosts (sub domains)
- Discovering the LMS Sub Domain which hosts Chamilo, talking about enumerating versions of opensource applications
- Start of talking about pulling MD5's of every file in a .git, so we can see when a file got introduced

#### Pikatwoo 
- Introduction
- Start of nmap
- Identifying all the technologies used in the box
- Looking at OpenStack Keystone Authentication and discovering CVE-2021-38155
- Pulling up API DOCS to see how to login to Keystone, then testing lockout

#### Pilgrimage 
- Introduction
- Start of nmap
- Uploading an image file and trying to identify how the upload works
- Running Git-Dumper to download the exposed .git directory, taking a look at the source code
- Looking at the ImageMagick version (7.1.0-49) and seeing it is vulnerable to CVE-2022-44268

#### Planning 
- Introduction
- Start of nmap
- Using gobuster to discover the VHOST and running into a minor issue, I think gobuster changed how it handles the domain on VHOST Scans.
- Looking at the Nuclei Results
- Using the append-domain (ad) flag in gobuster to allow our VHOST scan to work and discovering the Grafana subdomain

#### Player2 
- Begin of NMAP
- Identifying the Virtual Host (VHOST) player2.htb and doing recon on the webserver
- Testing basic SQL Injection on product.player2.htb
- Running gobuster against the product domain to find potential pages
- Running gobuster to try to enumerate sub domains.

#### Poison 
- Start of recon, use Bootstrap XSL Script to make nmap pretty
- Looking at nmap in web browser
- Navigating to the web page, and testing all the pages.
- Testing for LFI
- Using PHP  Filters to view the contents of php file through LFI (Local File Inclusion)

#### Popcorn 
- TMUX and Connecting to HTB
- Virtual Host Routing Explanation
- File Enumeration (Dirb)
- Discover of Web App
- Starting SQLMap in the Background

#### POV 
- Introduction
- Start of nmap
- Discovering the Dev Subdomain
- Playing with the Resume Download, discovering a File Disclosure Vulnerability
- Discovering some odd behavior with ../, its just a replace.  Grabbing web.config

#### Previous 
- Introduction
- Start of nmap
- Wappalyzer detects NextJS and shows the version, looking at CVE's
- Looking at the nextjs middleware vulnerability (CVE-2025-29927)
- Our nuclei scan didn't detect it, looking at templates, it should but needs the headless flag

#### Puppy 
- Introduction
- Start of nmap
- NFS is listening on Windows which is odd, looking into it briefly and not finding anything
- Using NXC to list shares and running RustHound
- Adding ourself to developers, which will let us access the develoeprs share

#### Rebound 
- Introduction
- Start of nmap then checking SMB Shares
- Using NetExec to do a RID Brute Force and increase the maximum to 10000
- Using vim g!/{string}/d to delete all lines that do not contain something to build wordlists
- Using ASREP Roasting to perform a Kerberoast attack without authentication

#### Redcross 
- Flow chart of potential paths through this box
- Begin of recon, SSL Enumeration, examining PHP Behavior
- Using GoBuster to dicover directories, pdf's, and php scripts
- Using wfuzz to discover subdomains (virtual host routing)
- Guessing credential, logging in with guest:guest disover SQL Injection

#### RedPanda 
- Introduction
- Start of nmap
- Poking at the web page, examining the request, playing with server headers
- Discovering an error message, googling it and finding out it is tied to Sping Boot
- Start of FFuf, using a raw request so we can ffuf like we can sqlmap

#### RegistryTwo 
- Start of nmap
- Enumerating port 5000/5001 to see a Docker Registry and Auth Server
- Creating our auth token for the Docker Registry
- Adding the SSL Cert to our certificate store, then doing a docker pull to download and run the container
- Discovering JSESSIONID Cookie, attempting the weird directory traversal bug of /..;/ (nginx directory didn't have a trailing slash on the location)

#### Resource 
- Introduction
- Start of nmap
- Discovering LFI in the page parameter but we cannot immediately exploit it
- Discovering admin and playing with ping, deciding its not vulnerable and moving on
- Uploading a zip file to the ticket, then using the phar wrapper with our LFI to include it

#### Retired 
- Start of nmap
- Talking about what the page parameter does and why its normally vulnerable to LFI
- Running gobuster to get a list of files on the webserver while we poke at the LFI
- Finding an LFI in combination with an EAR (Execute After Read) Vulnerability. Then examining the source code of index.php to see the vulnerability
- There was an sanitize string function that wasn't recursive, explaining how we could exploit this.

#### Rope 
- Nmap the box, then play with the WebServer. 404 msg are interesting
- Discovering Directory Traversal and then grabbing the webserver by going to /proc/self/cwd/
- Opening the binary up in Ghidra and exploring the binary to understand what it does
- Discovering we have control over the first argument in log_access/printf
- Showing one of my most hated things about debugging forks.  Be sure to always kill the process!

#### RouterSpace 
- Start of nmap
- Downloading the APK
- Running apktool to decode the APK, examining files, don't get much info
- Finding a certificate in the application that gives up the host name
- Trying out another APK Decompiler, Bytecode Viewer

#### Runner 
- Introduction
- Start of NMAP
- Discovering the TeamCity Subdomain, which has a version banner showing it running 129390 and is vulnerable to CVE-2023-42793
- Exploring the TeamCity Authentication Bypass vulnerability to see why URL's ending in RPC2 don't require authentication
- Logged in as an administrator on TeamCity creating a Backup, which has a Database Backup and any SSH Keys associated with projects

#### RustyKey 
- Introduction
- Start of nmap
- Syncing our time with the DC via NTPDate
- Writing a custom Cypher Query in Bloodhound to show everything that users and computers can directly do, except for group memberships. Discover an odd
- Using NetExec to perform a TimeRoast attack and then cracking the computer password

#### Sandworm 
- Introduction
- Start of nmap
- Finding their public key, then sending an encrypted message that contains a XSS Test payload
- Creating a PGP Key and sending our public key, so they can send an encrypted message back
- Decrypting the message they sent to us

#### Sau 
- Start of nmap
- Examining the website, playing with the basket, trying SSTI/SQL Injection special characters
- Looking at the settings, discovering we can perform a SSRF and get the response back. Grabbing localhost:80
- The local website runs maltrail 0.53, examining the exploit then manually exploiting it to get a shell
- Shell returned, checking if we really needed to encode the payload

#### Scepter 
- Introduction
- Start of nmap
- Looking at the NFS Mount on Windows, then downloading the certificates
- Examining the certificates, dumping information to look at username and expiration. Then cracking PEM and PFX
- Using certipy to auth with the certificate, discovering some accounts are locked out

#### Sea 
- Introduction
- Start of nmap
- Trying to identify what is running the webapp (WonderCMS), discovering a themes directory in source and burpsuite
- Taking a string that looks unique in the CSS and searching GitHub to discover where it exists in an open-source repo
- Showing several ways we could of dirbusted the themes directory to discover this file

#### Sekhmet 
- Start of nmap
- Running ffuf to discover the portal virtual host
- Logging in with admin:admin and discovering a new cookie
- Looking at the Node-Serialize exploit
- Attempting to do the exploit and discovering modsecurity blocks us, then putting some unicode in the payload to evade it

#### Shared 
- Start of nmap
- Taking a look at the website
- Searching the PrestaShop github to find a way to fingerprint the website, discovering INSTALL.TXT then finding the commit that contains our version
- Discovering checkout.shared.htb
- Examining how the checkout subdomain gets the contents of the shipping cart (cookies), editing the cookie and seeing what happens

#### Sightless 
- Introduction
- Start of nmap
- Discovering SQLPad
- Discovering a SSRF in SQLPad when adding connections. Sending to FFUF, use a time filter to show timeouts
- Finding the SQLPad Version (6.10.0), which has a template injection vulnerability getting a shell

#### Signed 
- Introduction
- Start of nmap
- Logging into the SQL Database with the provided credentials, going over basic enumeration
- Using XP_DIRTREE to have the SQL Server make a request, sending it to ourself and stealing/cracking the hash
- Showing RID Brute Forcing with MSSQL to enumerate additional users

#### Skyfall 
- Introduction
- Start of nmap
- Discovering the demo subdomain, which is a Flask website
- Quickly playing with the File Download, Upload, and Rename -- Looking for low hanging fruit, not finding any
- Playing with the URL Fetch looking for a good SSRF, Discovering the site is likely in Docker

#### Sneaky 
- If you're wondering how this could be an hour long video, over half the video is talking about IPv6.
- Recon + Web Enum
- SQL Injection
- Start of IPv6 Talk
- What is an IPv6 IP Address?

#### Snoopy 
- Introduction
- Start of nmap, discovering ssh/dns/http
- Taking a look at the website
- Discovering a message about DNS, taking a look at the DNS and discovering zone transfers are enabled
- Identifying the website is running with PHP Enabled, then running gobuster

#### Socket 
- Introduction
- Start of nmap
- Taking a look at QReader.htb
- Opening the QReader application to discover it requires GLIBC_2.35, going back to nmap to see what flavor of linux was used
- Switching to Ubuntu Jammy and running Wireshark with the app running to see it makes a request to WS.QREADER.HTB

#### SolarLab 
- Introduction
- Start of nmap
- Discovering Guest can read files on SMB, using mount to copy all the files
- Grabbing usernames and passwords from the excel document so we can use them for spraying
- Taking a look at port 6791 to see ReportHub, using FFUF to spray usernames to get a valid user

#### Soulmate 
- Introduction
- Start of nmap
- Bruteforcing virtualhosts with ffuf
- Discovering CrushFTP, running nuclei which will get the version
- Playing with the soulmate.htb website while our recon runs

#### Stocker 
- Introduction
- Start of nmap
- Running Gobuster in VHOST Detection mode to find the dev subdomain
- Intercepting a request to dev.stocker.htb and seeing an connect.sid  cookie and x-powered-by header saying express, both indicating it uses NodeJS/Exp
- Explaining why I'm trying these injections

#### Stratosphere 
- Begin of recon
- Manually checking the page out
- Discovering the webserver is java/tomcact
- Starting up GoBuster / Hydra
- The Directory /Monitoring was found - Discovering its Struts because of .action

#### Surveillance 
- Introduction
- Start of nmap
- Discovering an exploit for Craft CMS, it doesn't work out of the box because of a typo on exploit-db looking into this exploit
- Walking through the Exploit Script
- Getting a shell on the box with the script that was on Github

#### Tartarsauce 
- Begin of recon
- Discovery of Wordpress and fixing broken links with burp
- Start of WPScan
- Start of poking at Monstra, (Rabbit Hole)
- Back to looking at WPScan, Find Gwolle Plugin is vulnerable to RFI Exploits

#### TheFrizz 
- Introduction
- Start of nmap
- Discovering Gibbon LMS is running and enumerating the version
- Using CVEDetails to look at CVE's for Gibbon, then discovering an unauth file upload
- Getting a shell by uploading a malicious PHP Script

#### Time 
- Start of nmap
- Poking at the website
- Finding a way to generate error messages
- Researching the error message
- Throwing a random exploit from the internet and getting a new error

#### Timing 
- Start of nmap
- Running feroxbuster and discovering image.php
- Fuzzing image.php for parameters and discovering an LFI
- Enumerating the WAF to find blacklisted strings and then using a php filter to extract source
- Examing the login.php source code and discovering a timing attack

#### Titanic 
- Introduction
- Start of nmap
- Intercepting the booking download and finding the File Disclosure Vulnerability
- Finding the dev.titanic.htb host and discovering Gitea
- Running Gitea locally via docker to see how where it stores the configuration and database

#### Tombwatcher 
- Introduction
- Start of nmap
- Running RustHound with the credentials we were given
- Clicking outbound control a few times from Henry to see an obvious (but long) attack path
- Using BloodyAD to perform the Targeted Kerberoast attack

#### Topology 
- Introduction
- Start of nmap
- Discovering Discovering the LaTeX Equation Generator Page
- Attempting to get code execution, discovering a WAF. Building a wordlist and using FFUF to identify potentially dangerous commands that aren't blocked
- Discovering lstinputlisting is not blocked, which will let us read files

#### Trickster 
- Introduction
- Start of nmap
- Showing the Shop Subdomain via ffuf
- Performing a gobuster attack, need to update the user agent because everything returns 403 at first (WAF)
- Discover .git, then running git-dumper to download the .git directory and discover the unique admin directory

#### Unattended 
- Begin of recon
- Running GoBuster to discover /dev and index.php
- Checking out the web application
- Discovering SQL Injection in ID and playing with it
- Running SQLMap to dump pieces of the database

#### Underpass 
- Introduction
- Start of nmap
- Checking if SNMP is open and then installing the MIBS so we get more readable output
- Discovering the Daloradius directory and if we specify files in it we can get output. Logging in with default credentials
- Discovering Daloradius shows password hashes of users, cracking and logging in

#### University 
- Introduction
- Start of nmap
- Looking at the website, discovering it is Django
- Exporting a profile, discovering it is using ReportLabs and xhtml2pdf
- Confirming RCE in Report Labs with ping, then getting a reverse shell

#### Usage 
- Introduction
- Start of nmap
- Discovering the page is Laravel based upon cookies
- Discovering the SQL Injection in Reset Password, then running SQLMap screwing up our results because we logged out in middle of SQLMap
- Cracking the user out of admin_users

#### Vault 
- Begin of Recon
- Begin of GoBustering
- Discovery of an image upload script
- Attempting to bypass the upload filter
- Reverse Shell to ubuntu Returned.  Examining Web Source

#### Vintage 
- Introduction
- Start of nmap
- Running Bloodhound
- Bloodhound, Shortest Path to Tier 0 shows us two ADM users which can add themselves to Delegated Admins
- Dumping Password set time of users in bloodhound with JQ to see any passwords set at the same time

#### Visual 
- Introduction
- Start of nmap
- Examining the request the server makes to us
- Using docker to run a Gitea Instance
- Using docker to install a DotNet Container (make sure its the SDK!)

#### Voleur 
- Introduction
- Start of nmap
- Running RustHound
- Running smbclient with Kerberos, to login to the fileshare as Ryan and downloading/cracking a word document with password
- Opening the Access Review Document, discovering multiple credentials and looking at bloodhound to see what we can do

#### Waldo 
- Begin of Recon
- Looking at what Filtered means in Nmap
- Start of looking at webpage (GoBuster)
- Manual HTTP Enumeration
- Start of exploiting with BurpSuite

#### Wall 
- Start of recon
- Running GoBuster to discover the /monitoring directory
- Running hydra to try to brute force the HTTP Authentication (Does not work due to it being a secure password)
- Bypassing the AUTH Request by changing to a POST — Explain why this works later
- Looking at the Centreon Changelog to look for any exploits

#### WhiteRabbit 
- Introduction
- Start of nmap
- Playing with a JavaScript Client app (Vue) to get information to do recon and finding public /status/ page
- Looking at the N8N Workflow with GoPhish
- Looking at the JSON Schema File that leaks a secret key and shows possible SQL Injection

#### Wifinetic 
- Introduction
- Start of nmap
- Using wget to download all files from FTP then examining files, taking notes of the usernames
- Taking a look at the backup, discovering a password in the wireless config
- Using CrackMapExec to spray SSH with our password and getting a success with netadmin

#### WifineticTwo 
- Start of nmap
- Discovering OpenPLC, looking for default credentials and logging in with openplc:openplc
- Uploading a C reverse shell to OpenPLC
- Talking about our shell hanging our webserver, showing a POC that runs system() to background a process which seems to be smart
- Discovering a Wireless NIC, running IW to see wireless networks and OneShot to attack WPS

#### Ypuffy 
- Want the WireShark Sticker? http://weirdstuffis.online
- Begin of Recon
- Enumerating OpenBSD Patch Date via SSH Version
- Examining port 80... Use Wireshark to see why NMAP gets a response but firefox does not
- Invalid Requests, will cause HTTP Service to send error message

#### Yummy 
- Introduction
- Start of nmap
- Playing around with the website, booking a table and then registering an account
- Taking a look at the Save to iCalendar functionality and finding a File Disclosure vulnerability
- Finding the application source code via the /proc/self/cwd directory

#### Zipping 
- Introduction
- Start of nmap
- Discovering a likely LFI in product.php but cannot use filters, likely because there is a file_exists() check
- Playing with the File Upload functionality
- Talking about the PHAR wrapper in PHP, showing it will bypass the file_exist and we can go into the ZIP to bypass the .pdf check

</details>

---

## Tutorials, Methodology & Special Videos

These are IppSec's non-machine videos covering techniques, tool building, blue team, and methodology.

### Offensive Technique Deep-Dives

**Advanced PHP Deserialization - Phar Files**
- Previous Video: Intro to PHP Deserialization - https://youtu.be/HaW15aMzBUM
- Little bit of history about PHP Serialization
- Why is uploading Phar Files different than normal file upload vulns?

**All About DLL Hijacking - My Favorite Persistence Method**
- Why DLL Hijack is my favorite persistence, talk about a few others
- Going over the source code to our sample applications to talk about DLL Hijacking
- Compiling our executable and dll then transfering it to our windows box

**Attacking Password Resets with Host Header Injection**
- Introduction talking a little bit about
- Using Extension to show a legitimate password reset
- Modifying the host header and showing the website uses that in the sent email

**Automating Boolean SQL Injection and Evading Filters**
- Sign up for Snyk at https://snyk.co/ippsec
- Talking about why I like SQL Boolean Injection
- Opening up the source code to the web app

**AV Evasion - Mimikatz**
- Installing FireEye Commando to help keep our development environments sync'd
- Using Git to download mimikatz, openifang with Visual Studio 2017 and installing dependencies
- Verifying that we can compile mimikatz before we make any changes.

**Creating a VM to learn Linux PrivEsc**
- Support the stream: https://streamlabs.com/ippsec

**Deep Dive into Parsing SSH Keys To Exploit Improperly Sanitized Screenshots**
- Generating our SSH Key and Base64 Decoding it
- Opening the SSH Key in Bless
- Showing information from the SSH RFC which will tell us what we are parsing

**Detecting Exploits - OMIGod (Linux Logging with Auditd)**
- Intro, how to install and configure auditd
- Installing Auditd
- Downloading a good baseline ruleset from github

**Device Code Login Phishing Presentation Attack, Detect, Mitigate**
- A couple weeks ago, I explored Device Code Phishing with a friend, and we decided to make a video about it. It's a new format of video and topic as I rarely cover the cloud, so we'd appreciate if you 
- - https://www.microsoft.com/en-us/security/blog/2025/02/13/storm-2372-conducts-device-code-phishing-campaign/
- - https://www.volexity.com/blog/2025/02/13/multiple-russian-threat-actors-targeting-microsoft-device-code-authentication/

**DIY C2 - Malleable Agent Config**
- Showing malleable c2 configs
- Creating a Hello World in C++ then creating a 2000 byte variable
- Adding JSON Support to our program

**Dumping Data with NoSQL Injection via Regex and Python**
- Check out Snyk here: https://snyk.co/ippsec
- Introduction talking about the application we are testing and identifying NoSQL Injection with $ne
- Showing the RegEx Operator, which will let us do partial matches and enable us to validate characters one at a time

**Executing Linux Binaries Without Touching Disk - Living Off The Land with DDExec and Dirty Pipe Demo**
- Intro, the stream is here: https://www.twitch.tv/videos/1445106911
- Start of the video, showing what is new about this technique
- Running through the example, showing we can change the filename in ps to anything we want

**HHC2016 - Ads**
- https://ippsec.github.io/holidayhack2016/part-4/#ad

**HHC2016 - Analytics**
- https://ippsec.github.io/holidayhack2016/part-4/#analytics
- Note: Video may contain slight errors, most notably in this video is mistakenly saying "Hash" instead of "Encrypt" (ex: @5 minutes).
- A full text writeup can be found at:

**HHC2016 - Debug**
- https://ippsec.github.io/holidayhack2016/part-4/#debug

**HHC2016 - Dungeon**
- https://ippsec.github.io/holidayhack2016/part-4/#dungeon

**HHC2016 - Exception**
- https://ippsec.github.io/holidayhack2016/part-4/#exception

**HHC2016 - Getting Coins**
- https://ippsec.github.io/holidayhack2016/tokens/
- Note: Video may contain slight errors, most notably in this video is using "function" and "variable" interchangeably.

**HHC2016 - Terminal Speedrun**
- Write Up Link:
- https://ippsec.github.io/holidayhack2016/part-3/

**Intro to PHP Deserialization / Object Injection**
- Background information, showing variables are point in time
- Creating a PHP Class and Object
- Serializing the Object and going over the format

**Looking into the Looney Tunable Linux Privesc CVE-2023-4911**
- Introduction talking about what the Looney Tunable exploit is and my thoughts on the severity of the exploit
- Start talking about how the vulnerability works
- The POC String to identify if a box is vulnerable, it doesn't actually exploit but quickly identifies if a vulnerable glibc is installed

**Making Blind XXE Quicker and Easier By Creating a Script to Exfiltrate Files**
- Introduction, why I created this script and a quick demo
- Going over XML Entity Injection, doing it manually and explaining what the payloads are
- Sponsor shoutout, showing Snyk scan the source code to this application and catching the XXE

**PHP Type Juggling - Why === is Important - Bug Bounty Tips**
- Join Intigriti here: https://go.intigriti.com/ippsec
- Enumerating the application utilizes Laravel based upon a default cookie name.
- Jumping into a PHP Interpreter to show off the Type confusion bug.

**Playing with Exploits - OMIGod**
- Start of installing OMI Locally
- Downloading the exploit, but get a connection error because it cannot talk to OMI
- Editing the OMI Configuration to set it to listen on 5986

**Reversing Malware How is APT 29 Successful w/ this Phishing Tech and BRc4 (Brute Ratel) opsec fails?**
- Introduction, talking about why I think APT-29 successfully phishing is funny
- Unit42's blog post talking about how the phishing document worked
- Going to google to show APT29 doing the lnk file in a zip since atleast 2016, Mandiant post.

**SQL Injecting Beyond Strict Filters - Union Without Comma**
- Introduction
- Showing the trick and explaining why its important to understand the methodology behind finding the technique and not just the technique itself
- Going over the Flask App

**Using PAM EXEC to Log Passwords on Linux**
- Video will be public June 2nd
- Introduction
- Talking about what PAM is

### Blue Team / Detection / DFIR

**Advanced Windows Logging - Finding What AV Missed**
- Explaining the HELK Architecture
- Showing my VM's Spec's/build
- Installing HELK

**Basic Linux Memory Forensics - Dumping Memory and Files with DD - Analyzing Metttle/Meterpreter**
- Discovering a weird binary running in /tmp/ but it doesn't exist on disk
- Start of explaining dd copying things out of memory
- Reading maps to identify where the file is, showing how to covnert hex to decimal in bash

**Combining AD Honey Pot Accounts with Canaries to Detect Password Sprays and Kerberoasting for free!**
- **IMPORTANT: The event filter should be 4625 not 4624.
- Going over CanaryTokens
- Scheduled Task Basics

**Detecting Responder via LLMNR Honey Tasks on User Workstations**
- Talking about how the attack works and why NetBIOS/LLMNR should be disabled
- Running Responder on a linux host and then attempting to browse a file share on a Windows Host and grabbing the Hash
- Cracking the hashes our computer provided to show how easy it is to steal passwords on a network

**Ippsecs First Look and Setting up CrowdSec  - Stealthfully Forward Malicious Users to Honeypots**
- Intro talking about crowdsec and its multiplayer firewall
- Showing my setup, 3 web servers, 2 attack servers
- Installing Crowdsec

**Monitoring Sensitive Windows Commands via CanaryTokens - Deploying Registry Entries via Group Policy**
- Intro, you should be using centralized logging for this. But if not this hackjob will do
- Talking about the Sensitve Command Token
- Examining how this all works, creates three registry keys for Image File Execution Options and SilentProcessExit

**PowerSIEM - Analyzing Sysmon Events with PowerShell - Dynamic Malware Analysis**
- PowerSiem: https://github.com/IppSec/PowerSiem
- Creating PowerSiem: https://www.twitch.tv/videos/1438252177
- Sysmon: https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon

**Securing Vendor Webapps - A Vulnerability Assessment on HELK**
- More detailed notes: https://gist.github.com/IppSec/137a9f8870bed2763048072f321073e5
- My Vulnerability Assessment methodology
- Starting a Nessus Scan to see what it thinks

**Setting Up Elastic 8 with Kibana, Fleet, Endpoint Security, and Windows Log Collection**
- Intro brief descriptions of Elastic, Kibana, Fleet Management, Endpoint Security, Windows Logging
- Logging into our Elastic Box and going to https://www.digitalocean.com/community/tutorials/how-to-install-elasticsearch-logstash-and-kibana-elastic-stack-on-ubuntu-22-04
- Changing the Elastic Repo from 7.x to 8.x, then installing Elastic making sure to grab the default credentials

**Using Sysmon to Block Unwanted Files and Send Notifications to Slack via Scheduled Task Event Filter**
- Installing Sysmon and the configuration from Neo23x0's Repo
- Explaining the file blocked section
- Viewing the Sysmon log to confirm it is installed and see its EvendID 27

### Tool Setup / Building / Automation

**Building Ippsec's Parrot VM - How to Run the Playbook.**
- Github Repo: https://github.com/ippsec/parrot-build
- This is a quick video just to show how to run my Ansible Playbook to build out my Parrot VM. Check out the Building Parrot Playlist to see how this all works, so you can customize things to your likin

**Configuring Burpsuite and Firefox via Ansible - Intro to Jinja2 and Ansible**
- Introduction talking about the power of Jinja2
- Quick Jinja2 introduction, showing how Ansible uses templates
- Using Jinja2 Loops with Ansible Variables to build URL's of Firefox Plugins and not put a comma on the last item.

**Configuring Iptables/UFW and Auditd with Ansible**
- Introduction why you should setup logging
- Start of configuring UFW, enabling UFW and setting the policy to accept all
- Showing how to insert IPTABLES Rules into UFW's Config

**Creating Webhooks in Slack and sending messages from Powershell**
- Simple concept/video but we will build more upon it in the following weeks.
- Signing up and installing the client
- Changing our channel to Private and Installing the Webhook

**Fixing Hashcat Flask Session Module  - Just Needed to Update Maximum Length of the Hash**
- Recap, talking about the flask session cookie and showing hashcat won't crack ours
- Looking at Hashcat's source code, finding module 29100 which is flask session and seeing the max length is set to 27
- Checking out the JWT Module (16500) to see what the sizes are set there. Use this module because its similair.

**Golang for Hackers - LDAP Injector - Episode 04 - Functional Options Pattern**
- Video currently in member only, will go free May 19th
- Introduction (mistakenly called this episode 3, when it is 4)
- Going over the code we are going to update

**Golang For Hackers: LDAP Injector - Episode 01**
- Episode 2 Dependency Injection: https://youtu.be/BhLpqRev80s
- Introduction
- Going over LDAP Injection, showing we can log in with a wild card for username and password

**Golang For Hackers: LDAP Injector - Episode 02 - Dependency Injection**
- Episode 1 - Creating the program: https://youtu.be/uJFW4c4QE0U
- Episode 3 - Error Handling: https://youtu.be/BhLpqRev80s
- Introduction

**Golang for Hackers: LDAP Injector - Episode 03 - Error Handling**
- Next episode: Functional Options Pattern - https://youtu.be/p4VqejsO6oU
- Introduction talking about error handling
- Quickly going over some python/golang code to show the difference in mindset

**Hiding Spam with uBlock Origins**
- My uBlock Rule by the end of the video, definitely change the bad words:
- ! Twitter Bad Words
- twitter.com##[data-testid="cellInnerDiv"]:has-text(/ the | and | or /i)

**Installing VSCode with Copilot and Snyk via Ansible**
- Sponsor Link: https://snyk.co/ippsec
- Repo Here: https://github.com/IppSec/parrot-build
- Introduction Promoting Snyk

**Introduction to tmux**
- Why I like Tmux
- Creating Tmux Session
- Bash: Ctrl + R - Recursive Search

**Rebuilding Parrot and Using Ansible to Script Customizations to My Image**
- The Github Repo: https://github.com/IppSec/parrot-build
- Intro downloading the HTB Edition of Parrot and talking about basic VM Things
- Talking about using Ansible to install software after and why we should not use Snapshot's for a long-term solution.

### Other / Misc

**AppLocker Bypass COR Profiler**
- This video didn't go quite as smooth as I expected.  Still putting it here to show an unintended route for Ethereal.  When I get more time, I'll probably redo this video, so don't be surprised if it d
- Demo of this AppLocker Bypass
- How this is different than LOLBINs

**Automating a File Disclosure Vulnerability to Crawl Website Source**
- Check out https://snyk.co/ippsec
- Introduction
- Going over the file disclosure vulnerability we are using for the example (Zipping box from HTB)

**Beyond Root - Crawling PHP Webapps After File Disclosure**
- In Zipper, we had a File Disclosure vulnerability.  In the video we had made it so we could manually specify files to extract. I want to have it automagically crawl the website extracting all the sour

**Camp CTF 2015 - Bitterman**
- Introduction
- Using CheckSEC to explain the binary protections that can be applied.
- Running the binary to discover a segfault with long string of A's

**How To Create Empire Modules**
- Testing out a new microphone, enjoy the random video.
- Downloading Empire + PowerShell Port Forward
- Explaining Empire Directory Structure

**Intercepting Android App Traffic with BurpSuite**
- Introduction, talking about RouterSpace and why we can't just do what we did in that video
- Installing Genymotion, Virtual Box, and ADB; while talking about why I don't use Android Studio/AVD. Simply because genymotion just works.
- Make sure you upgrade your memory, processors, and enable Virtualization in your VM Settings!

**Ippsec's Thoughts on the New Hack The Box Seasons**
- Feedback: https://orrsuc93j02.typeform.com/HTBSEASONS
- Sorry for the bad cam quality.  Screwed up recording, then was too lazy to re-record.
- Introduction why you should play NOW

**Manually Parse Bloodhound Data with JQ to Create Lists of Potentially Vulnerable Users and Computers**
- Intro talking about why we want to parse Bloodhound Data with JQ to create lists
- Just examining the data in Bloodhound
- Writing a Cipher Query to show all enabled users in Bloodhound

**Reversing Malicious Office Document (Macro) Emotet(?)**
- OLEVBA - https://github.com/decalage2/oletools/wiki/olevba
- Extract Macro with olevba
- ExifTool to examine Document Metadata (Comments used in Macro)

**Sunday Night Learning**
- Unofficial Time Schedule.
- - First 30 minutes - Using ansible to build a Windows Domain
- - Next 30-45 minutes - Searching Exploit-DB and taking apart exploits to understand them

**Troubleshooting failed RCE Payloads by Debugging Python Web Applications  - Noter Beyond Root**
- Copying the webapp from the server to my local box
- Intalling the required modules to run the pip modules and running the website locally
- Using SSH Port forwarding to forward MySQL, so we don't have to setup a database

---

## UHC (Ultimate Hacking Championship) Machines

### UHC - Altered [Linux Hard]
- Start of nmap
- Enumerating the web page, finding a way to validate potential users
- Examining the data the website stores in our browser
- Attempting type juggling, finding out its not vulnerable

### UHC - Backend [Linux Medium]
- Introduction
- Start of nmap
- Examining the webpage, just finding json. Running gobuster to discover /docs and /api
- Examining the user and admin endpoint, showing /user/ has a 404 but we can go into it
- Talking about why API Discovery differs from normal web, instead of extensions we fuzz methods

### UHC - BackendTwo [Linux Medium]
- Start of nmap
- Talking about why dirbusting an API is different. Bruteforce methods instead of extensions and 404 doesn't terminate recursion
- Installing the latest version of FeroxBuster
- Running FeroxBuster with Force Recursion and multiple HTTP methods to discover user endpoints

### UHC - Gobox [Linux Medium]
- Intro, box is playable on HackTheBox!
- Start of nmap and enumerating the page on port 80
- Discovering Port 8080
- Using ffuf to fuzz and discover SSTI
- Showing wfuzz doesn't need nearly as many parameters

### UHC - Jarmis [Linux Hard]
- Intro going over the attack chain, SSRF to Protocol Smuggling to OMIGod
- Using nmap and then checking out the website and adding the DNS Names to our host file
- Running GoBuster to discover the /docs directory, which is swagger documentation
- Reading the documentation and explaining JARM Signatures
- Explaining the front-end which just makes accessing the backend pretty

### UHC - LogForge [Linux Medium]
- Start of nmap
- Discovering an Apache Tomcat Errror message despite the webserver being Apache
- Looking at Orange Tsai's 2018 Blackhat talk on Path Normalization
- Explaining the attack and how to bypass apache blocking access to /manager by using /..;/ or ;name=Stuff

### UHC - NodeBlog [Linux Easy]
- Box will be uploaded to HackTheBox by January 5th.
- Start of nmap
- Looking at the login, failing normal SQL Injection
- Start of talking about NoSQL/Mongo Injection

### UHC - Pressed [Linux Hard]
- Running nmap, discovering wordpress
- Manually looking at the wordpress site, finding a post that has some dynamic content on it... This is weird
- Attempting to poison the browser table with php/ssti/etc user agents
- Starting wpscan with enumerating all plugins

### UHC - Ransom [Linux Medium]
- Start of nmap, getting distribution by googling SSH/HTTP Server headers
- Checking out the web page and discovering it is a Laravel PHP Application based upon the cookie
- Talking a little bit about Laravel Internals, and why our web request is going to the API Middleware is useful
- Showing that Laravel accepts data in the BODY even if it is a GET Request

### UHC - Spooktrol [Linux Hard]
- Intro Hacking a Command and Control Server
- Running nmap and discovering two different SSH Instances, guessing one is Docker
- Looking at robots.txt which includes a link to the implant, looking at the error message and discovering its a cpp binary
- Using Wireshark to discover it makes a DNS Request to Spooktrol.htb, then walking through the C2's handshake
- Using BurpSuite and socat to proxy the connection of our binary

### UHC - Validation [Linux Easy]
- Intro, sorry for double upload.  First one missed the last 5 minutes.
- Start of nmap, discovering SSH/HTTP are different operating systems
- Testing the website
- Intercepting the registration and testing for SQL Injection on the Country
- Discovering a static cookie is returned that is a MD5Sum of the UserName

### UHC- Union [Linux Medium]
- Intro the best box to practice SQL Union Injections but I may be bias
- Start of nmap discovering nginx with PHP
- Doing recon on the website
- Starting recon in the background GoBuster/SQLMap
- Manually examining the player submission page

---

## HTB Sherlocks (DFIR)

### Analyzing auth.log and Playing with Grok Filters - HTB Sherlocks - Brutus
- Introduction
- Going over the wtmp file, showing utmpdump and last
- Start of talking about the auth.log, grabbing all the programs (ssh, cron, etc) so we know what is in the log
- Question 1: Identify the bruteforce use grep with oP to extract all IP Addresses with login failures
- Question 2: Looking at successful logins and seeing the malicious IP logged into root

### Analyzing Event Logs and MFT Dump with Chainsaw - HTB Sherlocks - CrownJewel-1
- Download Chainsaw: https://github.com/WithSecureLabs/chainsaw00:00 - Introduction, going over the scenario talking about dumping NTDS and why its incr
- Running chainsaw with the hunt operator, not getting much information
- Looking at what types of events were captured and using ChatGPT to give us event names for each ID
- Question 1: Looking at Event ID 7036 to see when Volume Shadow Copy Service entered a running state
- Showing how you could cheese the question by grepping for the word shadow

### Analyzing PCAP with Zeek - HTB Sherlocks - KnockKnock
- Going over the Scenario
- Talking about why I'm using Zeek and running it in a docker
- Showing a Corelight Zeek Cheat Sheet, which is tremendously helpful
- Showing Zeek-Cut on the x509 log, then looking at the SSL Log
- Looking for a single IP that sent multiple SSH Banners

### Analyzing Sysmon From Backdoored UltraVNC Malware - HTB Sherlocks - Unit42
- Introduction
- Going over the Unit42 Research that was posted to GitHub
- Downloading Chainsaw which is what we will use to parse the eventlog
- Running the hunt operation with chainsaw and default sigma rules to see some suspicious events quickly
- Using the search functionality to show us events with the process guid to show us what the suspicious file did

### IR Employee Fell for a Call Center - HTB Sherlocks - Tick Tock
- Introduction
- Analyzing the files we have
- Using Impacket to dump local creds
- Running MFTECmd to process MFT File and Chainsaw to process logs. These take a while
- Looking at the Prefetch files to see what programs have been run

### Log Analysis and Chainsaw Rule Creation - HTB Sherlocks - CrownJewel2
- Introduction
- Going over the Scenario
- Running Chainsaw Hunt to get an idea of whats in the log files, seeing  a Volume Shadow Copy Mount
- Running Hayabusa which is another tool that can analyze evtx files, it does a better job out of the box of showing malicious things
- Question 1: Looking at service start times to find when the latest time a Volume Shadow Copy started

### Post IR Investigation - MoveIT Exploit - HTB Sherlocks - I Like To
- Introduction
- Going over the questions
- Examing the forensic acquisition files
- Dumping the SAM Database to get hashes of the local accounts
- Running MFTECmd to convert the MFT (Master File Table) Dump to a JSON and CSV

---

## HTB Academy Module Reviews

- **Active Directory BloodHound**: HackTheBox Course on using Bloodhound, including writing cypher queries for custom graphs!  This cost 500 cubes, which is $50
- **Active Directory LDAP**: HackTheBox Course on Enumerating Active Directory over LDAP.  This cost 1000 cubes, which is ~$100
- **Active Directory PowerView**: HackTheBox course on Active Directory Enumeration and Exploitation with PowerView.  This cost 1000 cubes, which is $100
- **Attacking Web Applications with FFUF**: Free HackTheBox Course on using FFUF
- **Cracking Passwords with Hashcat**: HackTheBox Course on using Hashcat to its fullest.  This cost 100 cubes, which is ~$10
- **File Inclusion / Directory Traversal**: Free HackTheBox Course on performing Directory Traversal and File Inclusion attacks
- **Hacking Wordpress**: HackTheBox Course on Hacking Wordpress.  This cost 100 cubes, which is ~$10
- **Intro to Academy**: Free HackTheBox Course on using the Academy Platform
- **Javascript Deobfuscation**: Free HackTheBox Course on Deobfuscating Javascript
- **Learning Process**: Free HackTheBox Course on getting into the right mindset to learn.
- **Linux Privilege Escalation**: HackTheBox Course on Linux Privilege Escalation.  This cost 500 cubes, which is ~$50
- **Login Brute Forcing**: Free HackTheBox course on bruteforcing common logins
- **Network Enumeration with Nmap**: HackTheBox Course on using NMAP to its fullest.  This cost 50 cubes, which is ~$5
- **Secure Coding 101: Javascript**: HackTheBox Course on Javascript Coding.  This cost 1000 cubes, which is ~$100
- **Web Requests**: Free HackTheBox Course about HTTP or Web Requests
- **Whitebox Pentesting 101: Command Injection**: HackTheBox Course on Command Injection Vulnerabilities.  This cost 500 cubes, which is ~$50
- **Windows Fundamentals**: Free HackTheBox Introductory Course on Windows
