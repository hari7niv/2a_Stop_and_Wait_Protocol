# 2a_Stop_and_Wait_Protocol
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
## client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
  data = input("Enter a data: ")  
  c.send(data.encode()) 
  ack =c.recv(1024).decode()  
  if ack:
      print(f"Received: {ack}") 
  else:
      print("No acknowledgement, closing connection")
      break
```
## server:
```
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
  data = s.recv(1024).decode() 
  print(f"Received: {data}") 
```
## OUTPUT
![image](https://github.com/user-attachments/assets/6f71a527-c00d-4574-aa39-230e34ed5040)

![image](https://github.com/user-attachments/assets/de1e0a32-c6bf-4965-87dd-50485436f947)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
