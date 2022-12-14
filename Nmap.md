## MAP 
- When we tried to attack somewhere, firstly we need to create a map to see our _landscape._ 
- _Landscape_ generally includes port scanning
- Network connections are made between two ports - an open port listening on the server and a randomly selected port on your own computer.
- Every computer has total of **65535 available ports.** Many of them used as default ports. 
- If we do not know which of these ports a server has open, then we do not have a hope of successfully attacking the target; thus, it is crucial that we begin any attack with a port scan.
- **0-1024 ports** are well-known and specified ports.
## NMAP
- Perform many different kinds of port scan 
- Nmap will connect to each port of the target in turn. Depending on the port responds, it an be determined as being open, closed or filtered (by a firewall)
- Once we know which ports are open, we can then look at enumerating which services are running on each port – either manually, or more commonly using nmap.

- NMAP both used for Windows and Linux

##### PORT SCANNING
- **-sT** TCP Connect Scans
- _Three Way Handshake:
- if Nmap sends a TCP request with the SYN flag set to a closed port, the target server will respond with a TCP packet with the RST (Reset) flag set. By this response, Nmap can establish that the port is closed.
- If, however, the request is sent to an open port, the target will respond with a TCP packet with the SYN/ACK flags set. Nmap then marks this port as being open (and completes the handshake by sending back a TCP packet with ACK set).
- Many firewalls are configured to simply drop incoming packets. Nmap sends a TCP SYN request, and receives nothing back. This indicates that the port is being protected by a firewall and thus the port is considered to be filtered.
- RFC 793 defined appropiate behaviour of the TCP protocol
![image](https://user-images.githubusercontent.com/113854816/200820866-1c9891ec-1576-499a-aa94-43f0d8f4d54e.png)

- **-sS** SYN "Half-open" Scans
- Similar to TCP scans TCP port-range. Sometimes referreed as "Half-open" scans or "Stealth" scans.
- Where TCP scans perform a full three-way handshake with the target, SYN scans sends back a RST TCP packet after receiving a SYN/ACK from the server
- bypass older Intrusion Detection systems as they are looking out for a full three way handshake.
- SYN scans are often not logged by applications listening on open ports, as standard practice is to log a connection once it's been fully established. 
- Without having to bother about completing (and disconnecting from) a three-way handshake for every port, SYN scans are significantly faster than a standard TCP Connect scan.
- They require sudo permissions[1] in order to work correctly in Linux. This is because SYN scans require the ability to create raw packets (as opposed to the full TCP handshake), which is a privilege only the root user has by default.
- Unstable services are sometimes brought down by SYN scans, which could prove problematic if a client has provided a production environment for the test.
- If a port is closed then the server responds with a RST TCP packet. If the port is filtered by a firewall then the TCP SYN packet is either dropped, or spoofed with a TCP reset.
- 
![image](https://user-images.githubusercontent.com/113854816/200820957-15477242-ec01-47ee-88ad-1053f3146e25.png)

-  **-sU** UDP Scans 
-  Unlike TCP, UDP connections are stateless
-  When a packet is sent to an open UDP port, there should be no response. When this happens, Nmap refers to the port as being open|filtered. It can be open but it could be firewalled. If it gets a UDP response (which is very unusual), then the port is marked as open. 
-  In general, there is no response,  in which case the request is sent a second time as a double-check. If there is still no response then the port is marked open|filtered and Nmap moves on.
-  When the packet send to _closed_ port, target respond with an ICMP packet containing message that the port unreachable.
-  When we compare with TCP scans, these scans are much more slow so that it's usually good practice to run an Nmap scan with _--top-ports < number >_
-  nmap -sU --top-ports 20 < target > --> will scan the top 20 most commonly used UDP ports
  
- **-sN** TCP Null Scans
- when the TCP request is sent with no flags set at all. As per the RFC, the target host should respond with a RST if the port is closed.
![image](https://user-images.githubusercontent.com/113854816/200827315-7b2a6bf0-b4e3-425b-a936-b2babf88d284.png)

- **-sF** TCP FIN Scans
- work in an almost identical fashion; however, instead of sending a completely empty packet, a request is sent with the FIN flag (usually used to gracefully close an active connection). Once again, Nmap expects a RST if the port is closed.

![image](https://user-images.githubusercontent.com/113854816/200827555-8273200d-1e39-4527-abcd-c5361ade83a7.png)

- **-sX** TCP Xmas Scans 
- send a malformed TCP packet and expects a RST response for closed ports. It's referred to as an xmas scan as the flags that it sets (PSH, URG and FIN) give it the appearance of a blinking christmas tree when viewed as a packet capture in Wireshark.

![image](https://user-images.githubusercontent.com/113854816/200827658-37c26ac4-96f3-4366-9b44-1d9c2bbe8a86.png)

- NULL, FIN and Xmas scans will only ever identify ports as being open|filtered, closed, or filtered. If a port is identified as filtered with one of these scans then it is usually because the target has responded with an ICMP unreachable packet.
- In particular Microsoft Windows (and a lot of Cisco network devices) are known to respond with a RST to any malformed TCP packet -- regardless of whether the port is actually open or not.
- Reason of using these three scan types: **_firewall evasion**_

**PING SWEEP:**  Nmap sends an ICMP packet to each possible IP address for the specified network. When it receives a response, it marks the IP address that responded as being alive. 
- to perform a ping sweep: **-sn**
- The -sn switch tells Nmap not to scan any ports -- forcing it to rely primarily on ICMP echo packets (or ARP requests on a local network, if run with sudo or directly as the root user) to identify targets. In addition to the ICMP echo requests, the -sn switch will also cause nmap to send a TCP SYN packet to port 443 of the target, as well as a TCP ACK (or TCP SYN if not run as root) packet to port 80 of the target.

##### NSE Scripting
- Nmap Scripting Engine (NSE)
- performs in LUA language
- safe:- Won't affect the target
- intrusive: Not safe, likely to affect the target
- vuln:- Scan for vulnerabilities
- exploit: Attempt to exploit a vulnerability
- auth: Attempt to bypass authentication for running services (e.g. Log into an FTP server anonymously)
- brute:- Attempt to bruteforce credentials for running services
- discovery:- Attempt to query running services for further information about the network (e.g. query an SNMP server).


- NMAP scripts in Linux --> /usr/share/nmap/scripts 
- https://nmap.org/nsedoc/scripts/
- Searching for downloaded scripts:
1. ls -l /usr/share/nmap/scripts/*ftp*
2. grep "ftp" /usr/share/nmap/scripts/script.db.
3. /usr/share/nmap/scripts/script.db


If scripts are missing: 
- sudo apt update && sudo apt install nmap
- sudo wget -O /usr/share/nmap/scripts/< script-name>.nse https://svn.nmap.org/nmap/scripts/< script-name>.nse). This must then be followed up with nmap --script-updatedb, which updates the script.db
5. grep "safe" /usr/share/nmap/scripts/script.db


##### FIREWALL EVASION
- Pn:  tells Nmap to not bother pinging the host before scanning it. This means that Nmap will always treat the target host(s) as being alive, effectively bypassing the ICMP block; however, it comes at the price of potentially taking a very long time to complete the scan (if the host really is dead then Nmap will still be checking and double checking every specified port).
- f:- Used to fragment the packets (i.e. split them into smaller pieces) making it less likely that the packets will be detected by a firewall or IDS.
alternative for -f: providing more control over the size of the packets: --mtu < number>, accepts a maximum transmission unit size to use for the packets sent. This must be a multiple of 8.
- -scan-delay < time>ms:- used to add a delay between packets sent. This is very useful if the network is unstable, but also for evading any time-based firewall/IDS triggers which may be in place.
- -badsum:- this is used to generate in invalid checksum for packets. Any real TCP/IP stack would drop this packet, however, firewalls may potentially respond automatically, without bothering to check the checksum of the packet. As such, this switch can be used to determine the presence of a firewall/IDS.
https://nmap.org/book/man-bypass-firewalls-ids.html

  
 ##### PORT SCANNING 
 **6 NMAP STAGES**z
 1. **_OPEN:_** service is listening on the specified port.
 2. **_CLOSED:_** no service is listening on the specified port, although the port is accessible. By accessible, we mean that it is reachable and is not blocked by a firewall or other security appliances/programs.
 3. **_FILTERED:_** Nmap cannot determine if the port is open or closed because the port is not accessible. This state is usually due to a firewall preventing Nmap from reaching that port. Nmap’s packets may be blocked from reaching the port; alternatively, the responses are blocked from reaching Nmap’s host.
 4. **_UNFILTERED:_** Nmap cannot determine if the port is open or closed, although the port is accessible. This state is encountered when using an ACK scan -sA.
 5. **_OPEN|FILTERED:_** Nmap cannot determine whether the port is open or filtered.
 6. **_CLOSED|FILTERED:_** Nmap cannot determine whether the port is closed or filtered.

- Port 53: DNS 
- Port 22: TCP 

##### TCP HEADER FLAGS:
**1. URG:** Urgent pointer filed is significant. Incoming data is urgent, data classified as URG flag is set to processed immediately.
**2. ACK:** Acknowledge the receipt of a TCP segment and significant.
**3. PSH:** Push flag asking TCP to pass the data to the application promptly.
**4. RST:** Reset the connection. firewall, might send it to tear a TCP connection.  This flag is also used when data is sent to a host and there is no service on the receiving end to answer.
**5. SYN:** Synchronize flag is used to initiate a TCP 3-way handshake and synchronize sequence numbers with the other host. The sequence number should be set randomly during TCP connection establishment.
**6. FIN:** The sender has no more data to send.

- _NOTE:_ If you are not a privilged user (root or sudoer) a TCP connect scan is the only possible option to discover open TCP ports. 
- A closed TCP port responds to a SYN packet with **RST/ACK to indicate that it is not open.**
- sT --> TCP connect scan 
- -F may be used to enable fast mode and decrease the number of scanned ports from 1000 to 100 most common ports 
- -r scan the ports in consecutive order instead of random order 

###### TCP SYN SCAN 
- SYN scan does not need to complete the TCP 3-way handshake, it tears down the connection once it receives a response from the server. 
- -sS option used for this option 
- -sT TCP connect scan traffic 

-_NOTE:_ TCP SYN scan is the default scan mode when running Nmap as a privileged user, running as root or using sudo, and it is a very reliable choice. 


###### UDP SCAN 
- UDP is a connectionless protocol, it does not require any handshake 
- TCP SYN scan is the default scan mode when running Nmap as a privileged user, running as root or using sudo, and it is a very reliable choice. 
