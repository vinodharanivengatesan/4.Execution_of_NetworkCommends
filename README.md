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
## Program

Server.py

import socket

from pythonping import ping

s = socket.socket()

s.bind(('localhost', 8000))

s.listen(5)

print("Ping Server started... Waiting for connection")

c, addr = s.accept()

print("Connected to:", addr)

while True:

 hostname = c.recv(1024).decode()
    
 if not hostname:
    
 break
  
  try:
    
   result = ping(hostname, count=4, verbose=False)
        
  c.send(str(result).encode())
  
  except:
        c.send("Host Not Found".encode())
c.close()

Client.py

import socket

s = socket.socket()


s.connect(('localhost', 8000))

while True:

 website = input("Enter the website you want to ping: ")
    
if website.lower() == "exit":
    
 break

s.send(website.encode())

  result = s.recv(1024).decode()
    
  print("\nPing Result:\n", result)

s.close()

Traceroute.py

import os

print("Running Traceroute...\n")

os.system("C:\\Windows\\System32\\tracert.exe google.com")

## Output
1)ping

<img width="841" height="353" alt="Screenshot 2026-03-21 191822" src="https://github.com/user-attachments/assets/40bf41b8-fceb-40ef-abaf-66b751fb773d" />

2)Tracert

<img width="1137" height="503" alt="Screenshot 2026-03-21 191958" src="https://github.com/user-attachments/assets/651dd9a5-1c5f-4cdc-92d5-4803c1dee231" />

3)ipconfig

<img width="1002" height="783" alt="Screenshot 2026-03-21 192054" src="https://github.com/user-attachments/assets/7fc9195d-ffe0-4249-8ae0-2250ed81ed10" />

4)netstat

<img width="869" height="960" alt="Screenshot 2026-03-21 192145" src="https://github.com/user-attachments/assets/0ea57e0e-cbb0-4ae2-a1b3-72109393468b" />

5)nslookup

<img width="694" height="612" alt="Screenshot 2026-03-21 192251" src="https://github.com/user-attachments/assets/31b0a6b3-1b4e-47d5-9fd3-5fa36d52b4a4" />

6)getmac

<img width="1013" height="160" alt="Screenshot 2026-03-21 192342" src="https://github.com/user-attachments/assets/05bef52b-04e2-4950-a44d-b8eba11e1a7b" />

7)nbstat

<img width="1227" height="604" alt="Screenshot 2026-03-21 192408" src="https://github.com/user-attachments/assets/c23f2bd7-cbf8-473d-943b-eeadc880f766" />

8)arp

<img width="1030" height="788" alt="Screenshot 2026-03-21 192435" src="https://github.com/user-attachments/assets/8c79456c-92d8-4254-820f-fdbc121f1b5d" />

9)systeminfo

<img width="765" height="896" alt="Screenshot 2026-03-21 192529" src="https://github.com/user-attachments/assets/3e84e60e-b632-4814-a0c0-fbd799faf942" />

## Result
Thus Execution of Network commands Performed 
