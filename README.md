# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## client
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
## server
```import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## client
![Screenshot 2025-03-06 051433](https://github.com/user-attachments/assets/bd07a5cc-2230-4e88-92b5-50da88e3bd5b)
## server
![Screenshot 2025-03-06 051445](https://github.com/user-attachments/assets/891a607f-c402-4879-9536-fd096b38cc96)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.


