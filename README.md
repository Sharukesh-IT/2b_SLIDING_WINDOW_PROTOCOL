# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
NAME:sharukesh.s

REG NO 212224220095
## AIM
To write a python program to perform IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
SERVER 
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True:    
    print(s.recv(1024).decode()) 
    s.send("acknowledgement recived from the server".encode())

CLIENT
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
## OUPUT
<img width="1918" height="1141" alt="Screenshot 2025-09-03 115407" src="https://github.com/user-attachments/assets/b93e19f6-0082-45f0-9a74-c98bb3b2cfeb" />
<img width="1918" height="1137" alt="Screenshot 2025-09-03 115501" src="https://github.com/user-attachments/assets/8728e702-4e02-4444-92c8-5da5f36c837a" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
