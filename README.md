# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM

To write a python program to Implement Sliding window protocol.

## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
~~~
Developed by : W Allen Johnston Ozario
Reg no : 212224110004
~~~
~~~
Client:

import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("enter window size : "))
st= 0
i=0
while True:
    while(i<len(l)):
        st+=s
        c.send(str(l[i:st]).encode())
        ack=c.recv(1024).decode()
        if ack:
            print(ack)
            i+=s
~~~
~~~
Server :

import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recived".encode())

~~~

## OUPUT
![Screenshot 2025-03-27 105157](https://github.com/user-attachments/assets/17568950-4214-40b3-9e22-aff954202ae5)

![Screenshot 2025-03-27 105203](https://github.com/user-attachments/assets/4f45d6f7-b913-4304-9abc-8541f186afbf)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
