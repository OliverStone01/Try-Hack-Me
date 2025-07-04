# 🚪 Room: What is Networking?

## 🎯 Objectives
- Begin learning the fundamentals of computer networking in this bite-sized and interactive module.

## 🛠️ Tools Used
- Ping

## 💬 Summary
-

-----
## Notes

#### Task 1 - What is Networking?

Networks are things connected.

Networks can be found:
- City's public transport system.
- National power grid.
- Postal systems.

A network can be formed with as little as two devices to billions of devices. These devices can be your laptop, phone, cameras, and much more.

Networks are integrated into our everyday life from gathering weather data to sending messages. Networking is an essential concept in cybersecurity.

-----

#### Task 2 - What is the internet?

The internet is one giant network that consists of many small networks.

The first internet was within the `ARPANET` project in the late 1960s. The project was funded by the United States Defence Department. However, it wasn't until 1989 where the internet (WWW) we know now was invented by `Tim Berners-Lee`.

`WWW` = World wide web

The internet started to be used as a repository for storing and sharing information, just like it is today.

The internet is a much larger version of this diagram:

<img src="/pre-security/network-fundamentals/assets/network.png" alt="Network layout" style="width:300px">

These smaller networks that make up the internet are called `Private network`. The networks connecting the private networks together are called `Public networks`.

-----

#### Task 3 - Identifying devices on a network

For devices to communicate and maintain order, devices must be able to identify and be identifiable on a a network.

devices are similar to humans in the sense that we have two ways of being identified:
- Our name
- Our fingerprints

although we can change our name, we are unable to change our fingerprints. In computer's these are known as:
- An IP address (Non-perminent).
- A Media Access Control (MAC) Address. (Similar to a serial number)

**IP Addresses**
`IP address` = Internet Protocol.

An IP address is a way of identifying a host on a network for a period of time. Here is an IP address split up:

<img src="/pre-security/network-fundamentals/assets/ip4-address.png" alt="Example of IPv4" style="width:350px">

An IP address is a set of numbers (8-bits) that are divided into four octest. The value of each octet will summarise to be the IP address of the device on the network. This calculation is a technique known as `IP addressing & subnetting`.

IP addresses can change from device to device but cannot be active simultaneously within the same network.

IP addresses follow a set of standards known as protocols.

A public address is used to identify the device on the internet, while a private address is used to identify the device among other devices.

Two devices on a private network will use their private IP addresses to communicate with each other. However, any data sent to the internet from either device will be identified by the same public IP address. This is because your data is sent to the router in your home for example and your data is transmited from there which has it own public IP address which is given to the device by your `ISP` at a monthly fee.

`ISP` = Internet Service Provider

It was reported by Cisco (industry giant in networking) that it will become increasingly harder to get a public IP address that isnt already in use. This is because of as of 2021, there is estimated to be 50 Billion devices connected to the internet.

**IP address Version Types**

- IPv4 = standard 4 octet IP address. total of 4.29 billion IP addresses.

To combat this increasing issue, a new version of IP address was created called `IPv6`.

- IPv6 = better efficiency, over 340 Trillion-plus addresses.

Here is an image comparing the two IP addresses:

<img src="/pre-security/network-fundamentals/assets/ip-comparison.png" alt="IPv4 vs IPv6" style="width:300px">

**MAC Addresses**

Devices on a network will have a physical network microchip found on the device's motherboard. This network interface is assigned a unique address at the factory where it was built. This is called a `MAC Address`.

`MAC` = Media Access Control

The MAC address is twelve-characters hexadecimal number (base 16) split into two's and seperated by a colon. These colons are known as separators.

- The first 6 characters represent the company that made the network interface.
- The last 6 characters are unique numbers.

<img src="/pre-security/network-fundamentals/assets/mac-address.png" alt="MAC address example" style="width:350px">

MAC addresses can be faked by `spoofing`. Doing this will only break poorly implemented security designs. For example, if a firewall is configured to allow any communication going to and from a MAC address of an administrator. Then all you would need to do is spoof your MAC address to be the same.

Most common public places like these are where this issue is found:
- Coffee Shops
- Cafes
- Hotels

**Practical**

The interactive lab simulates a hotel wifi network where you have to pay for the service. the router is not allowing Bob's packers to the website and placing them in the bin. But Alice's packets are going through fine becuase she has paid for the service. We have to change Bob's MAC address to the same as Alice's to complete the challenge.

-----

#### Task 4 - Ping(ICMP)

Ping is one of the most fundametal network tools avaialable. Ping uses `ICMP` Packets to determine the performance of a connection between devices.

`ICMP` = Internet Control Message Protocol

The measuring is done by sending `ICMP's echo` packet from one device, and listening for the `ICMP's echo` reply from the Target device.

Ping can be performed against devices on a network or on resources like websites. This tool is easy to use and comes pre-installed on operating systems such as linux and windows. The syntax for ping is:
```
ping (IP ADDRESS/WEBSITE URL)
```
Here is an example from the room:

<img src="/pre-security/network-fundamentals/assets/ping.png" alt="Ping example" style="width:300px">

Using the deployable website, I had to ping the IP address `8.8.8.8`.

-----

## Questions and Answers

#### Task 1

What is the key term for devices that are connected together?

Answer = Network

-----

#### Task 2

Who invented the World Wide Web?

Answer = Tim Berners-Lee

-----

#### Task 3

q1. What does the term `IP` stand for?

Answer = Internet Protocol

q2. What is each section of an IP address called?

Answer = Octet

q3. How many sections does an IPv4 address have?

Answer = 4

q4. What does the term `MAC` stand for?

Answer = Media Access Control

q5. Deploy the interactive lab using the "View Site" button and spoof your MAC address to access the site.  What is the flag?

Answer = THM{YOU_GOT_ON_TRYHACKME}

-----

#### Task 4

q1. What protocol does ping use?

Answer = ICMP

q2. What is the syntax to ping 10.10.10.10

Answer = ping 10.10.10.10

q3. What flag did you get when you ping 8.8.8.8?

Answer = THM{I_PINGED_THE_SERVER}

-----

