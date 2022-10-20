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
