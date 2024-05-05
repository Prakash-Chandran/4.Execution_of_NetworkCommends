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
CLIENT :
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
SERVER:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode()) 
```
TRACER:
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output
CLIENT:

![325460808-6095ea6e-67de-4ce5-bf3d-650f20d9dd5c](https://github.com/Prakash-Chandran/4.Execution_of_NetworkCommends/assets/147120899/9f71fc28-cdde-4bfd-8796-f0eec6a72389)


SERVER:

![324173565-497c329a-2f74-40ec-a51d-6eeb2646ff49](https://github.com/Prakash-Chandran/4.Execution_of_NetworkCommends/assets/147120899/e224605a-94d0-47d6-b1e8-27556f79e99d)


TRACER:

![325460700-01764015-00f7-4c30-830f-3f2cc2f2816f](https://github.com/Prakash-Chandran/4.Execution_of_NetworkCommends/assets/147120899/33d26c21-83fd-4760-8ebb-d520eb9d2113)



## Result
Thus Execution of Network commands Performed Successfully.
