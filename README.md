# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
server:
```
File SERVER (fileserver.py)
import socket
# Create socket
server = socket.socket()
# Bind IP and port
server.bind(("127.0.0.1", 5555))
# Listen for client
server.listen(1)
print("Server waiting for connection...")
# Accept client
client, addr = server.accept()
print("Connected to:", addr)
# Ask filename
filename = input("Enter file name to send: ")
# Open and send file
with open(filename, "rb") as file:
 data = file.read()
 client.send(data)
print("File sent successfully")
# Close connections
client.close()
server.close()
```
client:
```
import socket
# Create socket
client = socket.socket()
# Connect to server
client.connect(("127.0.0.1", 5555))
# Save file name
save_name = input("Enter name to save file: ")
# Receive data
data = client.recv(1000000)
# Save file
with open(save_name, "wb") as file:
 file.write(data)
print("File received successfully")
# Close connection
client.close()
```
## OUPUT
<img width="947" height="1074" alt="image" src="https://github.com/user-attachments/assets/04062112-53fe-4096-964e-1eb5532c8ada" />
<img width="963" height="1079" alt="image" src="https://github.com/user-attachments/assets/3305ce5b-1db1-46f0-9aa2-2952f0147dd7" />
<img width="961" height="718" alt="image" src="https://github.com/user-attachments/assets/01508d30-cc05-40ed-959d-075b6b68022b" />
<img width="945" height="737" alt="image" src="https://github.com/user-attachments/assets/87cd0937-5ee3-4e69-9f1c-ceafc3e93cb2" />



## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
