# EX01 Developing a Simple Webserver
## Date:
25-10-2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Laptop configuration</h1>
<table border="2">
    <tr>
        <th>System Configuration
        </th>
        <th>Description
        </th>
    </tr>
    <tr>
        <td>Processor
        </td>
        <td>i7 - 13th Gen
        </td>
    </tr>
    <tr>
        <td>Primary Memory
        </td>
        <td>16 GB
        </td>
    </tr>
    <tr>
        <td>Secondary Memory</td>
        <td>512 GB</td>
    </tr>
    <tr>
        <td>OS</td>
        <td>Windows 11</td>
    </tr>
    <tr>
        <td>Model Name</td>
        <td>Lenovo Ideapad Slim 3</td>
    </tr>
</table>
</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```

## OUTPUT:

![alt text](image.png)

## RESULT:
The program for implementing simple webserver is executed successfully.
