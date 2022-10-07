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
