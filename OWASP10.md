## OWASP TOP 10 -- OPEN WEB APPLICATION SECURITY PROJECY 
- Improves security of software.
### INJECTION [SEVERITY 1]
- Root cause of the vulnerability: User controlled input is interpreted as actual commands or parameters by the application.
- Common examples:
- SQL Injection: User controlled input is passed to SQL queries. Attacker can pass in SQL queries to manipulate the outcome of such queries.
- Command Injection: User input is passed to system commands. Attacker is able to execute arbitrary system commands on application servers.
- **Result of the passing:**
- Access, modify and delete info in a database, steal sensitive information. (personal details and credentials)
- Execute arbitrary system commands on server, steal sensitive data and carry out more attacks infra linked server. 
- **Main defences:**
- _Using an allow list:_ when input sent to server, comparison between safe input or characters and input done and if it is marked as safe, input sent. otherwise, input rejected.
- _Stripping input:_ if the input contains dangerous charachteristics, characters removed before they processed.

**OS Command Injection**
- Server-side code (PHP) in a web app makes a system call on the hosting machine. 
- Attacker take advantage of that made system call to execute OS commands on the server 
- _Best Case:_ simple `whoami` and `ls` commands applied.
- _Worst Case:_ spawn a reverse shell to become the user that the web server is running as. `;nc -e/bin/bash` is all just the needed command to own the server.

**Blind Command Injection**
- System command made to the server does not return the response to the user in the HTML document. 

**Active Command Injection**
- System command made to the server does return the response to the user in the HTML document.
- It can be made visible through several HTML elements.
**_Ways to Detect Active Command Injection_**
- `passthru()`
- Linux Commands: `whoami` `id` `ifconfig/ip addr` `uname -a` `ps -ef` 
- Windows Commands: `whoami` `ver` `ipconfig` `tasklist` `netstat -an`
