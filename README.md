# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
SERVER:

      import socket
      
      HOST = '127.0.0.1'  
      PORT = 65432        
      
      with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as server_socket:
          server_socket.bind((HOST, PORT))
          server_socket.listen()
      
          print(f"Server is listening on {HOST}:{PORT}")
          while True:
              conn, addr = server_socket.accept()
              with conn:
                  print(f"Connected by {addr}")
                  while True:
                      data = conn.recv(1024)
                      if not data:
                          break
                      conn.sendall(data)
                      print(f"Echoed: {data.decode('utf-8')}")
CLIENT:

        import socket
        
        HOST = '127.0.0.1'  
        PORT = 65432  
        
        with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as client_socket:
            client_socket.connect((HOST, PORT))
        
            message = 'Hello, Server!'
            client_socket.sendall(message.encode('utf-8'))
        
            data = client_socket.recv(1024)
            print(f"Received echo: {data.decode('utf-8')}")
 
## OUPUT
1. Server
![image](https://github.com/user-attachments/assets/24b79f07-d279-482f-8b6c-90cbcaf11321)

2. Client
![image](https://github.com/user-attachments/assets/e444b4b8-01b9-45d8-b4c1-1dc3106a9d03)

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
