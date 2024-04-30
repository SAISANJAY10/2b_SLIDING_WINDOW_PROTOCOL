# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
Client.py
```
import socket 
s=socket.socket() 
s.bind(('localhost',8000)
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
Server.py
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```

## OUPUT

![Screenshot 2024-04-30 084221](https://github.com/SAISANJAY10/2b_SLIDING_WINDOW_PROTOCOL/assets/144228073/a12fa4ae-e39c-49cc-a0c6-a3280a638960)

![Screenshot 2024-04-30 084240](https://github.com/SAISANJAY10/2b_SLIDING_WINDOW_PROTOCOL/assets/144228073/c3ea9165-86f6-4f34-a288-bf9a547b67c0)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
