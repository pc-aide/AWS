# CloudFront

## URL
* [list-cloudfront-ips](https://d7uri8nf7uskq.cloudfront.net/tools/list-cloudfront-ips)

## Doc
* [Global Edge Network](https://aws.amazon.com/cloudfront/features/?nc=sn&loc=2)
* [Lambda@Edge Design Best Practices](https://aws.amazon.com/blogs/networking-and-content-delivery/lambdaedge-design-best-practices/)

## Acronym
* CDN - Content Delivery Network
* SNI - Server Name Indication
* HA - High Availability
* OIDC - OpenID Connect
* TTL - Time To Live
* CRR - Cross Region Replication
* IAM - Identity & Access Management
* ALB - Application load Balancer
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
  * Must first enabled the bucket as a static S3 website
* Custom Origin (HTTP)
  * ALB
  * EC2 instance
  * API Gateway (for more control... otherwise use API Gateway Edge)
  * Any HTTP backend you want
* Possibility to have a primary & secondary origin (HA - Failover)

---

## S3 as an Origin
[<img src="https://i.imgur.com/sPrkSWs.png">](https://i.imgur.com/sPrkSWs.png)

---

## EC2 or ALB as an origin
[<img src="https://i.imgur.com/zOGDyGO.png">](https://i.imgur.com/zOGDyGO.png)

---

## CloudFront vs S3 CRR
* CloudFront:
  * Global Edge network
  * Files are cached for a TTL (maybe a day)
  * Greate for **static content** that must be available everywhere
* S3 CRR:
  * Must be setup for each region you want replication to happen
  * Files are updated in near real-time
  * Read only
  * Great for **dynamic content** that needs to be available at low-latency in few regions
  
---

## Geo Restriction
* You can restrict who can access your distribution
  * **Whitelist**: Allow your users to access your content only if they're in one of the countries on a list of approved contries
  * **Blacklist**: Prevent your users from accessing your content if they're in one of the countries on a blacklist of banned countries
* The "country" is determined using a 3<sup>rd</sup> party geo-IP database
* Use case: **Copyright Laws** to control access to content

---

## Signed URL/Signed Cookies
* You want to distribute paid shared content to premim users over the world
* We can use CloudFront Signed URL/Cookies. We attach a policy with:
  * Includes URL expiration
  * Includes IP ranges to access the data from
  * Trusted signers (which AWS accounts can create signed URLs)
* How log should the URL be valid for?
  * Shared content (movie, music): make it short (a few minutes)
  * Private content (private to the user): you can make it last for years
* Signed URL = access to individual files (one signed URL per file)
* Signed Cookies = access to multiple files (one signed cookie for many files)

### Diagram
[<img src="https://i.imgur.com/xDOx0XI.png">](https://i.imgur.com/xDOx0XI.png)

---

## CloudFront URL vs S3 Pre-Signed URL
* CloudFront Signed URL:
  * Allow access to a path, no matter the origin
  * Account wide **key-pair**, only the **root** can manage it
  * Can filter by IP, path, date, expiration
  * Can leverage caching features
* S3 Pre-Signed URL:
  * Issue a request as the person who pre-signed the URL
  * Uses the IAM key of the signing IAM principal
  * Limited lifetime
  
### Diagram
[<img src="https://i.imgur.com/xFsu962.png">](https://i.imgur.com/xFsu962.png)

---

## Caching
* Cache based on:
  * Headers
  * Session Cookies
  * Query String Parameters
* The cache lives at each CloudFront **Edge Location**
* You want to maximize the cache hit rate to minimize requests on the origin
* Control the TTL (0 seconds to 1 year), can be set by the origin using the Cache-Control header, Epires header...

### Diagram
[<img src="https://i.imgur.com/O8CKuzW.png">](https://i.imgur.com/O8CKuzW.png)

---

## Caching - Whitelist Headers
[<img src="https://i.imgur.com/l6CKM5c.png">](https://i.imgur.com/l6CKM5c.png)

---

## Maximize cache hits by separating static & dynamic distributions
[<img src="https://i.imgur.com/jGKa9Cc.png">](https://i.imgur.com/jGKa9Cc.png)

---

## CloudFront Caching vs API Gateway Caching
[<img src="https://i.imgur.com/KpB91OK.png">](https://i.imgur.com/KpB91OK.png)

---

## Lambda@Edge
* You have deployed a CDN using CloudFront
* What if you wanted to run a global AWS Lambda alongside?
* Or how to implement request filtering before reaching your application?
* For this, you can use **Lambda@Edge**:
  * deploy Lambda functions alongside your CloudFront CDN
    * Build more responsive applications
    * You don't manage servers, Lambda is deployed globally
    * Customize the CDN content
    * Pay only for what you use
* You can use Lambda to change CloudFront requests & responses:
  1) After CloudFront receives a request from a viewer (viewer request)
  2) Before CloudFront forwards the request to the origin (origin request)
  3) After CloudFront receives the response from the origin (origin response)
  4) Before CloudFront forwards the response to the viewer (viewer response)
* You can also generate reponses to viewers without ever sending the request to the origin
* Lambda@Edge doesn't have any cache. It's only to change requests/responses
  
### Diagram
[<img src="https://i.imgur.com/3CuyTMd.png">](https://i.imgur.com/3CuyTMd.png)

---

## Lambda@Edge: Authentication & Authorization
[<img src="https://i.imgur.com/6kJ2BP8.png">](https://i.imgur.com/6kJ2BP8.png)

---

## Lambda@Edge: Use Cases
* Website Security & Privacy
* Dynamic Web Application at the Edge
* Search Engine Optimization (SEO)
* Intellignetly Route Across Origins & Data Centers
* Bot Mitigation at the Edge
* Real-time Image Transformation
* A/B Testing
* User Authentication & Authorization
* User Prioritization, User Tracking & Analytics
* Increasing the cache hit ratio (by modifying headers, normalize user-agent...)

---

## HTTPS configuration & Host
* Config 001:

[<img src="https://i.imgur.com/hgbWQkK.png">](https://i.imgur.com/hgbWQkK.png)

* Config 002 - SSL cert = CloudFront = ALB: 

[<img src="https://i.imgur.com/zIbvOyi.png">](https://i.imgur.com/zIbvOyi.png)

* Config 003:

[<img src="https://i.imgur.com/09pXyiM.png">](https://i.imgur.com/09pXyiM.png)
