# AWS WAF

## Acronym
* WAF - Web Application Firewall
* HTTP/2 - HTTP & HTTPS
* ACL - Access-Control List

## Doc
* [AWS WAF Documentation](https://docs.aws.amazon.com/waf/)

## Intro
* AWS WAF is a web application firewall that lets you monitor web requests that are
  forwarded to Amazon CloudFront distributions or an Application Load Balancer.
  You can also use AWS WAF to block or allow requests based on conditions that you
  specify, such as the IP addresses that requests originate from or values in the requests. 
* AWS WAF helps to prevent web sites & web applications from being maliciously attacked
  by common web attact patterns
* Used to identify how Amazon CloudFront distributions & appliaction load balancers respond
  to web requests
* It filters both HTTP/2 request distinguishing between legitimate & harmful inbound requests
  
## AWS Console
* service\WAF & Shield

[<img src="https://i.imgur.com/sjzffuA.png">](https://i.imgur.com/sjzffuA.png)

## WAF Compoents
* Conditions
* Rules
* Web ACLs

  * Conditions allow you to specify what elements of the incoming HTTP/2 request
    you want WAF to be monitoring for
1) Crost-site scripting :

[<img src="https://i.imgur.com/dxrY5kB.png">](https://i.imgur.com/dxrY5kB.png)

2) Geo match :

[<img src="https://i.imgur.com/j9wkmNq.png">](https://i.imgur.com/j9wkmNq.png)

3) IP Addresses : 

[<img src="https://i.imgur.com/tQDw4u5.png">](https://i.imgur.com/tQDw4u5.png)

4) Size constraints :

[<img src="https://i.imgur.com/vr7lPHa.png">](https://i.imgur.com/vr7lPHa.png)

5) SQL injection attacks :

[<img src="https://i.imgur.com/NnqBxSs.png">](https://i.imgur.com/NnqBxSs.png)

6) String & regex matching :

[<img src="https://i.imgur.com/AUz4zfa.png">](https://i.imgur.com/AUz4zfa.png)

## AWS Rules
* Intro :

[<img src="https://i.imgur.com/rZd301n.png">](https://i.imgur.com/rZd301n.png)

* Rules types : 

[<img src="https://i.imgur.com/YQzDq75.png">](https://i.imgur.com/YQzDq75.png)

* WEB ACL :

[<img src="https://i.imgur.com/F4LQogh.png">](https://i.imgur.com/F4LQogh.png)

* WEB ACL\components :

[<img src="https://i.imgur.com/KBUB4s0.png">](https://i.imgur.com/KBUB4s0.png)
[<img src="https://i.imgur.com/kFckwKv.png">](https://i.imgur.com/kFckwKv.png)
