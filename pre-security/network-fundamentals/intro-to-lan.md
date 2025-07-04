# 🚪 Room: Intro to LAN

## 🎯 Objectives
- Learn about some of the technologies and designs that power private networks.

## 💬 Summary
- Topologies
- Switches
- Routers
- Subnetting
- ARP
- DHCP

-----

## Notes

### Task 1 - Introducing LAN topologies

`LAN` = Local Area Networks.

`topology` = The design or look of the network at hand.

-----

#### Star Topology

<img>

Devices are individually connected via a central networking devicee such as a switch or a hub. This topology is the most commonly found due to it's reliability and scalability despite the cost.

**Benefits:**  
- Reliablility
- Scalablility

**Disadvantages:**  
- Cost (cabling and dedicated network devices)
- The larger the network, the more maintenance.
- Prone to failure (if the centralised hardware fails, the entire network fails)

-----

#### Bus Topology

<img>

This connection relies upon a single connection known as a `backbone cable`. 

**Benefits:**
- One of the easiest to set up.
- Cost-effcient

**Disadvantages:**
- Becauase all data travels on the same cable, it is quickly prone to bottlenecking (causing the network to slow down)
- Bottlenecking makes it difficult to troubleshoot where the issue is coming from.
- Prone to redundancy (reliability).

-----

#### Ring Topology

<img>

Also known as token topology. Devices are connected directly to each other to form a loop. This uses very little cabling to connect each device. The data is sent from one device around the loop until it reaches the target device. A device will choose to send its data first over passing other data from one device to another. Data is only sent in one direction around the loop.

**Benefits:**
- Low cost.
- Easy to set up.
- East to troubleshoot.
- less prone to bottlenecks.

**Disadvantages:**
- Inefficient to send data through multiple devices.
- If a cable or device breaks, it will stop the entire network.

-----

#### What is a switch?

<img>

Switches are dedicated network devices that are designed to aggregate multiple devices together using ethernet through the switches ports. Switches can be found in larger networks such as businesses and schools.

Switches can connect a large number of devices by having more ports. These devices are seen in sizes of:
- 4
- 8
- 16
- 24
- 32
- 64

Switches are much more efficent than their lesser couterpart (hubs/repeaters). Switches are able to keep track of what devices is connected to what port, that way, when it recives a packet, it knows where to send it, reducing network traffic.

Both switches and routers can be connected to one another. Doing so increases the redundancy (reliablility) becuase there are extra paths involved. Meaning if one path goes down, the packet can be sent via another path.

-----

#### What is a Router?

<img>

Routers connect networks and pass data between them. It does this via routing.

Routing is the name of the process of creating a path between two networks and data travelling across successfully.

Routing is useful when devices are connected by many paths.

-----

#### Practical

Learn about the ways to break each topology and collect the flag at the end.

- Ring topology:  
  Cut the cable to break the connection.
- Bus topology:  
  Send lots of data from one computer to the other overwelming the topology.
- Star topology:  
  Broke the center device with a hammer.

-----

### Task 2 - A primer on subnetting

Subnetting is splitting up a network into smaller networks. For example, in a business, you may want to subnet these diffrent departments:
- Accounting
- Finace
- Human Resources

Subnetting is achieved by spliting up the number of hosts that can fit within our network, represented by a number called a `subnet mask`. Recall, an IP address is made up of four octets. The samme is true for a subnet mask.

Subnets use IP addresses in three diffrent ways:
- Identify the network address:  
  Identifies the start of the network and is to identify a network's existence. For example, a device with the IP address 192.168.1.100 will be on the network 192.168.1.0
- Identify the host address:  
  Identiys a device on the subnet. For example, a device will have the network address of 192.168.1.1
- Identify the default gateway:
  The default gateway address is assigned to device on the network capable of sending information to another network. Any data that needs to go to a device outside of the network will be sent to this device. they can use any host but usually use the first or last address.

On a small network, you are likely to be on only one subnet unless the device count exceeds 254.

Subnetting provides benefits including:
- Effciency
- Security
- Full control

For example, a cafe will have two networks:
1. For employees, cash registers, and other devices for the facility.
2. For the general public to use as a hotspot.

Subnetting allows you to have these seperate networks while having the benefits of one large network.

-----

### Task 3 - ARP

`ARP` = Address Resolution Protocol

ARP is responsible for allowing devices to identify themselves on a network. It allows the device to associate its MAC address with an IP address on the network.

**How does ARP work?**
Each device on the network has a ledger to store information on. This is called a `cache`. In the context of ARP, the cache stores the identifiers of other devices on the network.

In order to map these two identifiers together (IP address and MAC address), ARP sends two messages:
1. ARP Request
2. ARP Reply

The ARP message is broadcated to the network asking "What device has this IP address?". The device that owns that IP address will send an ARP Reply with it's MAC address. The requesting device can now remeber this in the cache.

-----

### Task 4 - DHCP

`DHCP` = Dynamic Host Configuration Protocol

IP addresses can be assigned to a device manualy or automatically using a DHCP server. The device will send out a request (DHCP Discover) to if there is a DHCP server on the network. The DHCP server replies back with an IP Address the device could use (DHCP Offer). The device then sends a reply confirming it wants the offered IP Address (DHCP Request), and lastly the DHCP server sends back a reply acknowledging this has been complete called DHCP ACK.

<img>

-----

## Questions and Answers

#### Task 1

q1. What does LAN stand for?

Answer = Local Area Network

q2. What is the verb given to the job that router perform?

Answer = Routing

q3. What device is used to centrally connect multiple devices on the local network and transmit data to the correct location?

Answer = Switch

q4. What topology is cost efficient to set up?

Answer = Bus topology

q5. What topology is expensive to set up and maintain?

Answer = Star topology

q6. Complete the interactive lab attached to this task. What is the flag given at the end?

Answer = THM{TOPOLOGY_FLAWS}

-----

#### Task 2 

q1. What is the technical term for dividing a network up into smaller pieces?

Answer = Subnetting

q2. How many bits are in a subnet mask?

Answer = 32

q3. What is the range of a section (octet) of a subnet mask?

Answer = 0-255

q4. What address is used to identify the start of a network?

Answer = Network address

q5. What address is used to identify devices within a network?

Answer = Host Address

q6. What is the name used to identify the device responsible for sending data to another network?

Answer = Default gateway

-----

#### Task 3 

q1. What does ARP stand for?

Answer = Address Resolution Protocol

q2. What category of ARP Packet asks a device whether or not it has a specific IP address?

Answer = Request

q3. What address is used as a physical identifier for a device on a network?

Answer = MAC address

q4. What address is used as a logical identifier for a device on a network?

Answer = IP Address

-----

#### Task 4

q1. What type of DHCP packet is used by a device to retrieve an IP address?

Answer = DHCP Discover

q2. What type of DHCP packet does a device send once it has been offered an IP address by the DHCP server?

Answer = DHCP Request

q3. Finally, what is the last DHCP packet that is sent to a device from a DHCP server?

Answer = DHCP ACK
