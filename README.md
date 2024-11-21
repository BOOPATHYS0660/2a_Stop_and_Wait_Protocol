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
![CLIENT](https://github.com/c-sanjay/2a_Stop_and_Wait_Protocol/assets/147139405/083f9ced-4a81-4324-8cb4-f4d73a442a39)

### SERVER OUTPUT
![SERVER](https://github.com/c-sanjay/2a_Stop_and_Wait_Protocol/assets/147139405/28f3d13a-6ded-4b48-bcbd-e825661904b6)


## RESULT

Thus,python program to perform stop and wait protocol was successfully executed.
