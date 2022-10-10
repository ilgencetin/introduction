## Digital Forensics 
**_Digital forensics_** can be explained as investigation of digital evidences for a legal purpose. 
1. **_Public-sector Investigations:_** carried out by government and law enforcement agencies. it must be a crime or civil investigation.
2. **_Private-sector Investigations:_** carried out by corporate bodies by assigning a private investigator, it can be in-house or outsourced. (based on corporate policy violations.)

## Security Operations
_SOC (Security Operations Center):_ team of IT professionals tasked with monitoring a company's network and systems 24 hours for a day and 7 days.
**_Purpose_**
1. **_Find vulnerabilities on the network_** vulnerability might be discovered in any device’s software (operating system and programs) on the network, such as a server or a computer.
2. **_Detect unauthorized activity_** use clues such as geographic location to understand the users in correct manner and their credentials is not exploited.
3. **_Discover policy violations_** 
4. **_Detect intrusions_** attacker successfully exploiting our web application, user visiting a malicious site and getting their computer infected
5. **_Support with the incident response_** SOC team supports incident response team handle the situation whether the incident is severe or not

###### Data Sources for SOC 
- **_Server logs:_** mail server, web server and domain controller on MS Windows networks are examples of servers. successfull and failed login attempts is one of the main information in logs. There is a trove of information that can be found in the server logs.
- **_DNS activity:_** 
- _DNS:_ Domain Name System is the protocol responsible for converting a domain name (ilgencetin.com) to an IP adress among other domain name related queries.
- The SOC can gather information about domain names that internal systems are trying to communicate with by merely inspecting DNS queries.
- **_Firewall logs:_** 
- _Firewall:_ device that controls network traffic mainly lettinf them trough or blocking them. Firewall logs can reveal much information about what packets passed or tried to pass through the firewall.c
- - _Source and destination IP addresses:_ IP address is a logical address that allows you to communicate over the Internet.
- - _Source and destination port numbers:_ computer has IP address and each program on the computer needs a port number to communicate over the network.
- **_DHCP logs:_** 
- _DHCP:_ Dynamic Host Configuration Protocol is responsible for assigning IP address to the systems that try to connect to a network. One analogy of the DHCP request would be when you enter a fancy restaurant, and the waiter welcomes you and guides you to an empty table. Know that DHCP has automatically provided your device with the network settings whenever you can join a network without manual configuration.

###### SOC Services 
**_Reactive Services:_**
1. **_Monitor security posture:_** monitoring the network and computers for security alerts and notifications and responding to them as the need dictates.
2. **_Vulnerability Management:_**  finding vulnerabilities in the company systems and patching them. 
_they are not responsible for them but they assist to this process._
3. **_Malware Analysis:_** recover and detcting malicious programs in a basic base.
4. **_Intrusion detection:_** intrusion detection system (IDS) is used to detect and log intrusions and suspicious packets.
5. **_Reporting_**

**_Proactive Services:_**
1. **_Network Security Monitoring (NSM):_** monitoring the network data and analyzing the traffic to detect signs of intrusions.
2. **_Threat hunting:_** SOC assumes an intrusion has already taken place and begins its hunt to see if they can confirm this assumption.
3. **_Threat intelligence:_** learning about potential adversaries and their tactics and techniques to improve the company’s defences. The purpose would be to establish a threat-informed defence.
