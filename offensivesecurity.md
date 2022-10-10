## Offensive Security
-  break into computer systems
- expoilt software bugs 
- find loopholes 

##### Red Team
- enemy's perspective
- adversary 
- attacking an organization&providing feedback 


##### Bug Bounty

##### Brute Force
- trying many passwords to reach desired credentials

> Security of any system or application is concerned with attacks against:
> 1. Confidentiality 
> 2. Integrity 
> 3. Availabillity


## Defensive Security 
- preventing intrusions from occuring 
- detectinng intrusions when they occur and responding properly

##### Blue Team
- cyber security awareness
- documenting & managing the assets
- update & patch the systems
- setting up preventative security devices: 
- -- firewall: what netwrork traffic can go inside and what can leace the system or network
- -- IPS (intrusion prevention systems): block any network traffic that matches present rules and attack signatures

###### SOC (Security Operations Center)
- team of professionals that monitors the network and its systems to detect malicious cyber security events 
- _main areas of SOC:_
- 1. vulnerabilities: remediating vulnerabilities not assigned to them but their interest 
- 2. policy violation
- 3. unauthorized activity 
- 4. network intrusions

###### SIEM (Security Information and Event Management System)


###### Threat Intelligence
- _intelligence:_ info you gather about actual and potential enemies
- learning about your adversaries --> allows you to know their tactics, techniques and procedures
- identifying threat actor

###### DFIR (Digital Forensics and Incıdent Response)
- _covers:_
- 1. Digital Forensics
- **_forensics_** investigation of crimes
- file system: installed programs, created files, overwritten files and deleted ones.
- system memory: running malicious program memory rather than saving to the disk, aking low-level copy of the system memory
- system logs:traces may be left
- network logs
 
- 2. Incident Response
- **_four major steps of IR
- **_preparation:_** prevent incidents before happening 
- **_detection and analysis:_** learning about severity
- **_containment, eradication and recovery:_** stop the incident before affecting other systems and recover the affected systems
- **_post-incident activity:_** report must be produced
![image](https://user-images.githubusercontent.com/113854816/194542027-161e4ded-0721-44c8-a824-60a15a4a62cb.png)

- 3. Malware Analysis 
- virus as a pieceof code that attaches itself to a program
- trojan horse
- ransomware
-  In general, malware analysis includes:
-  1. static analysis works by inspecting malicious program without running it (assembly language)
-  2. dynamic analysis running the malware in a controlled environment and monitoring activities



## Web Application Security 
###### Common Attacks
###### Logs of Web 
- password security --> testing the long list of passwords and finds the credentials 
###### Product 
- breach the system bu adding spesific characters 
- return data it should not or execute a progrom should 
###### Payment
- seeing payment details are sent in cleartest or using weak encryption
- **_Encryption_** : making data unreadable without knowing the secret key or password


###### Identification and Authentication Failure 
- brute force 
- easy password 
- stored passwords 

##### Broken Access Control 
- access files related to their role or work 
- failing to apply _the principle of the least privilege 
- being able to view or modify someone else's account
- browse pages that requires _authentication_ as an unauthenticated user 

###### IDOR (Insecure Direct Object References)

##### Injection 
- user can implement _mailicous code_ as part of their input --> it can be done bc of the lack of proper validation and sanitization of the user's input 

##### Cryptographic Failures 
- **_crytography_** --> processes of encryption and decryption of data 
- **_encryption_** --> scrambles cleartest into ciphertext 
- - ensures no one can read the data without knowing the secret key 
- **_decryption_** --> converts ciphertext back into cleartext
- examples of cryptographic failures: 
- HTTP: protocol used to acces the web
- HTTPS: secure version of HTTP 
-- others can read everything you send over HTTP but not HTTPS 
- weak cryptographic algorithm 
- using default or weak keys for cryptographic functions

## Operation System Security 
**_Operation Systems:_**
- MS Windows 
- macOS 
- iOS
- Android   
- Chrome OS 
- Linux
- **_hardware_**: all computer parts and peripherals that physically seen. (screen, keyboard, printer, USB flash memory, desktop board)
- **_desktop board includes_**:
- CPU Central Processing Unit 
- RAM memory chips  
- desktop board connected to a storage device (HDD or SSD)
- 
![image](https://user-images.githubusercontent.com/113854816/194513497-76357490-5057-4996-8d66-92cbedf98d94.png)

> Operating system allows programs to access the hardware according to spesicific rules.
> You have some programmes such as: FireFox, Chrome, Safari. These applications can not be run directly in the hardware so operating system is a bridge between hardware and softwares.

###### Authentication and Weak Passwords
- **_Authentication achieved by:_**
- 1. St you know: password or PIN code 
- 2. St you are: fingerprint
- 3. St you have: phone number&SMS message

###### Weak File Permissions
- 'who can access what?'
- attack to confidentiality and integrity
- confidentiality: access files they should not be able to access
- integrity: might modify files that thet should not be able to edit

###### Access to Malicious Programs
- Trojan horses --> attacker able to read and modify the files
- Ransomware --> affects _availability_ by encryting the user's files

> System Administrator calles:
> **_ROOT_** in Android, Apple, Linux
> **_ADMINISTOR_** on MS Windows systems


## Network Security
-  network security refers to the devices, technologies, and processes to protect the confidentiality, integrity, and availability of a computer network and the data on it
-  **_hardware appliances:_** 
-  firewall appliance: predefined set of rules used for blocking connections 
-  IDS (intrusion detection system): detecks attackers' attempts to break into the network
-  IPS (intrusion prevention system): prevent attackers from breaking into to network 
-  VPN (virtual private network): network traffic cannot be read nor altered by a third party
-  **_software appliances:_**
-  antivirus software
-  host firewall: windws defender firewall, apple macOS includes an application firewall 

## Cyber Kill Chain

![image](https://user-images.githubusercontent.com/113854816/194585123-8d028f2f-4263-4791-ae1a-36c060d62b27.png)

1. **_Recon:_** reconnaissance attacker tries to learn abot the target 
- servers, operating system, IP adresses, names of users, email addresses
2. **_Weaponization:_** preparing file with mailicous component
 - to provide the attacker with remote access
3. **_Delivery:_** delivering weaponiced file to the target via feasible method 
- email or USB flash memory
4. **_Exploitation:_**
- user opens the file and execution of the file starts
5. **_Installation:_**
- previous step install the malicious file to system
6. **_Command& Control (C2):_**
- successfull previous steps gives vision to attacker 
7. **_Actions on Objectives:_**
- after gaining control over the system, attacker is able to achieve its goals.
