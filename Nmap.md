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
- **-sN** TCP Null Scans
- **-sF** TCP FIN Scans 
- **-sX** TCP Xmas Scans 
