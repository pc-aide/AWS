# WAF

## Abbreviation
* vuln - vulnerabilities

## Doc
* [WAF Price](https://aws.amazon.com/waf/pricing/)
* [Firewall Manager](https://aws.amazon.com/firewall-manager/)

## Acronym
* ALB - Application Load Balancer
* WAF - Web Application Firewall
* WASP -  open Web Application Security Project

## Intro
* Filter traffic with rules based on reqest
* Managed rules for common threats
  * Automatically updated
* Works with **CloudFront, ALB, API Gateway**

## Price
* No upfront cost
  * **Rules** deployed & **requests** received
  
  
| Resource Type | Price                             |
|---------------|-----------------------------------|
| Web ACL       | $5.00 per month (prorated hourly) |
| Rule          | $1.00 per month (prorated hourly) |
| Request       | $0.60 per 1 million requests      |

---

## Filtering
* IP address or country
* Value in request (HTTP headers & body, URI strings, lenght)
* SQL code - SQL injection
* Scripts - cross-site scripting

---

## Rule Actions
* Allow
  * Request goes through
* Block
  * Request does not go through
* Count
  * Good way to test rules
  * Also used for limiting
  
### Diagram
[<img src="https://i.imgur.com/adVSd7i.png">](https://i.imgur.com/adVSd7i.png)

---

## WASP Top 10 vuln
1) Injection
2) Broken Authentication
3) Sensitive Data Exposure
4) XML External Entities (XXE)
5) Broken Access control
6) Security misconfigurations
7) Cross Site Scripting (XSS)
8) Insecure Deserialization
9) Using Components with known vulnerabilities
10) Insufficient logging and monitoring

---

## WAF Manager
* Centrally configure & manage WAF rules across multiple accounts & resources
  * AWS Organizations
