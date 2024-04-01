# EX 4 - Execution_of_NetworkCommands
## AIM :
Use of Network commands in Real Time environment
## Software : 
Command Prompt And Network Protocol Analyzer
## Procedure: 
To do this EXPERIMENT- follows these steps:
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer.All commands related to Network configuration which includes how to switch to privilege modeand normal mode and how to configure router interface and how to save this configuration toflash memory or permanent memory.
This commands includes:

1.Configuring the Router commands

2.General Commands to configure network

3.Privileged Mode commands of a router 

4.Router Processes & Statistics

5.IP Commands

6.Other IP Commands e.g. show ip route etc.
## Program:
### PING COMMAND
#### CLIENT
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
#### SERVER
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
### TRACEROUTE COMMAND
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output:
### PING COMMAND
#### CLIENT

![image](https://github.com/VaradaramSK/4.Execution_of_NetworkCommends/assets/144356171/7d14097a-a1d9-485d-be13-94b157c271d6)

#### SERVER

![image](https://github.com/VaradaramSK/4.Execution_of_NetworkCommends/assets/144356171/55491c3f-2427-4ee9-a0fb-530c80b5cd29)

### TRACEROUTE COMMAND

![image](https://github.com/VaradaramSK/4.Execution_of_NetworkCommends/assets/144356171/1f5d8901-9514-44f9-a3fa-f700c40303f4)

## Result:
Thus Execution of Network commands Performed 
