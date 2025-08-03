# 🚪 Room: HTTP in detail

## 🎯 Objectives
Learn about how you request content from a web server using the HTTP protocol

## 🛠️ Tools Used


## 💬 Summary
- What is HTTP(S)
- Requests and responses
- HTTP methods
- HTTP status codes
- Headers
- Cookies
- Making requests

-----

## Notes

### Task 1 - What is HTTP(S)

HTTP = HyperText Transfer protocol

HTTP is what's used whenever you view a website. Developed by Tim Berners-Lee and his team between 1989-1991. HTTP is the set of rules used for communication with web servers for transmitting of webpage data, whether thats HTML, images, videos, etc

HTTPS = HyperText Transfer protocol Secure

HTTPS is the secure version of HTTP. HTTPS data is encrypted so it not only stops people from seeing the data you are receiving and sending, but it also gives you assurances that you're talking to the correct web server and not something impersonating it.

-----

### Task 2 - Requests and responses

When we access a website, your browser will need to make requests to a web server for assets such as HTML, Images, and download the responses. Before that, you need to tell the browser sepcifically how and where to acess these resources, this is where URLs will help.

`URL` = Uniform Resource Locator

A URL is predominantly an instruction on how to access a recource on the internet. Below shows what a URL looks like with all its features:
```
http://user:password@tryhackme.com:80/view-room?id=1#task3
```
- `http` = Scheme - Instructs what protocol to use.
- `user:password` = User - Require authentication to log in.
- `tryhackme.com` = Host/Domain - The domain name.
- `80` = Port - The port you are going to connect to.
- `view-room` = Path - The file name or location of the resource.
- `?id=1` = Query String - extra information for the path
- `#task3` = Fragment - reference to a location on the page.


### Making a request

You can make a request to a web server with just one line:
```
GET/HTTP/1.1
```

For a better web experience, you'll need to send `headers`. Headers contain extra information to give to the web server you're communicationg with.

Example Request:
```
GET / HTTP/1.1

Host: tryhackme.com
User-Agent: Mozilla/5.0 Firefox/87.0
Referer: https://tryhackme.com/

```

- Line 1: The request is sending the GET method
- Line 2: Tell the web server we want the webiste `tryhackme.com`
- line 3: Tells the server what browser we are using
- Line 4: What page referred us to this page
- Line 5: HTTP requests always end with a blank line

Example response:
```
HTTP/1.1 200 OK

Server: nginx/1.15.8
Date: Fri, 09 Apr 2021 13:34:03 GMT
Content-Type: text/html
Content-Length: 98


<html>
  <head>
    <title>TryHackMe</title>
  </head>
  <body>
    Welcome To TryHackMe.com
  </body>
</html>
```

- Line 1: HTTP version
- Line 2: Tells us the web server software and version.
- Line 3: The current data, time, and timezone of the server.
- Line 4: Type of information being sent.
- Line 5: Length of response.
- Line 6: HTTP response blank line.
- Lines 7-14: The information requested.

-----

### Task 3 - HTTP Methods

HTTP methods are a way for the client to show their intended action when making a HTTP request.

- `GET request` - For getting information from a web server.
- `POST request` - For submitting data to the web server.
- `PUT request` - For submitting data to a server to update info.
- `DELETE request` - For deleting info/records for a web server.

-----

### Task 4 - HTTP Status Codes

The first line in the HTTP server response always contains a status code informing the client of the outcome of their request. 

### HTTP Status codes
- `100-199` - Information Response
- `200-299` - Success
- `300-399` - Redirection
- `400-499` - Client Errors
- `500-599` - Server Errors

### Common HTTP Status Codes
- `200` - OK
- `201` - Created
- `301` - Moved Permanently
- `302` - Found
- `400` - Bad request
- `401` - Not authorised
- `403` - Forbidden
- `404` - Page not found
- `405` - Method not allowed
- `500` - Internal service error
- `503` - Service unavailable

-----

### Task 5 - Headers

Headers are additional data that you can send to the web server when making requests.

Although no headers are strictly required when making a HTTP request, you'll find it difficult to view a website without them.

### common request headers

These are headers that are sent from the client to the server.

- `Host` - Some web servers host multiple websites so by providing the host header you can tell it which site you are requesting.
- `User-Agent` - This is your browser software and version number, this helps format the website properly.
- `Content-Length` - This tells the web server how much data to expect.
- `Accept-Encoding` - Tells the web server what types of compression methods the browser supports so the data can be made smaller for transmitting over the internet.
- `Cookie` - Data sent to the server to help remember your information.

### Common Response Headers
These are headers that are returned to the client from the server after a request.

- `Set-Cookie` - Information to store which gets sent back to the web server on each request.
- `Cache-Control` - How long to store the content of the response in the browser's cache before it requests it again.
- `Content-Type` - This tells the client what type of data is being returned.
- `Content-Encoding` - What method has been used to compress the data to make it smaller when sending over the internet.

-----

### Task 6 - Cookies

Cookies are small piece of data that is stored on your computer. Cookies are saved when you receive a `Set-Cookie` header from a web server. Every further request you make, you'll send the cookie data back to the web server. Becuase HTTP is stateless (doesn't keep track of your previous requests), cookies can be used to remind the web server who you are, some personal settings for the website or whether you've been to the website before. Let's take a look at this an example HTTP request:
```
GET /HTTP/1.1                                  The client requests
Host: cookies.thm                        <---  the webpage from
User-Agent: xxxx                               http://cookies.thm

HTTP/1.1 200 OK
Server: nginx/1.15.8                           The server responds
Date: Wed, 14 Apr 2021 09:08:19 GMT            back with a simple
Content-Type: text/html; charset=UTF-8   <---  webpage with a form
                                               asking for the users
HTML DATA...                                   name




-----

## Questions and Answers

### Task 1

**q1.** What does HTTP stand for?

Answer = HyperText Transfer Protocol


**q2.** What does the S in HTTPS stand for?

Answer = Secure


**q3.** On the mock webpage on the right there is an issue, once you've found it, click on it. What is the challenge flag?

Answer = THM{INVALID_HTTP_CERT}

-----

### Task 2

**q1.** What HTTP protocol is being used in the above example?

Answer = HTTP/1.1


**q2.**

What response header tells the browser how much data to expect?

Answer = Content-Length

-----

### Task 3

**q1.** What method would be used to create a new user account?

Answer = POST


**q2.** What method would be used to update your email address?

Answer = PUT


**q3.** What method would be used to remove a picture you've uploaded to your account?

Answer = DELETE


**q4.** What method would be used to view a news article?

Answer = GET

-----

### Task 4

**q1.** What response code might you receive if you've created a new user or blog post article?

Answer = 201


**q2.** What response code might you receive if you've tried to access a page that doesn't exist?

Answer = 404


**q3.** What response code might you receive if the web server cannot access its database and the application crashes?

Answer = 503


**q4.** What response code might you receive if you try to edit your profile without logging in first?

Answer = 401

-----

### Task 5

**q1.** What header tells the web server what browser is being used?

Answer = User-Agent


**q2.** What header tells the browser what type of data is being returned?

Answer = Content-Type


**q3.** What header tells the web server which website is being requested?

Answer = Host

-----

### Task 6



-----
