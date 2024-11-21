# Ex No:1a  Stop and Wait Protocol

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
### CLIENT
```py
import socket
s=socket.socket()
s.bind(('localhost', 8000))
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
### SERVER
```py
import socket
s=socket.socket()
s.connect(('localhost', 8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())

```
## OUTPUT
### CLIENT OUTPUT
![Screenshot 2024-11-21 173341](https://github.com/user-attachments/assets/76ea72f2-95ba-4db1-a1c6-13b29f38a661)

### SERVER OUTPUT
![Screenshot 2024-11-21 173400](https://github.com/user-attachments/assets/b9ea4207-ddb9-49d7-91aa-bbaa1801ff04)


## RESULT

Thus,python program to perform stop and wait protocol was successfully executed.
