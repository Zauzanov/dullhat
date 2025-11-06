<p align="center">
  <h1 align="center"> dullhat Net Tool </h1>
</p>

## 🚀 Quick Start
## 1. Download 'dullhat.py' file and run it like this to open the helper:
```bash
python dullhat.py -h
python dullhat.py --help

#WARNING!
# flags for listeners(server) only: -c, -e, -u, -l
# flags for senders(client): -t, -p 
```
## 2. Upload files to the server:
```bash
# Run on the server(receiver/Terminal 1)
python dullhat.py -t 192.168.204.139 -p 1234 -l -u=arp01.py

# Run on the client machine(Terminal 2):
nc 192.168.204.139 1234 < arp01.py
```
## 3. Get a Command Shell:  
```bash
On the server(Terminal 1):
python dullhat.py -t 192.168.204.139 -p 1234 -l -c         

# On your own client machine(Terminal 2):
python dullhat.py -t 192.168.204.139 -p 1234                            
```
## 4. Command execution:
``` bash
# On the server:
python dullhat.py -t 192.168.204.139 -p 1234 -l -e="cat /etc/passwd"

# On the client:
python dullhat.py -t 192.168.204.139 -p 1234
```
## 5. Sending requests:
```bash
echo -ne 'GET / HTTP/1.1\r\nHost: 192.168.204.129\r\n\r\n' | python dullhat.py -t 192.168.204.129 -p 80
```

OUTPUT:
```bash
HTTP/1.1 200 OK
Date: Fri, 31 Oct 2025 18:31:22 GMT
Server: Apache/2.2.8 (Ubuntu) DAV/2
X-Powered-By: PHP/5.2.4-2ubuntu5.10
Content-Length: 891
Content-Type: text/html

<html><head><title>Metasploitable2 - Linux</title></head><body>
<pre>

                _                  _       _ _        _     _      ____  
 _ __ ___   ___| |_ __ _ ___ _ __ | | ___ (_) |_ __ _| |__ | | ___|___ \ 
| '_ ` _ \ / _ \ __/ _` / __| '_ \| |/ _ \| | __/ _` | '_ \| |/ _ \ __) |
| | | | | |  __/ || (_| \__ \ |_) | | (_) | | || (_| | |_) | |  __// __/ 
|_| |_| |_|\___|\__\__,_|___/ .__/|_|\___/|_|\__\__,_|_.__/|_|\___|_____|
                            |_|                                          


Warning: Never expose this VM to an untrusted network!

Contact: msfdev[at]metasploit.com

Login with msfadmin/msfadmin to get started


</pre>
<ul>
<li><a href="/twiki/">TWiki</a></li>
<li><a href="/phpMyAdmin/">phpMyAdmin</a></li>
<li><a href="/mutillidae/">Mutillidae</a></li>
<li><a href="/dvwa/">DVWA</a></li>
<li><a href="/dav/">WebDAV</a></li>
</ul>
</body>
</html>

```
