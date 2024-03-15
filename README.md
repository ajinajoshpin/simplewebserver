# EX01 Developing a Simple Webserver
## Date:15.03.2024

## AIM:
To develop a simple webserver to serve html pages.

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<head>
<title>Software Companies</title>
</head>
<body bgcolor="pink">
<table border="9" cellspacing="10" cellpadding="10" height="150" width="300" align="center">
<caption> <h3>Top Five Revenue Generating Sotware Companies </h3></caption>
<tr>
<th>COMPANIES</th>
<th>RANK</th>
<th>REVENUE</th>
</tr>
<tr>
<th>APPLE/th>
<th>8</th>
<th>$380.70 B</th>
</tr>
<tr>
<th>MICROSOFT</th>
<th>14</th>
<th>$227.58 B</th>
</tr>
<tr>
<th>ORACLE</th>
<th>32</th>
<th>$51.64 B</th>
</tr>
<tr>
<th>AMAZON</th>
<th>2</th>
<th>$574.78 B</th>
</tr>
<tr>
<th>GOOGLe/th>
<th>2$237.9 B</th>
<th>6</th>
</tr>
</table>
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
![Screenshot 2024-03-15 034125](https://github.com/ajinajoshpin/simplewebserver/assets/148514578/1e894221-99f5-4be0-b22a-9a25c5b82763)
![Screenshot 2024-03-15 034059](https://github.com/ajinajoshpin/simplewebserver/assets/148514578/18cd6388-bdf1-4527-b47c-c0b7f7cb57b3)



## RESULT:
The program for implementing simple webserver is executed successfully.
