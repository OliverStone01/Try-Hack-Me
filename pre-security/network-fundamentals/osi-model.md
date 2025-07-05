# 🚪 Room: OSI Model

## 🎯 Objectives
- Understand the fundamental networking framework that determines the stages of data handling across the network

## 🛠️ Tools Used
-

## 💬 Summary
-

-----
## Notes

### Task 1 - What is the OSI Model?

`OSI Model` = Open Systems Interconnection Model.

The OSI Model is a critical model used in networking. It provides a framework dictating how all devices on the network will send, receive, and interpret data.

One of the main benefits of the OSI model is that devices can have diffrent functionalities and designs, yet they can still comunicate with other devices.

The OSI model consists of seven layers, arranged from layer seven to layer one:

<img src="/pre-security/network-fundamentals/assets/osi-model.png" alt="OSI Model" style="width:300px">

At every layer that data travels through, specific process take place, and pieces of information are added to the data. This is called `encapsulation`.

-----

### Task 2 - Layer 1, Physical

This layer refrences the physical components of the hardware used in networking. For example, ethernet cables conneting devices. Devices use electrical signals to transfer data between each other in a binary numberbering system.

-----

### Task 3 - Layer 2, Data link

This layer focuses on the physical addressing of the transmission. it receives a packet from the network layer (including the IP address for the remote computer) and adds in the physical MAC address of the receiving endpoint taken from the NIC.

`NIC` Network Interface card (Where the MAC address is stored).

It's also the job of the data link layer to format the data in a format suitable for transmission.

-----

### Task 4 - Layer 3, Networking

This layer is where the magic of routing and re-assembly of data takes place. Routing simply determines the most optimal path to send data.





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


