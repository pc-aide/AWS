# SSL Encryption, SNI & MITM

## Acronym
* SSL - Secure Sockets Layer
* TLS - Transport Layer Security
* CA - Certificate Authorities
* SNI - Server Name Indication
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
