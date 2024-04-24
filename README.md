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

##CODE

CLIENT
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
SEREVR
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode()) 
```
TRACERT
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans) 
```
## Output
CLIENT
![Screenshot 2024-04-24 154447](https://github.com/mades2112/4.Execution_of_NetworkCommends/assets/152461996/238c9283-2f77-4bc3-8c9a-e5e04812e49d)


SERVER
![Screenshot 2024-04-24 154505](https://github.com/mades2112/4.Execution_of_NetworkCommends/assets/152461996/4b7a9d02-cee4-4c56-827c-99255e872494)


TRACERT
![Screenshot 2024-04-24 060634](https://github.com/mades2112/4.Execution_of_NetworkCommends/assets/152461996/a1ee8b77-f64c-4f02-b376-5ae61da26a91)


## Result
Thus Execution of Network commands Performed 
