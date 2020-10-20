# ACM

## Acronym
* ACM - AWS Certificate Manager
* LB - Load Balancer
* EB - Ealstic Beanstalk
* ALB - Application Load Balancer

## Doc

## Intro
* To host public SSL certificates in AWS, you can:
    * Buy your own & upload them using the CLI
    * Have ACM provision & renew public SSL certificate for you (free of cost)
* ACM loads SSL certificates on the following integrations:
    * LBs (including the ones created by EB)
    * CloudFront distributions
    * APIs on API Gateways
* SSL certificates is overall a pain to manually manage, to ACM is great to leverage in your AWS infrastructure

### Diagram
[<img src="https://i.imgur.com/uwsiTHR.png">](https://i.imgur.com/uwsiTHR.png)

---

## Demo
* certificate for EB
