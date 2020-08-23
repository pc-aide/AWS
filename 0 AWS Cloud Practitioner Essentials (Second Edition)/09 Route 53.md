# Route 53

## Doc
* [Creating records by using the Amazon Route 53 console](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/resource-record-sets-creating.html)
* [What is Amazon Route 53?](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/Welcome.html)
* [Amazon Route 53 Documentation](https://docs.aws.amazon.com/route53/)

## Terminology
* Amazon Route 53 registrar
  * Alternative godaddy

## Acronym
* ELB - Elastic Load Balancer
* DNS - Domain Name System
* NS - Name Server
* FQDN - Full Qualified Domain Name
* SOA record - Start of Authority record
    * record is implicit

## Ports
* DNS : 53

## What is Route 53?
[<img src="https://i.imgur.com/ogkv9c0.png">](https://i.imgur.com/ogkv9c0.png)

## How does it work?
### User
* type example.com in his chrome
[<img src="https://i.imgur.com/8dhax9f.png">](https://i.imgur.com/8dhax9f.png)

### Translation 
* example.com -> IPv Public -> 54.85.178.219
[<img src="https://i.imgur.com/AfNEGXn.png">](https://i.imgur.com/AfNEGXn.png)

## Creating a Hosted Zone
* First step: creating a Hosted Zone
* This is where your DNS data be kept

[<img src="https://i.imgur.com/778ccCT.png">](https://i.imgur.com/778ccCT.png)
[<img src="https://i.imgur.com/vsnccXO.png">](https://i.imgur.com/vsnccXO.png)
[<img src="https://i.imgur.com/wfz1FRL.png">](https://i.imgur.com/wfz1FRL.png)

## E.g
### AWS Console
1) Instance

[<img src="https://i.imgur.com/gNElgo2.png">](https://i.imgur.com/gNElgo2.png)

2) Ipv4 Public
* WebSrv - httpd

[<img src="https://i.imgur.com/hlD6nS1.png">](https://i.imgur.com/hlD6nS1.png)

3) Service\route 53\Hosted zones\
  * Create Hosted zone
  
[<img src="https://i.imgur.com/yELvo2h.png">](https://i.imgur.com/yELvo2h.png)

#### Create Hosted Zone
* Domain Name
* Comment
* Type

[<img src="https://i.imgur.com/GpRkPt4.png">](https://i.imgur.com/GpRkPt4.png)

### Create Record Set
[<img src="https://i.imgur.com/rPkZ53a.png">](https://i.imgur.com/rPkZ53a.png)

#### Create Record Set
* Name
* Type
  * A - IPv4
  * CNAME - Canonical name
  * AAAA - IPv6
  * TXT - Text
  * PTR - Pointer
  * SRV - Service locator
  * SPF - Sender Policy Framework
  * NAPTR - Name Authority Pointer
  * CAA - Certification Authority Authorization
  * NS
  * SOA - Sart of authority
* Value
  * IPv4 Public, LBA, ELB, CloudFront distribution, hosting my website, and so on
* Routing Policy
  * Simple
  * Weighted 
  * Latency
  * Failover
  * Geolocation
  * Multivalue Answer
  
[<img src="https://i.imgur.com/Cy0Z1gO.png">](https://i.imgur.com/Cy0Z1gO.png)
[<img src="https://i.imgur.com/bEGiry4.png">](https://i.imgur.com/bEGiry4.png)

* It doesn't work because i didn't pay for this domain (domain register)
* No record found (DNS lookup) - no paid no gain ;-)

## DNS Resolution Strategies
* Simple routing
* Geo-location
* Failover
* Weighted round robin
* Latency-based
* Multi-van answer

## Route 53: your Managed DNS Translator
* Domain registrtion
* Global, highly available DNS
* Public & private DNS names
* Multiple routing algorithms
* Both IPv4 & IPv6
* Integrated with other AWS cloud service

## Pendig requests
* How long do domains take to register
* it took less than 2 hours for the registration to be completed on my fresh new AWS account (never registered any domain)
* Domain Name: sampleapplication.co.uk
* Timestamp: 	August 23, 2020 **17:52** UTC-4

[<img src="https://i.imgur.com/tGSV5cm.png">](https://i.imgur.com/tGSV5cm.png)
