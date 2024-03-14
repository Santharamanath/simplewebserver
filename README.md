# EX01 Developing a Simple Webserver
## Date:25.02.2024

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
<!DOCTYPE html>
<html>
<head>
<title>TOP 5 COMPANIES</title>
</head>
<body>
<table border="4" cellspacing="8" cellpadding="5" width="50" height="50">
<h1>TOP 5 COMPANIES</h1>
<tr>
<th>RANK</th>
<th>NAME OF THE COMPANY</th>
<th>REVENUE( in USD millions)</th>
</tr>
<tr>
<td>01.</td>
<td>WALMART</td>
<td>$611,289
</tr>
<tr>
<td>02.</td>
<td>SAUDI ARAMCO</td>
<td>$603,651</td>
</tr>
<tr>
<td>03.</td>
<td>AMAZON</td>
<td>$574,785</td>
</tr>
<tr>
<td>04.</td>
<td>VITOL</td>
<td>$505,000</td>
</tr>
<tr>
<td>05.</td>
<td>APPLE</td>
<td>$394,328</td>
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
![alt text](<Screenshot 2024-03-15 034627.png>)
![alt text](<Screenshot 2024-03-15 035433.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
