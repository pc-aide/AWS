# ACM

## Acronym
* ACM - AWS Certificate Management
* ALB - Application Load Balancer
* CA - Certificate Authority
* EB - Elastic Beanstalk
* ELB - Elastic Load Balancer
* LB - Load Balancer
* SSL - Secure Sockets Layer


## Intro
* To host **public SSL certificate** in AWS, you can:
  * Buy your own & upload them using the CLI
  * Have ACM provision & renew public SSL certificates for you (**free** of cost)
* ACM loads SSL certificates on the following integrations:
  * LBs (including the ones breated by EB)
  * CloudFront distributions
  * APIs on API Gateways
* SSL certificates is overall a pain to manually manage, so ACM is great to leverage in your AWS infrastructure
* **Free public certificates** with services
* Managed certificate renewal
  * No "certificate expired" messages
* Private Certificate Authority (CA)
  * Manage your private certificates (not free$)
  
### Diagram
[<img src="https://i.imgur.com/p3sjGja.png">](https://i.imgur.com/p3sjGja.png)

---

## ACM - Good to know
* Possibility of creating **public certificates**
  * Must verify public DNS
  * Must be issed by a tusted public CA
* Possibility of creating **private certificates**
  * For your internal applications
  * You create your own private CA
  * It's **not free**
  * Your applications must ttrust your private CA
* Certificate renewal:
  * **Automatically** done if generated provisioned by ACM
  * Any manually uploaded certificates must be renewed manually & re-uploaded
* ACM is a **regional** service
  * To use with a global application (multiple ALB for example), you need to issue an SSL certificate in each region where your application is deployed
  * You can't copy certs across regions

---

## Use Cases
* Integrated with AWS services:
  * CloudFront
  * ELB
  * API Gateway

---

## Create & Deploy certs
* Private certs
  * Create & activate private CA
  * Request private cert
  * ACM can deploy or export cert
