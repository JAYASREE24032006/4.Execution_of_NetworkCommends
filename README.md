# EX.NO.04 - Execution_of_NetworkCommands

**DATE : 17.04.2024**

## AIM :

Use of Network commands in Real Time environment
## Software : 

Command Prompt And Network Protocol Analyzer
## Procedure: 
To do this EXPERIMENT- follows these steps:

In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 

All commands related to Network configuration which includes how to switch to privilege mode

and normal mode and how to configure router interface and how to save this configuration to

flash memory or permanent memory.

This commands includes

• Configuring the Router commands

• General Commands to configure network

• Privileged Mode commands of a router 

• Router Processes & Statistics

• IP Commands

• Other IP Commands e.g. show ip route etc.


## PROGRAM
**CLIENT**
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
**SERVER**
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
**TRACEROUTE COMMAND**
```
from scapy.all import*     
target = ["www.google.com"]     
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```

## Output

**CLIENT**
![image](https://github.com/JAYASREE24032006/4.Execution_of_NetworkCommends/assets/144360800/d637f77d-fd19-420d-9292-1d20231f7efd)
**SERVER**
![image](https://github.com/JAYASREE24032006/4.Execution_of_NetworkCommends/assets/144360800/59d24a6c-0a4a-481d-96a8-66914b3484a6)
**TRACEROUTE COMMAND**
![image](https://github.com/JAYASREE24032006/4.Execution_of_NetworkCommends/assets/144360800/004e16f4-be13-42a8-b9e8-4df61442a7c5)





## Result
Thus Execution of Network commands Performed 
