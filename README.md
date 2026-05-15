# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
'''
SERVER:
server:
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
       ip=c.recv(1024).decode()
       try:
          c.send(address[ip].encode())
       except KeyError:
          c.send("Not Found".encode())
CLIENT:
client:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())
'''
## OUPUT - ARP
<img width="1909" height="873" alt="Screenshot 2026-05-15 140552" src="https://github.com/user-attachments/assets/3117313d-c73b-4820-a04a-98abf2a1d10d" />
<img width="1348" height="913" alt="Screenshot 2026-05-15 140608" src="https://github.com/user-attachments/assets/3a9fcd6b-e4ee-4cbd-a634-050469f60cea" />
## PROGRAM - RARP
'''
SERVER:

## OUPUT -RARP
## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
