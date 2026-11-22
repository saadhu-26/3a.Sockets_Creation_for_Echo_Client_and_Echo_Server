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
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
host = '127.0.0.1'
port = 5000
server_socket.bind((host, port))
server_socket.listen(1)

print("Echo Server is waiting for connection...")
client_socket, addr = server_socket.accept()
print("Connected to:", addr)
while True:
    data = client_socket.recv(1024).decode()
    if not data:
        break
    print("Client:", data)
    client_socket.send(data.encode())
client_socket.close()
server_socket.close()
```
## Client
```
import socket
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
host = '127.0.0.1'
port = 5000
client_socket.connect((host, port))
while True:
    message = input("Enter message: ")
    if message.lower() == 'exit':
        break
    client_socket.send(message.encode())
    data = client_socket.recv(1024).decode()
    print("Server echoed:", data)
client_socket.close()
```

## OUPUT

## Server

<img width="1121" height="366" alt="image" src="https://github.com/user-attachments/assets/0a257f12-c7d3-4507-b05e-6c59eebd832e" />

## Client

<img width="1118" height="342" alt="image" src="https://github.com/user-attachments/assets/34e0f2e3-2853-4d95-b47f-a28eb1fc38d5" />

## RESULT

Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links was successfully created and executed.
