# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## Name: Mugil Raj S A
## Register No: 212223220062
## AIM:
To perform a study on sliding window protocol.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### Client:
```import socket
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
### Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
### Client:

![Screenshot 2024-05-14 173942](https://github.com/MugilRaj1105/2b_SLIDING_WINDOW_PROTOCOL/assets/154905390/9c357900-1ac7-4b46-ad45-f32c13f596c0)

### Server:

![Screenshot 2024-05-14 174012](https://github.com/MugilRaj1105/2b_SLIDING_WINDOW_PROTOCOL/assets/154905390/436ea035-569e-4df0-84cd-33e9b515c648)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
