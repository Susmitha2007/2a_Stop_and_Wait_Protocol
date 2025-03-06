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
### server.py
```python
import socket
s=socket.socket()
s.bind(('localhost', 8000))
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
### client.py
```python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT

![alt text][Screenshot 2025-03-06 051220](https://github.com/user-attachments/assets/daf5abcc-da07-4f4c-bd96-59dcefa240c0)
![alt text][Screenshot 2025-03-06 051207](https://github.com/user-attachments/assets/488f64ea-3256-4a14-89ef-66bdf9bec18d)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.

