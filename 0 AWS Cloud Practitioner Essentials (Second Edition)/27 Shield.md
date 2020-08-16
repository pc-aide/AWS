# Shield

## Doc
* aws.amazon.com/shield

## Acronym
* API - Application Program Interface
* DRT- DDoS response team
* DDoS - Distributed Denial of Service
  * Many attacker (botnet)
* WAF - Web Application Firewall
  * E.g: FortiOS, Junos OS
* Std - Standard
* Adv - Advanced
* ELB - Elastic Load Balancer
* DoS - Denial of Service
  * One attacker 

## Getting started with AWS Shield
* AWS Shield is a managed DDoS protection service that safeguards applications running on AWS

## DoS 
* A deliberate attempt to make your website or application unabailable to users
  * E.g: Many request on IP (Ping of Death, Slowloris, flooding, HTTP floods, DNS query floods,
    reflection attack, SYN floods, SYN-ACK, UDP floods, UDP reflection, NTP, SSDP reflection)

## DDoS
* Multiple sources are used to attack target; infrastructure & application layers can be affected
  * Botnet

## DDos application layer attack
[<img src="https://i.imgur.com/FP5Q2S1.png">](https://i.imgur.com/FP5Q2S1.png)

## DDoS mitigation challenges
* Complex setup & implementation
* Bandwidth limitations
* Manual intervention
* Time consuming
* Degraded performance
* Expensive

## Shield tiers 
* AWS Shield Std
  * Automatic protections available for all AWS customers, at no additional charge
* AWS Shield Advanced
  * Paid service for higher levels of protection, features, & benefits
  
## Shield Std
* Automatic proctection
  * Any AWS resource
  * Any AWS region
* Quick detection - Always-on
* Inline attack mitigation
  * built-in automated mitigation techniques
  * Avoids latency impact
* Self service
  * No need to engage AWS Support

## Shield Advanced
* Specialized support (AWS Support 24/7 access)
  * Call: The DRT
* Advanced attack mitigation
* Visibility & attack notification
* Always-on monitoring
  * Amazon Route 53, Amazon CloudFront, ELB, Elastic IP
* Enhanced detection
* DDoS cost protection

## Shield benefits
* Cost efficient
* Seamless integration & deployment
* Customizable proctection

## Protecting your DNS 
* Using Amazon Route 53
  * AWS Shield Standard - Hosted zones
  * AWS Shield Adv - Attack visibility, DRT support
  
## Protecting web application & APIs
* Using Amazon CloudFront or ALB
  * AWS Shield Standard - Always-on, scrubs bad traffic
  * AWS Shield Adv - DRT support, traffic engineering, application layer protection
  
## Protecting other application
* Using Elastic IP Address
  * AWS Shield Std - Build-in techniques
  * AWS Shield Adv - Custom mitigation profiles, additional bandwidth
  
## Wrap-up
* AWS Shield provides
  * Bult-in protection againt DDoS attacks
  * Access to tools, services & expertise to help you protect your AWS applications
 
