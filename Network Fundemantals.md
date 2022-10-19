## What is Networking?
- Networks are simply things connected. 
- **WWW:** World Wide Web 
- _Internet made up of many small networks all joined together. These small networks called as **Public Networks**_
- Network can be one of two types such as _private network_ and _public network_

##### Identifying Devices on a Network
- IP Address: can be change like our name.
- A Media Access Control Adress (MAC): can not change like our fingerprint.
###### IP Adresses 
- Short for Internet Protocol 
- Identifying a host on a network for a period of time, where that IP address can then be associated with another device without the IP address changing. 
- IP addresses can change from device to device but cannot be active simultaneously more than once within the same network.
- Public IP addresses are givrn by your _Internet Service Provider_ 
- IPv4, which uses a numbering system of 2^32 IP addresses (4.29 billion) 
- IPv6 is a new iteration of the Internet Protocol addressing scheme to help tackle this issue.
- - Supports up to 2^128 of IP addresses (340 trillion-plus)
- - More efficient due to new methodologies

- Octet: each sectionof an IP address
- Octet's range is between 0-255
![image](https://user-images.githubusercontent.com/113854816/196631362-aabd538b-6f11-49dd-98a7-0d8641f27827.png)

###### MAC Addresses
- **Twelve character hexadecimal number** split into two's and seperated by a :.
- Devices on a network will all have a physical network interface, which is a microchip board found on the device's motherboard. This network interface is assigned a unique address at the factory it was built at, called a MAC (Media Access Control ) address. 
- ![image](https://user-images.githubusercontent.com/113854816/196632310-620af932-4456-4e7d-bd1a-18811596faf4.png)

-**_Spoofing:_** stoling and usin another computer's MAC address and using the identity to escape from firewall rules.

###### Ping (ICMP) 
- Internnet Control Message Protocol (ICMP) used within ping to determine the performance of a connection between devices. 
- The time taken for ICMP packets travelling between devices is measured by ping, such as in the screenshot below. 

## Local Area Network (LAN) Topologies
- "topology", we are actually referring to the design or look of the network at hand.

###### Star Topology
- devices are individually connected via a central networking device such as a switch or hub. 
- Any information sent to a device in this topology is sent via the central device to which it connects.
- cabling & the purchase of dedicated networking equipment is required for this topology, it is more expensive than any of the other topologies. 
![image](https://user-images.githubusercontent.com/113854816/196667665-60b9e249-e9a1-426e-a9ac-58503e8fc6fa.png)

###### Bus Topology
- connection relies upon a single connection which is known as a backbone cable. 
-  all data destined for each device travels along the same cable, it is very quickly prone to becoming slow and bottlenecked if devices within the topology are simultaneously requesting data.
-  bus topologies are one of the easier and more cost-efficient topologies
-   little redundancy in place in case of failures.
![image](https://user-images.githubusercontent.com/113854816/196667936-a84b6bde-b0ca-4433-ac4e-c5b241026bf2.png)

###### Ring Topology
- Devices such as computers are connected directly to each other to form a loop, meaning that there is little cabling required and less dependence on dedicated hardware such as within a star topology. 
-  sending data across the loop until it reaches the destined device, using other devices along the loop to forward the data. 
-  Because there is only one direction for data to travel across this topology, it is fairly easy to troubleshoot any faults that arise.
![image](https://user-images.githubusercontent.com/113854816/196668192-a6f3f9f7-8feb-4d74-9c94-4a599433c92f.png)

###### What is a Switch?
-  dedicated devices within a network that are designed to aggregate multiple other devices such as computers, printers, or any other networking-capable device using ethernet. 
-  These various devices plug into a switch's port. Switches can connect a large number of devices by having ports of 4, 8, 16, 24, 32, and 64 for devices to plug into.
-  Both Switches and Routers can be connected to one another. The ability to do this increases the redundancy (the reliability) of a network by adding multiple paths for data to take. If one path goes down, another can be used. 
![image](https://user-images.githubusercontent.com/113854816/196668504-7e53305f-d627-4cd3-881b-b03817513d4b.png)

###### What is Router?
- Router's job to connect networks and pass data between them. 
- Routing is the label given to the process of data travelling across networks. Routing involves creating a path between networks so that this data can be successfully delivered.

## Subnetting 
- Splitting up a network into smaller, miniature networks within itself. Subnetting is you deciding who gets what slice & reserving such a slice of this metaphorical cake.
- Network administrators use subnetting to categorise and assign specific parts of a network to reflect this.
- subnet mask: 32 bytes

![image](https://user-images.githubusercontent.com/113854816/196676911-595fe407-3c6f-49f2-8209-cf65cd2afa64.png)

## The ARP Protocol (Adress Resolution Protocol)
- Responsible for allowing devices to identify themselves on a network 
- ARP helps the device connect with MAC adress and IP adress on the network. 

###### How it is work?
- **_cache:_** spesific books to store information on 
- Cache stores _identifiers_ for ARP
- In order to map two identifiers (IP and MAC adress) two message sent:
1. ARP Request 
- message broadcasted to every other device found on a network by the device
-  If the device does have the requested IP address, an ARP reply is returned to the initial device to acknowledge this. The initial device will now remember this and store it within its cache (an ARP entry). 
2. ARP Reply
- MAC address used for physical identifier 
- IP adress used for logical identifier

## DHCP Dynamic Host Control Protocol 
- IP addresses can be assigned automatically by using DHCP server
- if device connects to a network and assigned to IP, it sends out a request (DHCP Discover) to see if any DHCP servers are on the network.
- **DHCP Discover:** search whether any conneected IP is there or not 
- **DHCP Offer:** DHCP server returns wwith an IP address the device could use
- **DHCP Request:** The device then sends a reply confirming it wants the offered IP Address 
- **DHCP ACK:** acknowledgement about the completion status

## OSI MODEL (Open Systems Interconnection Model)
- Framework explains the networked devices will send, receive and interpret data.
- **_ENCAPSULATION_**: key word for when pieces of informatiion get added to data
- 
###### LAYER 7: APPLICATION
- Applications provide Graphical User Interface _GUI_ for users interact with data sent or received. 
- Other protocols such as DNS (Domain Name System) which is how websiite addresses are translated into IP addresses.

###### LAYER 6: PRESENTATION
- Layer acts as a translator for daa to and form the layer 7. 
- The receiving computer will also understand data sent to a computer in one format destined for in another format. For example, when you send an email, the other user may have another email client to you, but the contents of the email will still need to display the same.
- Security features such as data encryption (like HTTPS when visiting a secure site) occur at this layer.

###### LAYER 5: SESSION 
- Once data come from layer 6 as translated, layer 5 will begin to create a connection to the other computer that the data destined for. When a connection is established, a session is created. Whilst this connection is active, so is the session.
- The session layer (layer 5) synchronises the two computers to ensure that they are on the same page before data is sent and received. 
- Data divided to small sections end sen that way. By this method, if the connection lost, only little chunks that weren't sent yet will be sent again
- What is worthy of noting is that sessions are unique — meaning that data cannot travel over different sessions, but in fact, only across each session instead.
- packets: small chunks of data
- session: connection established
