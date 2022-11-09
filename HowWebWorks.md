## DNS (Domain Name System)
- Tool for communicate with devices on the internet without remembering complex numbers. 
- Websites has an IP number such as 100.00.10.000, instead of remembering this IP, remembering ilgencetin.com will be much more easier.

## Domain Hierarchy 
### TLD (Top-Level Domain)
- rigthand part of a domain name. (.com, .edu, .gov, .mil)
- TLD versions: https://data.iana.org/TLD/tlds-alpha-by-domain.txt
- Two types of TLD:
1. **gTLD generic top-level domain** meant to tell the user the domain name's purpose
- a .com would be for commercial purposes
- .org for an organisation
- .edu for education 
- .gov for government
2. **ccTLD country code top level domain** geographical purposes 
- .ca for sites based in Canada
- .co.uk for sites based in the United Kingdom and so on.

### Second-Level Domain 
- ilgencetin.com .com is TLD and ilgencetin is Second Level Domain
- Limited to 63 characters + the LTD and can use a-z 0-9 and hyphens _but it can not start nor end with -_ or have consecutive hyphens

### Subdomain
- subdomain sits on the left side of the second-level domain such as admin.servers.ilgencetin.com
- **like second-level domain** Limited to 63 characters + the LTD and can use a-z 0-9 and hyphens _but it can not start nor end with -_ or have consecutive hyphens
- you can use multiple subdomains but _length must be kept to 253 characters or less._

## DNS Record Types 
- DNS not only for websites and several types of DNS record exist.
1. **A Record:** Resolve to IPv4 addresses such as 100.00.10.000
2. **AAAA Record:** Resolve IPv6 addresses such as 2606:4700:20::681a:be5
3. **CNAME Record:** These records resolve to another domain name, for example, TryHackMe's online shop has the subdomain name store.tryhackme.com which returns a CNAME record shops.shopify.com. Another DNS request would then be made to shops.shopify.com to work out the IP address.
4. **MX Record:** These records resolve to the address of the servers that handle the email for the domain you are querying, for example an MX record response for tryhackme.com would look something like alt1.aspmx.l.google.com. These records also come with a priority flag. This tells the client in which order to try the servers, this is perfect for if the main server goes down and email needs to be sent to a backup server.
5. **TXT Record:** common ones can be to list servers that have the authority to send an email on behalf of the domain (this can help in the battle against spam and spoofed email). They can also be used to verify ownership of the domain name when signing up for third party services.

## Making A Request 
1. When you request a domain name, your computer first checks its local cache to see if you've previously looked up the address recently; if not, a request to your Recursive DNS Server will be made.
2. A Recursive DNS Server is usually provided by your ISP, but you can also choose your own. This server also has a local cache of recently looked up domain names. If a result is found locally, this is sent back to your computer, and your request ends here (this is common for popular and heavily requested services such as Google, Facebook, Twitter). If the request cannot be found locally, a journey begins to find the correct answer, starting with the internet's root DNS servers.
3. The root servers act as the DNS backbone of the internet; their job is to redirect you to the correct Top Level Domain Server, depending on your request. If, for example, you request www.tryhackme.com, the root server will recognise the Top Level Domain of .com and refer you to the correct TLD server that deals with .com addresses.
4. The TLD server holds records for where to find the authoritative server to answer the DNS request. The authoritative server is often also known as the nameserver for the domain. For example, the name server for tryhackme.com is kip.ns.cloudflare.com and uma.ns.cloudflare.com. You'll often find multiple nameservers for a domain name to act as a backup in case one goes down.
5. An authoritative DNS server is the server that is responsible for storing the DNS records for a particular domain name and where any updates to your domain name DNS records would be made. Depending on the record type, the DNS record is then sent back to the Recursive DNS Server, where a local copy will be cached for future requests and then relayed back to the original client that made the request. DNS records all come with a TTL (Time To Live) value. This value is a number represented in seconds that the response should be saved for locally until you have to look it up again. Caching saves on having to make a DNS request every time you communicate with a server.

## HTTP (HyperText Transfer Protocol)
-  HTTP is the set of rules used for communicating with web servers for the transmitting of webpage data, whether that is HTML, Images, Videos, etc.
## HTTPS (HyperText Transfer Protocol Secure)
- HTTPS is the secure version of HTTP. HTTPS data is encrypted so it not only stops people from seeing the data you are receiving and sending, but it also gives you assurances that you're talking to the correct web server and not something impersonating it.

## URL (Uniform Resource Locator)
![image](https://user-images.githubusercontent.com/113854816/196927415-31ad9c05-9e83-4d2c-8376-944db637c2d1.png)

- **Scheme:** what protocol used for accessing the resource such as HTTP,  HTTPS, FTP 
- **User:** Some services require authentication to log in 
- **Host:** Domain name or IP address of the server we wish to enter. 
- **Port:** usually 80 for HTTP and 443 for HTTPS
- **Path:** file name or location of the resource you are trying to access.
- **Query String:** Extra bits of information that can be sent to the requested path. For example, /blog?id=1 would tell the blog path that you wish to receive the blog article with the id of 1.
- **Fragment:** reference to a location on the actual page requested. commonly used for long content and certain part of the page directly linked to it.

###### Making a Request
1. **GET /HTTP/1.1** Request is sending
2. **Host: ilgencetin.com** website we are searching
3. **User-Agent: Mozilla/5.0 Firefox/87.0** web server we are using
4. **Referer: https://ilgencetin.com** web server that web page that referred to us 

###### GET Request: 
- Getting information from a web server
###### POST Request:
- Submitting data to the web server and potentially creating new records
###### PUT Request:
- Submitting data to a web server to update information
###### DELETE Request:
- Deleting info/records from a web server.

![image](https://user-images.githubusercontent.com/113854816/200759699-eff4c5f5-8e87-4fea-af61-802a1eaba0b8.png)

**HTTPS STATUS CODE:** informing the client of the outcome of their request and also potentially how to handle it. Always found in HTTP server respond's first line.

## Headers
- Headers are additional bits of data you can send to the web server when making requests.
##### COMMON REQUEST HEADERS:
**_HOST:_** some web servers host multiple websites so by using host headers, you can seperate them and tell it which one you require, otherwise default website for the server will come.
**_USER-AGENT:_** Browser software and version number, some elements of HTML, JavaScript and CSS are only available in certain browsers. 
**_CONTENT_LENGTH:_** Tells to web server how much data to expect in the web request. Server will be sure to not missing any data.
**_Accept-Encoding:_** Tells the web server what types of compression methods the browser supports so the data can be made smaller for transmitting over the internet.
**_Cookie:_** Data sent to the server to help remember your information.

##### COMMON RESPONSE HEADERS:
**_Set-Cookie:_** Information to store which gets sent back to the web server on each request
**_Cache-Control:_** How long to store the content of the response in the browser's cache before it requests it again.
**_Content-Type:_** his tells the client what type of data is being returned, i.e., HTML, CSS, JavaScript, Images, PDF, Video, etc. Using the content-type header the browser then knows how to process the data.
**_Content-Encoding:_** What method has been used to compress the data to make it smaller 

## COOKIES
- Cookies are saved when you receive a "Set-Cookie" header from a web server.Then every further request you make, you'll send the cookie data back to the web server. Because HTTP is stateless (doesn't keep track of your previous requests), cookies can be used to remind the web server who you are, some personal settings for the website or whether you've been to the website before. 
- Cookies mainly used for website authentication 
- Usually they are not clear-text string but a token
- Cookies are saved when you receive a "Set-Cookie" header from a web server. 
- **_TOKEN:_** unique secret code that isn't easily humanly quessable 

## HOW WEBSITES WORK?
- When you visit a website, your browser (like Safari or Google Chrome) makes a request to a web server asking for information about the page you're visiting. It will respond with data that your browser uses to show you the page; a web server is just a dedicated computer somewhere else in the world that handles your requests.
- Two major components:
1. Front End (Client-Side): browser renders a website
2. Back End (Server-Side): server processes your request and returns a response

Websites created by using:
- **HTML (HyperText Markup Language:** to build websites and define the structure.
- **CSS:** to make websites look pretty by adding styling options 
- **JavaScript:** implement complex features on pages using interactivity

Structure of which is the same for every website:
![image](https://user-images.githubusercontent.com/113854816/200765734-3bdf0086-4633-42e3-a015-8c486cceefcf.png)

**Structure:** 
- **<!DOCTYPE html>:** defines that page is a HTML5 document, this helps standardisation across different browsers and tells the browser use it.
-**< html>:** root element, all other elements come after that code.
-**< head>:** contains information about the page (page title)
- **< body>:** defines HTML document's body; only content inside the body is shown in the browser
- **< h1>:** large heading
- **< p>:** paragraph
- **< button>**
- **< img>**

**HTML VS. JAVASCRIPT**
- HTML only used for creating the website structure, JS gives as dynamic structure, which controls functionality of web pages.
- JavaScript added within the page with source code and can be loaded with < script> or included remotely with src attribute:  < script src=...>
 
##### SENSITIVE DATA EXPOSURE 
- Sensitive clear-text information did not protected to the end-user, usually can be found in a site's frontend source code. 
- Website developer may have forgotten remove login credentials, hidden links to private parts of the website or other sensitive data shown in HTML or JavaScript.

##### HTML INJECTION 
- Occurs when unfiltered user input is displayed on the page. 
- If a website fails to sanitise user input (filter any "malicious" text that a user inputs into a website), and that input is used on the page, an attacker can inject HTML code into a vulnerable website.
- **_Input sanitisation:_** as information a user inputs into a website is often used in other frontend and backend functionality.

**LOAD BALANCERS:**
- Provide to feauters: ensuring high traffic websites can handle the load and providing failover if a server becomes unresponsive.
- When you make a request to a website with load balancers, request firstly goes to load balancer and after that request goes to multiple servers
- **_round-robin:_** sends it to each server in turn
- **_weighted:_** checks how many requests a server is currently dealing with and sends it to the least busy one.
- **_health check:_** checkes whether server responds or not and if it not, stops traffic until the respond comes.

**CDN (Content Delivery Networks):**
- Cuts down traffic to a busy website. 
- Host static files from your website (JS, CSS, img, vid) and host them across several servers all over the world.
- When request comes, CDN finds out the nearest server which is phsically located and send the request there. 

**DATABASES**
- Websites search for information in the databases and MySQLi MSSQL, Postgres are some examples of these databases.

**WAF (Web Application Firewall)**
- Sits between web request and the web server 
- _Primary purpose:_ protect webserver from hacking or DoS attacks. 
- Checks the requests sended from real browser or bot 
- _Rate limiting::_ only certain amount of requests from an IP can be obtained. 
- If otherwise, requests dropped and never sent to the webserver

**Web Server**
- A web server is a software that listens for incoming connections and then utilises the HTTP protocol to deliver web content to its clients.
- Web Server Software: Apache, Nginc, IIS and NodeJS

**Virual Hosts**
- Web servers can host multiple websites with different domain names; to achieve this, they use virtual hosts. 
- The web server software checks the hostname being requested from the HTTP headers and matches that against its virtual hosts (virtual hosts are just text-based configuration files). 
- If it finds a match, the correct website will be provided. If no match is found, the default website will be provided instead.
