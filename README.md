# 2a_Stop_and_Wait_Protocol
## NAME:N.KANNAN
## REG NO:2122223230097
## AIM 
To write a python program to perform stop and wait protocol.
## ALGORITHM
1. Start the program.
2. Get the frame size from the user.
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client.
6. Stop the Program.
## PROGRAM:
## Client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,address=s.accept()
while True:
    i = input("Enter a data:")
    c.send(i.encode())
    ack = c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```

## Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledment Received".encode())
```

## OUTPUT:
## CLIENT
![image](https://github.com/kannan-nagaraju/2a_Stop_and_Wait_Protocol/assets/145742755/b9056b50-3128-4b2a-9204-0851d5844096)

## SERVER:
![image](https://github.com/kannan-nagaraju/2a_Stop_and_Wait_Protocol/assets/145742755/f43d38be-4f63-4353-844a-15dea39edf0f)

## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
