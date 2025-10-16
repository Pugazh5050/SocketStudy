# Ex.No:1a  			Study of Socket Programming
## NAME: 	PUGAZHALENTHI V
## REG NO : 212224100047


## Aim: 
To write a python program to perform sliding window protocol
## ALGORITHM:
ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
6. Stop the program
PROGRAM:

SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
CLIENT
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 continue
 else:
 c.close()
 break
```
## OUTPUT:

## server.py

<img width="466" height="262" alt="image" src="https://github.com/user-attachments/assets/e0c7b18c-c463-4452-bab4-7f330689fa87" />

## client.py

<img width="462" height="307" alt="image" src="https://github.com/user-attachments/assets/06b1a765-f0ba-4c52-8941-71988406f196" />

 
## Result:
Thus the study of Socket Programming Completed Successfully
