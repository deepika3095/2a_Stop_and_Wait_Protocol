# NAME: DEEPIKA.R
# REG NO.:212223230038
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
## PROGRAM:
# CLIENT:
import socket

s=socket.socket()

s.bind(('localhost',8000))

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

# SERVER:
import socket

s=socket.socket()

s.connect(('localhost', 8000))

while True:

    print(s.recv(1024).decode())
    
    s.send("Acknowledgement Recived".encode()) 
## OUTPUT:
![Screenshot 2024-03-04 135600](https://github.com/deepika3095/2a_Stop_and_Wait_Protocol/assets/151625159/37a0d0bc-9f31-4e61-8a93-4d8d66bbafa5)

![Screenshot 2024-03-04 135555](https://github.com/deepika3095/2a_Stop_and_Wait_Protocol/assets/151625159/2c69e9cf-4a08-4907-ae4e-77fb7e8f97a3)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
