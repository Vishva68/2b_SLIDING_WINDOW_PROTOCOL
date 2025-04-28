# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME :Vishvanandh N
## REG NO.: 212224240186
## AIM
IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
```
CLIENT:

import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s
 ```
```
SERVER:
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT

![Screenshot 2025-03-19 103716](https://github.com/user-attachments/assets/915bc668-87cc-4138-b85b-f23495384de2)
![Screenshot 2025-03-19 103755](https://github.com/user-attachments/assets/32c4724e-1f10-4c72-a9d2-c6d8917d434e)





## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
