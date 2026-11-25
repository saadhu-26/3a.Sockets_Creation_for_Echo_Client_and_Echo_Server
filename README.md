# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS

## AIM
To write a python program for creating Echo Client and Echo Server using TCP Sockets Links.

## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in server .
4. Send and receive the message using the send function in socket.

## PROGRAM

## Server
```
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Echo Server waiting for client...")
c, addr = s.accept()
print("Client connected:", addr)
while True:
    data = c.recv(1024).decode()
    if not data:
        break
    print("Received from client:", data)
    c.send(data.encode())
c.close()
s.close()
```
## Client
```
import socket
s = socket.socket()
s.connect(('localhost', 8000))
print("Connected to Echo Server")
while True:
    msg = input("Enter a message: ")
    if msg.lower() == "exit":
        break
    s.send(msg.encode())
    data = s.recv(1024).decode()
    print("Echo from server:", data)
s.close()
```
## OUPUT

## Server

<img width="668" height="198" alt="image" src="https://github.com/user-attachments/assets/6abbce18-db80-4590-ad45-f5105749718c" />

## Client

<img width="789" height="231" alt="image" src="https://github.com/user-attachments/assets/f327f6f3-5951-4626-b468-b0dd1c0672a0" />

## RESULT

Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links was successfully created and executed.
