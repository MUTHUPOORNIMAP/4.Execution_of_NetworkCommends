# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## Program:
Client:
```
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost'8000))
s.listen(5)
c,addr=s.accept()
while True:
   hostname=c.recv(1024).decode()
   try:
      c.send(str(ping(hostname, verbose=False)).encode())
   except KeyError:
      c.send("Not Found".encode())
```
Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
   ip=input("Enter the website you want to ping ")
   s.send(ip.encode())
   print(s.recv(1024).decode())
```
Tranceroute Command:
```
from scapy.all import*
target = ["www.google.com"]
result, unans = traceroute(target,maxttl=32)
print(result,unans)
```
## Output:

Client:

<img width="829" height="98" alt="image" src="https://github.com/user-attachments/assets/ef7e41dd-db2c-4bbf-81da-2360173a5b52" />

Server:

<img width="717" height="530" alt="image" src="https://github.com/user-attachments/assets/b3f79cda-5e27-4af5-b229-949cf960886a" />

Tranceroute:

<img width="611" height="271" alt="image" src="https://github.com/user-attachments/assets/44b02653-f424-4981-ad5d-7340904b1e9e" />

## Result
Thus Execution of Network commands Performed 
