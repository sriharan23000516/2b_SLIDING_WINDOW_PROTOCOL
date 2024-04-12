# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

## Developed By : SRIHARAN JV
## Register No  : 212223100054

## AIM
## ALGORITHM:
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

## server.py
```
  import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
 ```
## OUPUT
## Client:
![321523440-aa3a56ef-9ff1-4276-8cd6-e938a103f2d5](https://github.com/sriharan23000516/2b_SLIDING_WINDOW_PROTOCOL/assets/139841769/4f83a8f6-09a4-4cda-b662-1a8f0a430bf8)

## Server :
![321523484-05384699-a28d-44f3-b62f-e58936da0e7a](https://github.com/sriharan23000516/2b_SLIDING_WINDOW_PROTOCOL/assets/139841769/67f735ae-5055-4db7-9d29-f58166dbeaf4)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
