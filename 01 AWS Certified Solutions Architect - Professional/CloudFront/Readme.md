# CloudFront

## Doc
* [Global Edge Network](https://aws.amazon.com/cloudfront/features/?nc=sn&loc=2)

## Acronym
* CDN - Content Delivery Network
* DDoS - Distribute Deny of Service
* OAI - Origin Access Identity
* WAF - Web Application Firewall

## Intro
* CDN
* Improves read performance, **content is cached** at the **edge**
* 216 Point of Presence globally (edge locations)
* DDoS protection, integration with Shield, AWS WAF
* Can expose external HTTPS & can talk to internal HTTPS backends

### Map
[<img src="https://i.imgur.com/nFNlLHr.png">](https://i.imgur.com/nFNlLHr.png)

---

## Origins
* S3 bucket
  * For distributing files & **caching** them at the **edge**
  * Enhanced security with CloudFront **OAI**
  * CloudFront can be used as an ingress (to upload files to S3)
* S3 website
  * Must first enabled 
