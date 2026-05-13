# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol.
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
## CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter the data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close
        break
```
## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```
## OUTPUT:
## CLIENT:
<img width="1728" height="342" alt="Screenshot 2026-05-13 151749" src="https://github.com/user-attachments/assets/441ea090-66f0-4acb-ad79-215caea79417" />

## SERVER:
<img width="1735" height="347" alt="Screenshot 2026-05-13 151806" src="https://github.com/user-attachments/assets/dc9511e0-28f1-4709-9818-aa57cc1840ee" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
