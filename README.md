# Developing a Simple Webserver
## AIM:
To develop a simple webserver to display about top five programming languages

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
<h1>Python : python is an interpreted high-level general purpose programming languag......
Java : java is a object-oriented programming language that is designed to have as few implementation dependencis as possible.....
C program : c programming is a general-purpose,procedural computer programming language......
C++ program : C++ is a powerful general-purpose programming language,used to develop operating system......Swift : swift is a multi-paradigm,complied programming language</h1>
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
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:![output1](https://user-images.githubusercontent.com/94228215/143049038-dfbc69ba-6d1f-4236-aa99-9f095e659b5c.PNG)
![ouput2](https://user-images.githubusercontent.com/94228215/143049081-3c22b128-4798-4573-ab21-40c0374158cd.PNG)



## RESULT:
   Simple webserver is developed to display top five language
