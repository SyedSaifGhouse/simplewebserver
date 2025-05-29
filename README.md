
 EX01 Developing a Simple Webserver
## Date:27/05/2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler

# Corrected HTML content
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>TCP/IP Protocol Suite</title>
    <style>
        body {
            background-color: #f0f4f8;
            margin: 0;
            padding: 0;
        }

        .head-box {
            border: 2px solid black;
            border-radius: 20px;
            text-align: center;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            font-size: large;
            width: 60%;
            margin: 20px auto;
            background: linear-gradient(to bottom, #c8e6f9, #90caf9);
            color: #000;
            padding: 20px;
        }

        .info-box {
            margin: 20px auto;
            width: 600px;
            height: 600px;
            border-radius: 20px;
            overflow: hidden;
            border: 2px solid black;
            box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .info-box table {
            width: 100%;
            height: 100%;
            border-collapse: collapse;
            table-layout: fixed;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        .info-box th, .info-box td {
            border: 1px solid #555;
            text-align: center;
            padding: 0;
            margin: 0;
            height: 25%;
            vertical-align: middle;
            background-color: #e3f2fd;
            font-size: 16px;
        }

        .info-box th {
            background-color: #1976d2;
            color: white;
            font-size: 18px;
        }

        .info-box tr:nth-child(even) td {
            background-color: #bbdefb;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="head-box">
            <h1>TCP/IP Protocol Suite Overview</h1>
        </div>

        <div class="info-box">
            <table>
                <tr><th>TCP/IP Layer</th><th>Example Protocols</th></tr>
                <tr><td>Application Layer</td><td>HTTP, FTP, SMTP, DNS, DHCP</td></tr>
                <tr><td>Transport Layer</td><td>TCP, UDP</td></tr>
                <tr><td>Internet Layer</td><td>IP (IPv4, IPv6), ICMP, ARP, IGMP</td></tr>
                <tr><td>Network Access Layer</td><td>Ethernet, Wi-Fi, PPP, SLIP</td></tr>
            </table>
        </div>
    </div>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
![alt text](<Screenshot 2025-05-18 163713.png>)

![alt text](<Screenshot 2025-05-18 163909.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
