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
## client.py
```
import socket

s = socket.socket()

s.connect(('localhost', 8000))

while True:
    print(s.recv(1024).decode())

    s.send("Acknowledgement Received".encode())
```

## Server.py

```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Server is waiting for connection...")

conn, addr = s.accept()
print("Connected:", addr)

while True:
    msg = input("Enter message: ")
    conn.send(msg.encode())

    print(conn.recv(1024).decode())
```
## OUTPUT
<img width="952" height="187" alt="Screenshot 2026-11-02 133743" src="https://github.com/user-attachments/assets/28b1511a-a209-4913-b39e-018311bb70b7" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
