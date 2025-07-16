# 🚪 Room: Extending Your Network

## 🎯 Objectives
- Learn about some of the technologies used to extend networks out onto the Internet and the motivations for doing this.

## 🛠️ Tools Used
-

## 💬 Summary
- Port forwarding
- Firewalls
- VPN basics
- LAN Network Devices
- Routers
- Switches

-----

### Task 1 - Introduction to Port Forwarding

Port forwarding is an essential component in connecting applications and services to the internet. Without port forwarding, applications and services like web servers would only be available to devices within the same direct network.

Port forwarding is configured on the router of a network.

-----

### Task 2 - Firewalls 101

A `firewall` is a device within a network responsible for determining what traffic is allowed to enter and exit. A `firewall` can be thought of as a border security of a network.

An administrator can configure a firewall to permit or deny traffic from entering or exiting a network based on:
- Where the traffic is coming from.
- Where the traffic is going to.
- What port the traffic is for.
- What protocol the traffic is using.

Firewalls perform packet inspection to determine the answers to these questions.

Firewalls come in all shapes and sizes. From dedicated hardware that can handle large amounts of data to residential routers or software such as Snort, firewalls can be categorised into two to five categories.

Let's look at the two primary categories.
```
Firewall |
Category |  Description
- - - - -| - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         |  Uses the entire information from a connection rather than
         |  inspecting an individual packet, this firewall determines
         |  the behaviour of a device.
         |
Stateful |  This firewall type consumes many resources as decision
         |  making is dynamic. For example, it could allow the first
         |  part of a TCP handshake and later fail.
         |
         |  If a connection from a host is bad, it will block the device.
- - - - -| - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
         |  Uses a static set of rules to determine whether or not an
         |  individual packets are accepted or not.
         |
         |  These firewalls are much dumber as they are only as effective
Stateless|  as the rules that are defined.
         |
         |  However these firewalls are great when receiving large
         |  amounts of traffic from a set of hosts (DDOS attack)
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
```
-----

### Task 3 - Practical

Configure the firewall to prevent the malicious packets from reaching the web server.

-----

### Task 4 - VPN Basics

`VPN` = Virtual Private Network

A VPN allows devices on separate networks to communicate securely by creating a dedicated path between each other over the internet (known as a tunnel). Devices connected within this tunnel form their own private network.

**Benefit**:
- Allows networks in different geographical locations to be connected.
- Offers privacy
- Offers anonymity.

Here are some VPN technologies:
```
VPN        |
Technology |  Description
- - - - - -| - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
           |  Used by PPTP to allow for authentication and provide
    PPP    |  encryption of data.
- - - - - -| - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
           |  Point-to-Point Tunnelling Protocol allows the data from
           |  PPP to travel and leave a network. Its easy to set up and
   PPTP    |  is supported by most devices. Weak encryption.
- - - - - -| - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
           |  Internet protocol security encrypts data using the
   IPSec   |  the existing Internet Protocol (IP) framework.
           |  Difficult to set up. strong encryption.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
```
-----

### Task 5 - LAN Networking Devices

#### What is a Router?
A router's job is to connect networks and pass data between the networks. It does this using routing.

Routing is the label given to the process of data travelling across networks. Routers create a path between networks for the data to travel on. Routers operate at `level 3` of the `OSI model`. They often have an interactive interface like a website so that administrators can configure various rules, such as port forwarding and firewalls.

Routers are dedicated devices and do not perform the same function as switches.

Protocols decide which path the data should take across routers. The factors that decide this are:
- What path is the shortest?
- What path is most reliable?
- Which path has the faster medium (e.g. copper or fibre)?

#### What is a Switch?

A switch is a dedicated networking device that allows you to connect to multiple devices. Switches can facilitate many devices (from 3 to 63 per switch) using Ethernet cables.

Switches can operate at both layer 2 and layer 3 of the OSI model. These are exclusive in the sense that layer 2 switches cannot operate at layer 3.

Here is a Layer 2 switch that forwards frames onto the connected devices using their MAC addresses.
```
[Device 1]\
           \
[Device 2]- - - [Layer 2 Switch] - - - [Router]
           /
[Device 3}/
```
Let's now look at layer 3 switches. These are a little more sophisticated than layer 2 as they can perform some of the responsibilities of a router. These switches will send frames to devices and route packets to other devices using the IP protocol.

`VLAN` = Virtual Local Area Network. It allows specific devices within a network to be virtually split up. Doing this means you can have two networks that can have an internet connection but are treated separately from each other. This is commonly seen within a company where the sales team will have a network and the accounting team will have a network.
```
 - - Sales - -
|   [Device]  |
|   [Device]  | \
|   [Device]  |  \
 - - - - - - -    \
                  [Layer 3 Switch] - - - [Router]
 - -Finance- -    /
|   [Device]  |  /
|   [Device]  | /
|   [Device]  |
 - - - - - - -
```
-----

### Task 6 - Practical - Network Simulator

Experiment with the network simulator.

-----

## Questions and Answers

### Task 1

q1. What is the name of the device that is used to configure port forwarding?

Answer = router

-----

### Task 2

q1. What layers of the OSI model do firewalls operate at?

Answer = 3 & 4

q2. What category of firewall inspects the entire connection?

Answer = stateful

q3. What category of firewall inspects individual packets?

Answer = stateless

-----

### Task 3

q1. What is the flag?

Answer = THM{FIREWALLS_RULE}

-----

### Task 4

q1. What VPN technology only encrypts & provides the authentication of data?

Answer = PPP

q2. What VPN technology uses the IP framework?

Answer = IPSec

-----

### Task 5

q1. What is the verb for the action that a router does?

Answer = routing

q2. What are the two different layers of switches?

Answer = Layer 2,Layer 3

-----

### Task 6

q1. What is the flag from the network simulator?

Answer = THM{YOU'VE_GOT_DATA}

q2. How many HANDSHAKE entries are there in the Network Log?

Answer = 5

-----

