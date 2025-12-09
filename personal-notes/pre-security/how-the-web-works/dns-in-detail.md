e# 🚪 Room: DNS in Detail

## 🎯 Objectives
- Learn how DNS works and how it helps you access internet services.

## 💬 Summary
- What is DNS 
- Domain Hierarchy
- Record Types
- Making a Request

-----

### Task 1 - What is DNS?

`DNS` = Domain Name System

DNS provides a simple way for us to communicate with devices on the internet without needing to remember complex IP addresses. Much like how a house has a unique address for sending mail directly to it, every computer on the internet has its own unique address. This is called an `IP address`.

An IP address is made up of four octets ranging from `0-255`:
```
104.26.10.229
```
DNS sets a name to the IP address, so instead of needing to remember 8.8.8.8, you can remember `google.com` instead.

-----

### Task 2 - Domain Hierarchy

```
Second-Level Domain      Top-Level Domain      Root Domain
    [Harvard] - - - - - - - -[.edu]\
                                    \
     [Google] - - - - - - - -[.com]--\ 
                                      - - - - - - ["."]
      [NASA] - - - - - - - - [.gov]--/
                                    /
      [Army] - - - - - - - - [.mil]/
```
#### TLD

`TLD` = Top-Level Domain

The TLD is the `.com` part of a site. For example, `Tryhackme.com`.  

There are two types of TLD:
- gTLD = Generic Top Level
- ccTLD = Country Code Top Level

Historically, gTLD was meant to tell the user the domain name’s purpose; for example, `.com` would be for commercial, `.org` for organisations, `.edu` for education, and `.gov` for government.

Because there is such a demand, there are now over 2000 TLDs [you can check out here](https://data.iana.org/TLD/tlds-alpha-by-domain.txt).

#### Second-level Domain

In `Tryhackme.com` the `Tryhackme` part is what is known as the second-level domain. the second-level domain is limited to 63 characters in length + the TLD. You can use a-z, 0-9, and hyphens (cannot start or end with hyphens).

#### Subdomain

A subdomain sits on the left-hand side of the second-level domain using a period to separate the two. For example, in `admin.tryhackme.com` the `admin` is a subdomain. A subdomain has the same restrictions in length as a second-level domain. You can also have as many subdomains as you wish, as long as the total length of the domain is less than 253 characters.

-----

### Task 3 - DNS Record Types

DNS isn't just for websites. Multiple types of DNS records exist.

- A Record: These records resolve to IPv4.
- AAAA Record: These records resolve to IPv6.
- CNAME Record: Resolves to another domain name.
- MX Record: Resolves to the address of the server that handles the email for the domain you are querying.
- TXT Record: free text fields where any text-based data can be stored.

-----

### Making a DNS request

1. When you request a domain name, your computer checks if it's in its local cache to see if you have previously searched for the address. If not, a request is made to your Recursive DNS Server.

2. A recursive DNS server is usually provided by your Internet Service Provider (ISP). This server also has a cache of recently looked-up domain names. If the address is found locally, then it is sent back to your computer. Otherwise, a journey begins to find the correct answer, starting with the internet's root DNS servers.

3. The root servers act as the DNS backbone of the internet. Their job is to redirect you to the correct Top Level domain server, depending on your request.

4. The TLD server holds records for where to find the authoritative server to answer the DNS request.

5. An authoritative DNS server is responsible for storing the DNS records. This is where any changes to your domain would be made. The address is then sent all the way back through all the servers with a TTL (Time to live) factor. This means you will need to repeat the process once the timer has run out.

-----

### Task 5 - Practice

Use the website to build requests to make DNS queries.


-----

## Questions and Answers

### Task 1

**q1.** What does DNS stand for?

Answer = Domain Name System

-----

### Task 2

**q1.** What is the maximum length of a subdomain?

Answer = 63


**q2.** Which of the following characters cannot be used in a subdomain ( 3 b _ - )?

Answer = _


**q3.** What is the maximum length of a domain name?

Answer = 253


**q4.** What type of TLD is .co.uk?

Answer = ccTLD

-----

### Task 3

**q1.** What type of record would be used to advise where to send email?

Answer = MX


**q2.** What type of record handles IPv6 addresses?

Answer = AAAA


-----

### Task 4

**q1.** What field specifies how long a DNS record should be cached for?

Answer = TTL


**q2.** What type of DNS Server is usually provided by your ISP?

Answer = recursive


**q3.** What type of server holds all the records for a domain?

Answer = authoritative


-----

### Task 5

**q1.** What is the CNAME of shop.website.thm?

Answer = shops.myshopify.com


**q2.** What is the value of the TXT record of website.thm?

Answer = THM{7012BBA60997F35A9516C2E16D2944FF}


**q3.** What is the numerical priority value for the MX record?

Answer = 30


**q4.** What is the IP address for the A record of www.website.thm?

Answer = 10.10.10.10


-----
