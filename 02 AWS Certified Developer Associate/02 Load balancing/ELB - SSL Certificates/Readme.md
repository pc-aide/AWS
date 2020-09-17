# ELB - SSL Certificates

## Doc
* [Replace the SSL certificate for your Classic Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-update-ssl-cert.html?icmpid=docs_elb_console)
* [Create a Classic Load Balancer with an HTTPS listener](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-create-https-ssl-load-balancer.html?icmpid=docs_elb_console#config-backend-auth)
* [Listeners for your NLB](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-listeners.html)

## Acronym
* SSL - Secure Sockets Layers
* TLS - Transport Layer Security
* VPC - Virtual Private Cloud
* ACM - AWS Certificate Manager
* SNI - Server Name Indication
* ALB - Application Loading Balancer
* NLB - Network Loading Balancer
* CLB - Classic Loading Balancer
* ELB - Elastic Load Balancer
* IAM - Indentity & access Manager

## Terminology
* X.509 certificate

## Introduction
* An SSL Certificate allows traffic between your clients & your LB to be encrypted in transit (in-flight encryption)
* SSL refers to Secure Sockets Layer, used to encrypt connection - developed by Netscape
* TLS refers to Transport Layer Security, which is a new version - refont the SSL by Microsoft
* Nowadays, TLS certificates are mainly used, but people still refer as SSL
* Public SSL certificates are issued by Certificate Authorities (CA)
    * Comodo, Symantec, GoDaddy, GlobalSign, Digicert, Letsencrypt, ssls.com (cheap ssl), etc
    * attach our SSL to your LB
* SSL certificates have an expiration data (you set) & must be renewed

## Topology
* LB - SSL Certificates

[<img src="https://i.imgur.com/H2bAOjb.png">](https://i.imgur.com/H2bAOjb.png)

* The LB uses an X.509 certificate (SSL/TLS server certificate)
* You can manage certificates using ACM 
* You can create upload your own certificates alternatively
* HTTPS listener:
    * You must specify a default certificate
    * You can add an optional list of certs to support multiple domains
    * Clients can use SNI (Server Name Indication) to specify the hostname they reach
    * Ability to specify a security policy to support older version of SSL/TLS (legacy clients)
    
## SSL - Server Name Indication
* SNI solves the problem of loading **multiple SSL certificates onto one web server** (to serve multiple websites)
* It's a "newer" protocol, & requires the client to **indicate** the hostname of the target server in the initial SSL handshake
* Ther server will then find the correct certificate, or return the default one
* Note:
    * Only works for ALB & NLB (newer generation), CloudFront
    * Does not work for CLB (older generation)

### Topology
[<img src="https://i.imgur.com/rlPO149.png">](https://i.imgur.com/rlPO149.png)

## ELB - SSL Certificates
* CLB (v1)
    * Support only one SSL certificate
    * must use multiple CLB for multiple hostname with multiple SSL certificates
* ALB (v2)
    * Supports multiple listeners with multiple SSL certificates
    * Uses Server Name Indication (SNI) to make it work
* NLB (v2)
    * Supports multiple listeners with multiple SSL certificates
    * Uses Server Name Indication (SNI) to make it work
    
## Demo SSL cert
### CLB
* Listener :

[<img src="https://i.imgur.com/DlZ1QvD.png">](https://i.imgur.com/DlZ1QvD.png)

* cipher:

[<img src="https://i.imgur.com/EbHwEJb.png">](https://i.imgur.com/EbHwEJb.png)
[<img src="https://i.imgur.com/ec6OLau.png">](https://i.imgur.com/ec6OLau.png)

* SSL cert:

[<img src="https://i.imgur.com/7YKjhc0.png">](https://i.imgur.com/7YKjhc0.png)

### ALB
* Listener:

[<img src="https://i.imgur.com/sHT1n9t.png">](https://i.imgur.com/sHT1n9t.png)

* Default action(s)

[<img src="https://i.imgur.com/ZRnlpaP.png">](https://i.imgur.com/ZRnlpaP.png)
[<img src="https://i.imgur.com/jTw0rjr.png">](https://i.imgur.com/jTw0rjr.png)
[<img src="https://i.imgur.com/j9Ur9Bt.png">](https://i.imgur.com/j9Ur9Bt.png)

### NLB
* wainting ~2min for new NLB:

[<img src="https://i.imgur.com/hpbmjGA.png">](https://i.imgur.com/hpbmjGA.png)
[<img src="https://i.imgur.com/KPJm76D.png">](https://i.imgur.com/KPJm76D.png)
[<img src="https://i.imgur.com/dl0lxvn.png">](https://i.imgur.com/dl0lxvn.png)

* Listener:

[<img src="https://i.imgur.com/rDj4dCF.png">](https://i.imgur.com/rDj4dCF.png)
[<img src="https://i.imgur.com/1k25XqC.png">](https://i.imgur.com/1k25XqC.png)

* Forward to... :

[<img src="https://i.imgur.com/03QlfiU.png">](https://i.imgur.com/03QlfiU.png)
