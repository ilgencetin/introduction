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
