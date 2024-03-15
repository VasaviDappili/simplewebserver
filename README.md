# EX01 Developing a Simple Webserver
## Date:27-02-2024

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
content = """<html>
<head>
<title>Top Software companies in revenue</title>
</head>
<body>
<h1 align="left">TOP SOFTWARE COMPANIES IN REVENUE</h1>
<table border="2" cellspacing="5" cellpadding="5" width="40" height="50">
<tr>
<th>S.NO</th>
<th>COMPANY</th>
<th>RANK</th>
<th>REVENUE FROM SOFTWARE ACTIVITY</th>
<th>TOTAL REVENUES</th>
<th>NATIONALITY</th>
</tr>
<tr>
<td>1</td>
<td>SAP</td>
<td>1</td>
<td>10672.0</td>
<td>10672.0</td>
<td>GERMANY</td>
</tr>
<tr>
<td>2</td>
<td>SAGE</td>
<td>3</td>
<td>1614.1</td>
<td>1614.1</td>
<td>BRITISH</td>
</tr>
<tr>
<td>3</td>
<td>SOFTWARE AG</td>
<td>4</td>
<td>847.4</td>
<td>847.4</td>
<td>GERMANY</td>
</tr>
<tr>
<td>4</td>
<td>AUTONOMY</td>
<td>5</td>
<td>820.0</td>
<td>820.0</td>
<td>UK</td>
</tr>
<tr>
<td>5</td>
<td>MISYS</td>
<td>6</td>
<td>523.6</td>
<td>1126.1</td>
<td>UK</td>
</tr>
<tr>
<td>6</td>
<td>VISMA</td>
<td>7</td>
<td>386.5</td>
<td>386.5</td>
<td>NORWEGIAN AND SWEDISH</td>
</tr>
<tr>
<td>7</td>
<td>SWIFT</td>
<td>8</td>
<td>471.6</td>
<td>586.1</td>
<td>BELGIUM</td>
</tr>
<td>8</td>
<td>MICRO FOCUS</td>
<td>9</td>
<td>453.0</td>
<td>453.0</td>
<td>BRITISH</td>
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

![alt text](<Screenshot (19).png>)
![alt text](<Screenshot (20).png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
