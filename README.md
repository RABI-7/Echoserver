# Echoserver
Echo server and client using python socket
# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
## Server.py
```
import socket
HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
## Client.py
```
import socket
HOST = "127.0.0.1"  
PORT = 65432  
with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Name: RABI BASKAR PRABURAJAN, Date: 22-04-2026, Reg No: 212224040257")
    data = s.recv(1024)

print(f"Received {data!r}")
```
##  Architecture Diagram

```bash
+--------------------------+
|  User's Web Browser      |
|  (Client: Chrome/Firefox)|
+-----------+--------------+
            |
            |  HTTP Request (GET /)
            v
+-----------+--------------+
|   Python Web Server      |
| (http.server + Handler)  |
| - Listens on Port 8000   |
| - Handles GET Requests   |
| - Sends HTML Response    |
+-----------+--------------+
            |
            |  HTML Response
            v
+--------------------------+
|  User Sees Rendered Page |
|  <h1>Hello Web Server</h1>|
+--------------------------+
```


## OUTPUT:
### CLIENT OUTPUT:
<img width="1600" height="997" alt="image" src="https://github.com/user-attachments/assets/f782c589-39cc-4cd3-b681-20c7e8ecbbcb" />


### SERVER OUTPUT:
<img width="1600" height="999" alt="image" src="https://github.com/user-attachments/assets/4c7d68f4-fe2e-46bc-8e1c-6f324b8c4c13" />


## RESULT:
The program is executed succesfully
