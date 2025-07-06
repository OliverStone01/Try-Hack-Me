# 🚪 Room: OSI Model

## 🎯 Objectives
- Understand the fundamental networking framework that determines the stages of data handling across the network

## 💬 Summary
- OSI Model:
  - Layer 1 = Physical
  - Layer 2 = Data link
  - Layer 3 = Network
  - Layer 4 = Transport
  - Layer 5 = Session
  - Layer 6 = Presentation
  - Layer 7 = Application

-----
## Notes

### Task 1 - What is the OSI Model?

`OSI Model` = Open Systems Interconnection Model.

The OSI Model is a critical model used in networking. It provides a framework dictating how all devices on the network will send, receive, and interpret data.

One of the main benefits of the OSI model is that devices can have different functionalities and designs, yet they can still communicate with other devices.

The OSI model consists of seven layers, arranged from layer seven to layer one:

<img src="/pre-security/network-fundamentals/assets/osi-model.png" alt="OSI Model" style="width:300px">

At every layer that data travels through, specific processes take place, and pieces of information are added to the data. This is called `encapsulation`.

-----

### Task 2 - Layer 1, Physical

This layer references the physical components of the hardware used in networking. For example, Ethernet cables connecting devices. Devices use electrical signals to transfer data between each other in a binary numbering system.

-----

### Task 3 - Layer 2, Data link

This layer focuses on the physical addressing of the transmission. It receives a packet from the network layer (including the IP address for the remote computer) and adds in the physical MAC address of the receiving endpoint taken from the NIC.

`NIC` Network Interface Card (where the MAC address is stored).

It's also the job of the data link layer to format the data in a format suitable for transmission.

-----

### Task 4 - Layer 3, Networking

This layer is where the magic of routing and reassembly of data takes place. Routing simply determines the most optimal path to send data.

These protocols include:
`OSPF` = Open Shortest Path First
`RIP` = Routing Information Protocol.

The factors that decide what route is taken are decided by the following:
- What path is the shortest?
- What path is the most reliable?
- What path has the faster physical connection?

At this layer, everything is dealt with by the IP address. The router uses this IP address to deliver packets.

-----

### Task 5 - layer 4 Transport

This layer plays a vital part in transmitting data across a network. When data is sent between devices, it follows one of two different protocols based on several factors:

- `TCP` = Transmission control protocol.
- `UDP` = User Datagram protocol.

TCP is designed to be reliable and have guarantees in mind. This protocol reserves a constant connection between the two devices until the data has been sent and received.

TCP also incorporates error checking. This is how TCP can check that all data chunks were received and reassembled in the same order.

Advantages of TCP:
- Guarantees the accuracy of data.
- Capable of synchronising two devices to prevent each other from being flooded with data.
- Performs a lot more processes for reliability.

Disadvantages of TCP:
- Requires a reliable connection between two devices. If one piece of data is not received, then the entire chunk of data cannot be used.
- Slow connecting can bottleneck the receiving device.
- Significantly slower than UDP.

TCP is used for file sharing, internet browsing, or sending an email. This is because these require data to be accurate and complete.

UDP is not as advanced as TCP. UDP does not offer error checking and reliability. Any data sent via UDP is sent to the receiving device, whether it gets there or not.

Advantages of UDP:
- UDP is much faster than TCP.
- UDP leaves the application layer (user software) to decide if there is any control over how quickly packets are sent.
- UDP does not reserve a continuous connection on a device.

Disadvantages of UDP:
- UDP doesn't care if the data is received.
- Unstable connections result in terrible experiences for the user.

UDP is useful where small pieces of data are being sent, for example, protocols for discovering devices (ARP and DHCP) or larger files such as video streaming where it is okay if some parts of the video are pixelated.

-----

### Task 6 - layer 5 Session

Once data has been correctly translated or formatted from the presentation layer, the session later will begin to create and maintain the connection to the other computer. Once a connection has been made, a session is created and is active until the end of the connection.

The session layer is responsible for closing a connection. A session can contain `checkpoints`, where if data is lost, only the newest data needs to be sent.

Sessions are unique. Meaning data cannot travel over different sessions, but only across each session.

-----

### Task 7 - layer 6 Presentation

Here is where standardisation starts to take place. Because developers are able to create software differently, the data still needs to be handled in the same way, no matter how the software works.

This layer acts as a translator. Security features such as data encryption occur at this layer.

-----

### Task 8 - Layer 7 Application

The Application layer is the layer in which protocols and rules are in place to determine how the user should interact with data sent or received.

Everyday applications such as email clients, browsers, or file service browsing software provide a friendly GUI for users to interact with data sent or received. Other protocols include DNS, which is how website addresses are translated into IP addresses.

`GUI` = Graphical User Interface.
`DNS` = Domain Name System

-----

## Questions and Answers

### Task 1

q1. What does the "OSI" in "OSI Model" stand for?

Answer = Open Systems Interconnection

q2. How many layers (in digits) does the OSI model have?

Answer = 7

q3. What is the key term for when pieces of information get added to data?

Answer = encapsulation

-----

### Task 2

q1. What is the name of this Layer?

Answer = Physical

q2. What is the name of the numbering system that is both 0's and 1's?

Answer = Binary

q3. What is the name of the cables that are used to connect devices?

Answer = Ethernet cables

-----

### Task 3

q1. What is the name of this layer?

Answer = Data link

q2. What is the name of the piece of hardware that all networked devices come with?

Answer = Network Interface Card

-----

### Task 4

q1. What is the name of this layer?

Anwer = Network

q2. Will packets take the most optimal route across a network? (Y/N)

Answer = Y

q3. What does the acronym "OSPF" stand for?

Answer = Open Shortest Path First

q4. What does the acronym "RIP" stand for?

Answer = Routing Information Protocol

q5. What type of addresses are dealt with at this layer?

Answer = IP Addresses

-----

### Task 5

q1. What is the name of this Layer?

Asnwer = Transport

q2. What does TCP stand for?

Answer = Transmission Control Protocol

q3. What does UDP stand for?

Answer = User Datagram Protocol

q4. What protocol guarantees the accuracy of data?

Answer = TCP

q5. What protocol doesn't care if data is received or not by the other device?

Answer = UDP

q6. What protocol would an application such as an email client use?

Answer = TCP

q7. What protocol would an application that downloads files use?

Answer = TCP

q8. What protocol would an application that streams video use?

Answer = UDP

-----

### Task 6

q1. What is the name of this layer?

Answer = Session

q2. What is the technical term for when a connection is succesfully established?

Answer = Session

-----

### Task 7

q1. What is the name of this Layer?

Answer = Presentation

q2. What is the main purpose that this Layer acts as?

Answer = Translator

-----

### Task 8

q1. What is the name of this Layer?

Answer = Application

q2. What is the technical term that is given to the name of the software that users interact with?

Answer = Graphical User Interface

-----

### Task 9

q1. Escape the dungeon to retrieve the flag. What is the flag?

Answer = THM{OSI_DUNGEON_ESCAPED}

-----




