# 🚪 Room: Packets & Frames

## 🎯 Objectives
- Understand how data is divided into smaller pieces and transmitted across a network to another device.

## 🛠️ Tools Used
-

## 💬 Summary
- What are packets and frames
- TCP/IP
- Three-way handshake

-----

## Notes

### Task 1 - What are packets and frames

Packets and frames are small peices of data that, when formed together, they make a larger piece of information or message.

They are two diffrent things in the OSI model.

A `frame` is at the `layer two - data link`. This means there is no IP address.

You can think of this as putting an envelope in an evelope and sending it away. The first envelope is the packet that you mail, but once opened, the envelope inside contains the data. This is known as the frame.

This process is called `encapsulation`.

When talking about IP addresses, we are talking about packets. When the encapsulating information is stripped away, we are talking about the frame itself.

Packets are an effcient way of communicating data across network devices. Because the data is exchanged in small pieces, there is less chance of bottlenecking occuring across a network when a large message is being sent.

For example, when loading an image from a website, this image is sent as small pieces and reconstructed on your computer.

Packets have diffrent structures. Networking is full of standards and protocols that act as a set of rules for how the packet is handled on a device. With billions of devices on the internetm things can quickly break down if there is no standardisation.

Let's continue with the internet protocol. A packet using this protocol will have a set of headers that contain additional pieces of information to the data that is being sent across the network.

Here are some of the notable headers:  
**Time to live**: Sets an expiry timer for the packet to not clog up your network if it never manages to reach a host or escape!

**Checksum**: Provides integrity checking for protocols such as TCP/IP. If any data is changed, this value will be diffrent and therefore corrupt.

**Source address**: The IP address of the device that the packet is being sent from so that the data knows where to return to.

**Destination Address**: The device's IP address the packet is being sent to so that data knows where to travel next.

-----

### Task 2 - TCP/IP (The three-way handshake)

`TCP` = Transmission Control Protocol.

TCP is another rule used in networking.

This protocol is very similar to the OSI model. TCP/IP protocol concists of four layers and is arguably a summarised version of the OSI model. These layer are:
- Application
- Transport
- Internet
- Network interface

Similarly to how the OSI model works, information is added to each layer of the TCP model as the piece of data (packet) traverses it. This process is known as encapsulation where the reverse of this process is decapsulation.

One defining feature of TCP is that it is `connection-based`, which means that TCP must establish a connection between both device acting as a server before data is sent. This guarantees that any data sent will be received on the other end. 

This process is names the Three-way handshake.

Advantages of TCP:
- Guarentees the integrity of data.
- Capable of synchronising two devices to prevent each other from being flooded with data in the wrong order.
- Performs a lot more processes for reliability.

Disadavantages of TCP:
- Requires a reliable connection between the two devices. If one small chunk of data is not recieved, then the entire chunk of data cannot be used and must be re-sent.
- A slow connection can bottleneck another device as the connection will be reserved on the other device the whole time.
- Significantly slower than UDP because more computing has to be done.

TCP packets contain various sections of information known as headers that are added from encapsulation:
**Source Port**: The port opened by the sender to send the TCP packet from. This value is chosen randomly between 0-65535 that are not already in use.

**Destination Port**: The port number that an application or service is running on the remote host (receiving data).

**Source IP**: The IP address of the device that is sending the packet.

**Destination IP**: The IP address of the device receiving the packet.

**Sequence Number**: When a connection occurs, the first piece of data transmitted is given a random number.

**Acknowledgement Number**: After a piece of data has been given a sequence number, the number for the nect piece of data will have the squence number +1.

**Checksum**: This value is what gives TCP integirty. A mthmatical calculation is made where the output is remembered. When the receiving device performs the mathmatical calculation, if the output is diffrent, the data must be corrupt.

**Data**: This header is where the data (bytes of a file) are being stored during the transmission.

**Flag**: Determines how the packet should be handled by either device during the handshake. 

The three way handshake. The term given to the process used to establish a connection between two devices.

**Step 1 - SYN:**:
This is the initial packet sent by a client. This packet initiates a connection and synchronises the two devices together.

**Step 2 = SYN/ACK:**
This packet is sent by the recieving device (server) to acknowledge the synchronisation attempt from the client.



-----

## Questions and Answers

### Task 1

q1. What is the name for a piece of data when it does have IP addressing information?

Answer = Packet

q2. What is the name for a piece of data when it does not have IP addressing information?

Answer = Frame

-----

### Task 2


