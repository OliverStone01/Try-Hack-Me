# 🚪 Room: Packets & Frames

## 🎯 Objectives
- Understand how data is divided into smaller pieces and transmitted across a network to another device.

## 🛠️ Tools Used
-

## 💬 Summary
- What are packets and frames
- TCP/IP
- Three-way handshake
- Closing a TCP connection
- UDP/IP
- Ports 101
-----

## Notes

### Task 1 - What are packets and frames

Packets and frames are small pieces of data that, when formed together, make a larger piece of information or message.

They are two different things in the OSI model.

A `frame` is at the `layer two - data link`. This means there is no IP address.

You can think of this as putting an envelope in an evelope and sending it away. The first envelope is the packet that you mail, but once opened, the envelope inside contains the data. This is known as the frame.

This process is called `encapsulation`.

When talking about IP addresses, we are talking about packets. When the encapsulating information is stripped away, we are talking about the frame itself.

Packets are an efficient way of communicating data across network devices. Because the data is exchanged in small pieces, there is less chance of bottlenecking occurring across a network when a large message is being sent.

For example, when loading an image from a website, this image is sent as small pieces and reconstructed on your computer.

Packets have different structures. Networking is full of standards and protocols that act as a set of rules for how the packet is handled on a device. With billions of devices on the internet, things can quickly break down if there is no standardisation.

Let's continue with the Internet Internet Protocol. A packet using this protocol will have a set of headers that contain additional pieces of information to the data that is being sent across the network.

Here are some of the notable headers:  
**Time to live**: Sets an expiry timer for the packet to not clog up your network if it never manages to reach a host or escape!

**Checksum**: Provides integrity checking for protocols such as TCP/IP. If any data is changed, this value will be different and therefore corrupt.

**Source address**: The IP address of the device from which the packet is being sent so that the data knows where to return to.

**Destination Address**: The device's IP address to which packet is being sent so that data knows where to travel next.

-----

### Task 2 - TCP/IP (The three-way handshake)

`TCP` = Transmission Control Protocol.

TCP is another rule used in networking.

This protocol is very similar to the OSI model. The TCP/IP protocol consists of four layers and is arguably a summarised version of the OSI model. These layers are:  
- Application
- Transport
- Internet
- Network interface

Similarly to how the OSI model works, information is added to each layer of the TCP model as the piece of data (packet) traverses it. This process is known as encapsulation, where the reverse of this process is decapsulation.

One defining feature of TCP is that it is `connection-based`, which means that TCP must establish a connection between both devices acting as a server before data is sent. This guarantees that any data sent will be received on the other end. 

This process is known as the Three-way handshake.

Advantages of TCP:
- Guarantees the integrity of data.
- Capable of synchronising two devices to prevent each other from being flooded with data in the wrong order.
- Performs a lot more processes for reliability.

Disadvantages of TCP:
- Requires a reliable connection between the two devices. If one small chunk of data is not received, then the entire chunk of data cannot be used and must be resent.
- A slow connection can bottleneck another device as the connection will be reserved on the other device the whole time.
- Significantly slower than UDP because more computing has to be done.

TCP packets contain various sections of information known as headers that are added during encapsulation:
**Source Port**: The port opened by the sender to send the TCP packet from. This value is chosen randomly between 0 and 65535 that are not already in use.

**Destination Port**: The port number on which an application or service is running on the remote host (receiving data).

**Source IP**: The IP address of the device that is sending the packet.

**Destination IP**: The IP address of the device receiving the packet.

**Sequence Number**: When a connection occurs, the first piece of data transmitted is given a random number.

**Acknowledgement Number**: After a piece of data has been given a sequence number, the number for the next piece of data will have the sequence number +1.

**Checksum**: This value is what gives TCP integrity. A mathematical calculation is made where the output is remembered. When the receiving device performs the mathematical calculation, if the output is different, the data must be corrupt.

**Data**: This header is where the data (bytes of a file) are being stored during the transmission.

**Flag**: Determines how the packet should be handled by either device during the handshake. 

The three-way handshake. The term given to the process used to establish a connection between two devices.

**Step 1 - SYN:**
This is the initial packet sent by a client. This packet initiates a connection and synchronises the two devices together.

**Step 2 = SYN/ACK:**
This packet is sent by the receiving device (server) to acknowledge the synchronisation attempt from the client.

**Step 3 = ACK:**
This packet can be used by either the client or the server to acknowledge that packets have been successfully received.

**Step 4 = DATA:**
Data (bytes of files) is sent via the "DATA" message.

**Step 5 = FIN:**
This packet closes the connection after it has completed.

**RST:**
This packet abruptly ends all connections. This can indicate there was a problem during the process.

```
Alice             Bob
  |    -> SYN ->   |
  |                |
  |  <- SYN/ACK <- |
  |                |
  |    -> ACK ->   |

```
Any data sent is given a random number sequence. The data is then reconstructed using this number sequence and incremented by one. Both devices must agree on the same number sequence so the data can be sent in the correct order. These are the three steps taken for the devices to agree on the order:

1. SYN - Client:  
Here's my initial sequence number (ISN) to **SYN**chronise with (0).

2. SYN/ACK - Server:  
Here's my initial sequence number (ISN) to **SYN**chronise with (5,000), and I **ACK**nowledge your initial number sequence (0).

3. ACK - Client:  
I **ACK**nowledge your initial sequence number (ISN) of (5,000). Here is some data that is my ISN+1 (0+1).
```
Device  |  Initial Number Sequence (ISN)  |  Final Number Sequence
- - - - | - - - - - - - - - - - - - - - - | - - - - - - - - - - - -
Client  |  0                              |  0 + 1 = 1
Client  |  1                              |  1 + 1 = 2
Client  |  2                              |  2 + 1 = 3
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
```
### TCP Closing a connection:
Here is the process behind TCP closing a connection. First, TCP will close a connection once a device has successfully received all of the data.

It is best practice to close a `TCP` connection as soon as possible.

To initiate the closure of a `TCP` connection, the device will send a `FIN` packet to the other device. The other device will also have to acknowledge this packet with `TCP`.
```
Alice          Bob
  |  -> FIN ->  |
  |             |
  |  <- ACK <-  |
  |  <- FIN <-  |
  |             |
  |  -> ACK ->  |

```
Alice sends the `FIN` packet to Bob. Bob then `ACK`knowledges the packet and sends `FIN` back to Alice. Alice then sends Bob an `ACK`knowledge packet to complete the closure.

-----

### Task 3 - Practical - handshake

Help Alice and Bob communicate by reassembling the `TCP` handshake.

-----

### Task 4 - UDP/IP

`UDP` = User Datagram Protocol. This is another protocol that is used to communicate data between devices.

`UDP` is a stateless protocol that doesn't require a constant connection between two devices for data to be sent.

`UDP` is used in situations where applications can tolerate data loss, such as video streaming or voice chat.

**Advantage of UDP**:
- UDP is much faster than TCP.
- UDP leaves the application to decide if there is any control over how quickly packets are sent.
- UDP does not have a continuous connection to a device.

**Disadvantages of UDP**:
- UDP doesn't care if the data is received or not.
- It is flexible for software developers.
- Unstable connections result in terrible experiences for the user.

No setup is required to connect between two devices. There are no safeguards such as those offered by TCP, such as data integrity.

`UPD` packets are much simpler than `TCP` packets and have fewer headers. However, both protocols share some standard headers.
```
Header      |  Description
- - - - - - | - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Time to     |  Sets an expiry timer for the packet, so it doesn't
Live (TTL)  |  clog up your network if it never reaches the host.
- - - - - - | - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Source      |  The IP address of the device that the packet is being
Address     |  sent from, so that the data knows where to return to.
- - - - - - | - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Destination |  The device's IP address the packet is being sent to.
Address     |
- - - - - - | - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Source      |  The port that is opened by the sender to send the UDP
Port        |  packet from. This value is randomly chosen (0-65535).
- - - - - - | - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Destination |  The port that an application or service is running on
Port        |  the remote host.
- - - - - - | - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Data        |  The header where the data is stored
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
```  
Here is the process of a connection via `UDP`:
```
Alice              Bob
  |  <- Request <-  |
  |                 |
  |  -> Response -> |
  |  -> Response -> |
  |  -> Response -> |

```
-----

### Task 5 - Ports 101 (practical)

Ports are an essential point at which data can be exchanged. If you think of a boat dock, each boat needs to line up with its compatible port before it can dock. For example, a cruise ship can't dock at a port made for a fishing boat.

Network devices use ports to enforce rules when communicating with one another. Ports are numerical values between `0` and `65535`.

Because of the large range of ports, it's important that we track which application goes where. Thankfully, there is a standard that tells each application which port it can use. For example, web browser data is sent over port `80`. 

A few other protocols have been allocated a standard rule. Any port that is within `0` and `1024` is known as a `common port`.

```
Protocol       |  Port      |  Description
               |  Number    |
- - - - - - - -|- - - - - - - - - - - - - - - - - - - - - - - - - - -
File Trasfer   |            | 
Protocol (FTP) |     21     |  Used by file-sharing applications.
- - - - - - - -| - - - - - -| - - - - - - - - - - - - - - - - - - - -
Secure Shell   |            |  Used to securely login to systems via
(SSH)          |     22     |  text-based interfaces.
- - - - - - - -| - - - - - -| - - - - - - - - - - - - - - - - - - - -
HyperText      |            |  Powers the world wide web (WWW). Your
Transfer       |     80     |  browser uses this to download text,
Protocol (HTTP)|            |  images, and videos of web pages.
- - - - - - - -|- - - - - - | - - - - - - - - - - - - - - - - - - - -
HyperText      |            |  
Transfer       |            |  Protocol does the exact same as the
Protocol Secure|     443    |  above, however, securly using encryption
(HTTPS)        |            |
- - - - - - - -| - - - - - -| - - - - - - - - - - - - - - - - - - - -
Server Message |            |  Similar to FTP. However, SMB allows you
Block (SMB)    |     445    |  to share devices like printers and files.
- - - - - - - -| - - - - - -| - - - - - - - - - - - - - - - - - - - -
Remote Desktop |            |  Secure means of logging in to a system
Protocol (RDP) |    3389    |  with a visual desktop interface.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
```
[Here are the rest of the ports](http://www.vmaxx.net/techinfo/ports.htm)

These protocols only follow the standards. You can administer applications that interact with these protocols on a different port. For example, a web server running on port 8080 instead of 80. However, you do have to provide a colon(:) with the port number.

-----

## Questions and Answers

### Task 1

q1. What is the name for a piece of data when it does have IP addressing information?

Answer = Packet

q2. What is the name for a piece of data when it does not have IP addressing information?

Answer = Frame

-----

### Task 2

q1. What is the header in a TCP packet that ensures the integrity of data?

Answer = checksum

q2. Provide the order of a normal Three-way handshake (with each step separated by a comma)

Answer = SYN,SYN/ACK,ACK

-----

### Task 3

q1. What is the value of the flag given at the end of the conversation?

Answer = THM{TCP_CHATTER}

-----

### Task 4

q1. What does the term "UDP" stand for?

Answer = User Datagram Protocol

q2. What type of connection is "UDP"?

Answer = stateless

q3. What protocol would you use to transfer a file?

Answer = TCP

q4. What protocol would you use to have a video call?

Answer = UDP

-----

### Task 5

q1. What is the flag received from the challenge?

Answer = THM{YOU_CONNECTED_TO_A_PORT}

-----














