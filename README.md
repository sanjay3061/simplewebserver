# Developing a Simple Webserver
## AIM:
To develop a simple webserver to serve html pages.
## DATE:07-10-2023
## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Top 5 Revenue generating software Companies<h1>
<UL TYPE=“circle”>
<LI> zoho </LI>		
<LI> apple </LI>
<LI> infosys </LI>
<LI> accenture </LI>
<LI> microsoft </LI>
</UL>
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

![image](https://github.com/sanjay3061/simplewebserver/assets/121215929/5561a52f-3c8f-4795-8b78-08fbccebf315)

![image](https://github.com/sanjay3061/simplewebserver/assets/121215929/d1c418ec-9a31-4f03-b66f-2f4fc765aa75)



## RESULT:
The program for implementing simple webserver is executed successfully.
