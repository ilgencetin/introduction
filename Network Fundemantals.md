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
-  Switches can facilitate many devices (from 3 to 63) using Ethernet cables.
-  These various devices plug into a switch's port. Switches can connect a large number of devices by having ports of 4, 8, 16, 24, 32, and 64 for devices to plug into.
-  Both Switches and Routers can be connected to one another. The ability to do this increases the redundancy (the reliability) of a network by adding multiple paths for data to take. If one path goes down, another can be used. 
![image](https://user-images.githubusercontent.com/113854816/196668504-7e53305f-d627-4cd3-881b-b03817513d4b.png)

- Switches can operate at both layer 2 and layer 3 of the OSI model. However, these are exclusive in the sense that Layer 2 switches cannot operate at layer 3.
- These switches are more sophisticated than layer 2, as they can perform some of the responsibilities of a router. Namely, these switches will send frames to devices (as layer 2 does) and route packets to other devices using the IP protocol. 

![image](https://user-images.githubusercontent.com/113854816/196898268-4f840a88-f17b-423a-aef6-894e1b1ff770.png)


###### VLAN (Virtual Local Area Network) 
- Allows specific devices within a network to be virtually split up. They can benefit from things such as an internet connection but treated as seperately. 

###### What is Router?
- Router's job to connect networks and pass data between them. 
- Routing is the label given to the process of data travelling across networks. Routing involves creating a path between networks so that this data can be successfully delivered.
- Routers operate at Layer 3 of the OSI model. 
- They often feature an interactive interface (such as a website or a console) that allows an administrator to configure various rules such as port forwarding or firewalling.

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
- Layer acts as a translator for data to and form the layer 7. 
- The receiving computer will also understand data sent to a computer in one format destined for in another format. For example, when you send an email, the other user may have another email client to you, but the contents of the email will still need to display the same.
- Security features such as data encryption (like HTTPS when visiting a secure site) occur at this layer.

###### LAYER 5: SESSION 
- Once data come from layer 6 as translated, layer 5 will begin to create a connection to the other computer that the data destined for. When a connection is established, a session is created. Whilst this connection is active, so is the session.
- The session layer (layer 5) synchronises the two computers to ensure that they are on the same page before data is sent and received. 
- Data divided to small sections end sen that way. By this method, if the connection lost, only little chunks that weren't sent yet will be sent again
- What is worthy of noting is that sessions are unique — meaning that data cannot travel over different sessions, but in fact, only across each session instead.
- packets: small chunks of data
- session: connection established

###### LAYER 4: TRANSPORT
- Transmitting data across a network and can be a little bit difficult to grasp.
- It has error checking and reliability skills.
- Generally used for sharing, internet browsing or sending an email bc the data chunks must be send completely in these procedures. There is no mean of sending little chunks of data's.
- When data send between devices, two protocols based:
1. TCP (Transmission Control Protocol) 
- Constant connection between the two devices for the amount of time it takes for the data to be sent and received.
![image](https://user-images.githubusercontent.com/113854816/196862302-ef30c261-a56c-4d6a-8363-842a530ddc93.png)
2. UDP (User Datagram Protocol)
- Any data that gets sent via UDP is sent to the computer whether it gets there or not, the connection between devices is not guaranteed, indeed there is no _synchronisation_
- Usefull for small data 
- Used for vide streaming by using pixels
![image](https://user-images.githubusercontent.com/113854816/196862850-257ed1e7-57d5-49af-97af-1d20fd531fa9.png)

###### LAYER 3: NETWORK 
- Where the magic of **routing & re-assembly** of data takes place.
- Firstly, routing simply determines the most optimal path in which these chunks of data should be sent.
- OSPF (Open Shortest Path First)
- RIP (Routing Information Protocol)
- The factors that decide what route is taken is decided by the following:
- What path is the shortest? I.e. has the least amount of devices that the packet needs to travel across.
- What path is the most reliable? I.e. have packets been lost on that path before?
- Which path has the faster physical connection? I.e. is one path using a copper connection (slower) or a fibre (considerably faster)?
- Everything dealt with IP addresses. Routers capable of delivering packets includes in this layer.

###### LAYER 2: DATA LINK
- Focuses on the physical addressing of the transmission. It receives a packet from the network layer (including the IP address for the remote computer) and adds in the physical MAC (Media Access Control) address of the receiving endpoint.
- **NIC Network Interface Card:** every network enabled computer has it. comes with unique MAC address to identify it.
-  data link layer present the data in a format suitable for transmission.

**_IN OSI MODEL, FIREWALLS OPERATE AT LAYER 3 AND LAYER 2_**

###### LAYER 1: PHYSICAL 
- This layer references the physical components of the hardware used in networking
- Devices use electrical signals to transfer data between each other in a binary numbering system (1's and 0's).
- Ethernet cables one of an example 

## PACKETS AND FRAMES   
- Packets: small chunks of data
- Frames: within the data, still a data found
- **Time to Live:** Expiry timer for the packet which can not manage to reach a host 
- **Checksum:** Integrity checking for protocols such as TCP/IP. If any data changes, value will be different and corrupts.
- **Source Address:**  The IP address of the device that the packet is being sent **from** so that data knows where to **return to.**
- **Destination Address:** The device's IP address the packet is being sent to so that data knows where to travel next. 

## TCP/IP 
- TCP Transmission Control Protocol 
- TCP/IP protocol is a summarized version of OSI Model 
- Four layers:
1. Application 
2. Transport 
3. Internet 
4. Network Interface 
- Information is added to each layer as packets. _Encapsulation and decapsulation occurs._
- TCP connection based, connection both a client and a device acting as a server **before** data sent.
- **_Three-way handshake:_** TCP guarantees that any data sent will be received on the other end.
- ENCAPSULATED TCP PACKETS: 
1. **_Source Port:_** This value is the port opened by the sender to send the TCP packet from. This value is chosen randomly (out of the ports from 0-65535 that aren't already in use at the time).
2. **_Destination Port:_** This value is the port number that an application or service is running on the remote host (the one receiving data); for example, a webserver running on port 80. Unlike the source port, this value is not chosen at random.
3. **_Source IP:_** IP address of the sender of the packet
4. **_Destination IP:_** IP address of the receiver of the packet
5. **_Sequence Number:_** When connection occurs, the first piece of data transmitted one number. 
6. **_Acknowledgement Number:_** After a piece of data has been given a sequence number, the number for the next piece of data will have the sequence number + 1.
7. **_Checksum:_** This value is what gives TCP integrity. Mathematical calculation done and correction with the TCP must be checked and if it the value is not true, data must be corrupt.
8. **_Data:_** bytes of a file that is being transmitted
9. **_Flag:_** This header determines how the packet should be handled by either device during the handshake process. Specific flags will determine specific behaviours (like background rules)

**THREE-WAY HANDSHAKE USES SOME MESSAGES TO CONSIST CONNECTION BETWEEN DEVICES:**
1. **_SYN:_** first packet send to the client and _synchronise_ the two devices together 
2. **_SYN/ACK:_** packet is sent by the receiving device (server) to acknowledge the synchronisation attempt from the client.
3. **_ACK:_** packet can be use by client or server to announce that series of packets have been successfully received.
4. **_DATA:_** after connection established, data (such as bytes of a file) is sent vie DATA message.
5. **_FIN:_** clean and properly closing the connection between server and device after interaction completed. 
6. **_RST:_** ends all communication. This is the last resort and indicates there was some _problem during the process._ For example, if the service or application is not working correctly, or the system has faults such as low resources. 
- **FIN** packets sends by receiver and also client for completing the communication between them. 

## UDP/IP 
- **Stateless protocol** which means does not need any _constant connection._ 
- data integrity not a main concern of UDP 
- **DATA HEADERS:**
- **_Time to Live:_** expiry timer 
- **_Source Address:_** The IP address of the device that the packet is being sent **from** so that data knows where to **return to.**
- **_Source Port:_** This value is the port opened by the sender to send the TCP packet from. This value is chosen randomly (out of the ports from 0-65535 that aren't already in use at the time).
- **_Destination Port:_** This value is the port number that an application or service is running on the remote host (the one receiving data); for example, a webserver running on port 80. Unlike the source port, this value is not chosen at random.
- **_Data:_** bytes of a file that is being transmitted
- UDP is a _stateless protocol_ so that, there is no acknowledgement packet sent to receiver or server.
- **Ex: TCP used for sending a file, UDP used for having a video call**

## PORTS 
- Ports are an essential point in which data can be exchanged.
- Ports enforces strict rules when communicating with one another. 
- Ports can be range of 0 to 65535 in computing.
- Regardless the randomity of the ports, there is standart rules for some ports. Some platforms enforced to sent over a strict number of a port. 
- Any port that is within **0 and 1024 (1,024) is known as a common port.
- You can find spesific ports used for spesific tasks in here: http://www.vmaxx.net/techinfo/ports.htm 
![image](https://user-images.githubusercontent.com/113854816/196883573-c5517f0d-16fb-4d75-a967-1acea8911c63.png)
- What is worth noting here is that these protocols only follow the standards. I.e. you can administer applications that interact with these protocols on a different port other than what is the standard (running a web server on 8080 instead of the 80 standard port). Note, however, applications will presume that the standard is being followed, so you will have to provide a colon (:) along with the port number.

## PORT FORWARDING
- We need to port forwarding process for making available the devices work within the different network. 
- Within this network, the server with an IP address of "192.168.1.10" runs a webserver on port 80. Only the two other computers on this network will be able to access it (this is known as an intranet).
- If the admin wants the website accesible to the public using the internet
- Port forwarding opens specific ports (recall how packets work). 
- Port forwarding is configured at the router of a network.
![image](https://user-images.githubusercontent.com/113854816/196885989-1752744d-f22d-45e8-8201-5fe8ced74381.png)

##### FIREWALL 
- Device within a network whether traffic is allowed to enter and exit. 
- Firewall permit or deny traffic based on:
1. Where the traffic is coming from? (has the firewall been told to accept/deny traffic from a specific network?) 
2. Where is the traffic going to? (has the firewall been told to accept/deny traffic destined for a specific network?)
3. What port is the traffic for? (has the firewall been told to accept/deny traffic destined for port 80 only?)
4. What protocol is the traffic using? (has the firewall been told to accept/deny traffic that is UDP, TCP or both?)

**PRIMARY CATEGORIES OF FIREWALLS:**
1. **STATEFUL:** Uses the entire information, not packets of info.
- Determines the behaviour of a device based upon the entire connection.
- Decision making is dynamic. Firewall could allow the first parts of a TCP handshake that would later fail. 
- If a connection from a host is bad, it will block the entire device.
2. **STATELESS:** Uses a static set of rules to determine whether or not individual packets are acceptable or not.
- Some device sending bad packet will not necessarily mean that the entire device is then blocked. 
- These firewalls are only effective as the rules that are defined within them. If a rule is not exactly matched, it is effectively useless.
- However, these firewalls are great when receiving large amounts of traffic from a set of hosts (such as a Distributed Denial-of-Service attack)

##### VPN Basics
- VPN Virtual Private Network 
- **Tunnel:** created a dedicated path between each other over the internet 
- VPN is a technology that allows devices on separate networks over tunnels.
- Only devices within the same network (such as within a business) can directly communicate.
**Advantages of VPN**
- **_Allows networks in different geographical locations to be connected._** 
- **_Privacy_** VPN uses encryption to protect data. This enables understood between the devices it was being sent from and is destined for, meaning the data isn't vulnerable to sniffing.
- **_Anonyminity_**  Your traffic can be viewed by your ISP and other intermediaries and therefore tracked. VPN that logs all of your data/history is essentially the same as not using a VPN in this regard.

**VPN TECHNOLOGIES**
- **_PPP:_** This technology used by _PPTP_ to allow for authentication and provide encryption of data. VPNs work by using a private key and public certificate (similar to SSH).
- Only encrypts & provides the authentication of data 
- This technology is not capable of leaving a network by itself.
- **_PPTP:_** Point to Point Tunneling Protocol 
- technology that allows the data from PPP to travel and leave a network. 
- Easy set up and supported by most devices but weakly encrypted.
- **_IPSec:_** Internet Protocol Security encrypts data using the existing Internet Protocol (IP) framework.
- Hard to set up but strong encryption 
