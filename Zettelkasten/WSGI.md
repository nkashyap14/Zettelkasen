# WSGI

- Web Server Gateway Interface
- Specification for a simple and universal interface between web servers and web applications or frameworks for the [[Python]] programming language
- Used to ensure easy interoperability between different web servers and web applications written in python making it easy to develop and deploy python web applications
- WSGI servers as a middle layer/ [[middleware]] between the [[web server]] and the web app
- When a web server receives a request from the client it passes the request details to a WSGI application
- The application processes the request and returns the response to the server which then sends it back to the client
- On the application side a WSGI-compatibly web application must implement a callable (usually a function or method) that accepts two arguments: an environment (a dictionary containing request data) and a start_response callable (a function provided by the server used to begin the HTTP response). 
- On the server side the web server implements the WSGI interface to communicate with the web application. Calls the applications callable, passing the environment and the start_response callable and then transmits the applications response back to the client

---
Links :: [[Computer Science]] [[System Design]] [[Distributed Systems]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-02 00:32
