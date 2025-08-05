# 🚪 Room: Putting it all together

## 🎯 Objectives
- Learn how all the individual components of the web work together to bring you access to your favourite web sites.

## 🛠️ Tools Used
-

## 💬 Summary
- Putting it all together
- Other components
- How web servers work
- Quit

-----

## Notes

### Task 1 - Putting it all together

To summarise, when you request a website, your computer needs to know the server's IP address it needs to talk to; for this, it uses DNS. Your computer then talks to the web server using a special set of commands called the HTTP protocol; the webserver then returns HTML, JavaScript, CSS, Images, etc., which your browser then uses to correctly format and display the website to you.

-----

### Task 2 - Other Components

#### Load balencers

When a website's traffic starts getting quite large or is running an application that needs to have high availability, one web server may not be enough to handle the load. Load balancers provide two main features, ensuring high trafiic websites can handle the load and providing a failover if a server becomes unresponsive.

When you request a website with a load balancer, the load balancer will receive your request first and then forward it to one of the mulitple servers behind it. The load balancer uses diffrent algorithms to help it decide which server is best to deal with the request. A couple of examples of these algorithms are `round-robin`, which sends it to each server in turn, or `weighted`, which checks how many requests a server is currently dealing with and sends it to least busy server.

Load balancers also perform periodic checks with each server to ensure they are running correctly; this is called a `health check`. If a server doesn't respond appropriately or doesn't respond, the load balencer will stop sending traffic until it responds appropriately again.


#### CDN (Content Delivery Networks)

A CDN can be an excellent resource for cutting down traffic by allowing you to host static files from your website, such as JavaScript, CSS, Images, Videos, and host them across thousands of servers all over the world. When a user requests one of the hosted files, teh CDN works out where the nearest server is physically located and sends the request there instead of sending the data from the other side of the world.


#### Databases

Often websites will need a way of stroing information for their users. Webservers can communicate with databases to store and recall data from them. Databases can range from just a simple plain text file up to complex clusters of multiple servers providing speed and resilience. You'll come across some common databases: MySQL, MSSQL, MongoDB, PostGres, and more; each has its specific features.

#### WAF (Web Application Firewall)

A WAF sits between your web request and the web server; its purpose is to protect the webserver from hacking or denial of service attacks. It analyses the web requests for common attack techniques, whether the request is from a real browser rather than a bot. It also checks if an excessive amount of web requests are being sent by utilising something called rate limiting, which only allow a certain amount of requests from an IP per second. If a request is deemed a potential attack, it will be dropped and never sent to the webserver.

-----

### Task 3 - How web servers work

#### What is a web server

A web server is a software thats listening for incoming connections and then utilises the HTTP protocol to deliver web content to its client. Some of the most common web server software is `Apache`, `Nginx`, `IIS`, and `NodeJS`. A web server delivers files from what's called its root directory, which is defined in the software settings. 

#### Virtual Hosts

Web servers can host multiple websites with diffrent domain names; to achieve this, they use virtual hosts. The web server software checks the hostname being requested from the HTTP headers and matches that against its virtual hosts (virtual hosts are text-based configuration files). If it finds a match, the correct website will be provided. If not match is found, the default website will be provided instead.

Virtual hosts can have their root directory mapped to different locations on the hard drive. For example, `one.com` being mapped to /var/www/website_one, and `two.com` being mapped to /var/www/website_two

There is no limit to the number of diffrent websites you can host on a web server.

#### Static Vs Dynamic content

Static content is content that never changes. Common examples are pictures, javascript, CSS, etc., but can also include HTML that never changes. These are files that are directly served from the webserver with no changes made to them.

Dynamic content is content that could change with different requests. An example of dynamic content would be a blog. The homepage of the blog will show you the latest entry. If a new entry is created, then the homepage needs to display the latest entry. 

These changes to what you end up seeing are done on the `backend` with the use of programming and scripting languages. It is called `backend` because it is all happening behind the sceens. 

#### Scripting and backend languages

There's not much of a limit to what a backend language can achieve, and these are what make a webiste interactive to the user. Some of these languages are:
- PHP
- Python
- Ruby
- NodeJS
- Perl

These languages can interact with dabases, call external services, process data from the user, and more.

-----

## Questions and Answers

### Task 1

**q1.** I've read this...

Answer = No answer needed

-----

### Task 2 

**q1.** What can be used to host static files and speed up a clients visit to a website?

Answer = CDN


**q2.** What does a load balancer perform to make sure a host is still alive?

Answer = health check


**q3.** What can be used to help against the hacking of a website?

Answer = WAF

-----

### Task 3 

**q1.** What does web server software use to host multiple sites?

Answer = Virtual Hosts


**q2.** What is the name for the type of content that can change?

Answer = Dynamic


**q3.** Does the client see the backend code? Yay/Nay

Answer = Nay

-----

### Task 4

**q1.** Flag

Answer = THM{YOU_GOT_THE_ORDER}

-----









