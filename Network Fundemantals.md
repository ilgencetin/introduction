## What is Networking?
- Networks are simply things connected. 
- **WWW:*** World Wide Web 
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
![image](https://user-images.githubusercontent.com/113854816/196631362-aabd538b-6f11-49dd-98a7-0d8641f27827.png)

###### MAC Addresses
- **Twelve character hexadecimal number** split into two's and seperated by a :.
- Devices on a network will all have a physical network interface, which is a microchip board found on the device's motherboard. This network interface is assigned a unique address at the factory it was built at, called a MAC (Media Access Control ) address. 
- ![image](https://user-images.githubusercontent.com/113854816/196632310-620af932-4456-4e7d-bd1a-18811596faf4.png)

-**_Spoofing:_** stoling and usin another computer's MAC address and using the identity to escape from firewall rules.

###### Pig (ICMP) 
- Internnet Control Message Protocol (ICMP) used within ping to determine the performance of a connection between devices. 
- The time taken for ICMP packets travelling between devices is measured by ping, such as in the screenshot below. 
