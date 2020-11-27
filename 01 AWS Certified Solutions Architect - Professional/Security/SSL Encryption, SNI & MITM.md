# SSL Encryption, SNI & MITM

## Acronym
* SSL - Secure Sockets Layer
* DNS - Domain Name System
* TLS - Transport Layer Security
* CA - Certificate Authorities
* SNI - Server Name Indication
* DNS SEC - DNS Security Extension
* MITM - Man In The Middle
* ALB - Application Load Balancer
* CLB - Classic Load Balancer
* NLB - Network Load Balancer

## SSL/TSL - Basic
* SSL used to encrypt connections (in-flight)
* TLS whic is a newer version (idem)
* Nowadays, **TLS certificates are mainly used**, but people still refer as SSL
* **Public SSL** certificates are issued by CA
* Many public SSL CA:
  * Comodo, Symantec, GoDaddy, GlobalSign, Digicert, LetsEncrypt, etc...
* SSL certificates have expiration data (you set) & must be renewed

---

## SSL Encryption - How it works
[<img src="https://i.imgur.com/60kHzXa.png">](https://i.imgur.com/60kHzXa.png)

---

## SSL - SNI
* SNI solves the problem of loading **multiple SSL certificates onto one web server** (to serve multiple websites)
* It's a "newer" protocol, & requires the client to **indicate** the hostname of the target server in the initial SSL handshake
* The server will then find the correct certificate, or return the default one
* Note:
  * Only works for ALB & NLB, CloudFront
  * Does not work for CLB
  
### Diagram
[<img src="https://i.imgur.com/VxyWbO5.png">](https://i.imgur.com/VxyWbO5.png)

---

## SSL - Man in the Middle Attacks
[<img src="https://i.imgur.com/TH9ts73.png">](https://i.imgur.com/TH9ts73.png)

### How to prevent
1) Don't use public-facing HTTP, use HTTPS (meaning, use SSL/TLS certificates)
2) Use DNS that has DNS SEC
  * To end send a client to a pirate server, a DNS response needs to be "forged" by a server which intercepts them
  * It's possible to protect your domain name by configuring DNS SEC
  * Route 53 suppports DNS SEC for domain registration. However, Rout 53 does not support DNS SEC service, regardless of whether the domain is registered with Route 53. If you want to configure DNS SEC for a domain that is registered with Route 53, you must use another SNS service provider
  * You could run a custom DNS server on EC2 for example (**Bind** is the most popular, dnsmasq, KnotDNS, PowerDNS)
