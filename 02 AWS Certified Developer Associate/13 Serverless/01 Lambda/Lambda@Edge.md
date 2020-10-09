# Lambda@Edge

## Acronym
* CDN - Content Delivery Network
* SEO - Search Engine Optimization

## Doc

## Intro
* You have deployed a CDN using CloudFront
* What if you wanted to run a global Lambda alongside?
* Or how to implement request filtering before reaching your application?
* For this, your can use **Lambda@Edge**:
    * deploy Lambda functions alongside your CloudFront CDN
        * build more responsive applications
        * You don't manage servers, Lambda is deployed globally
        * Customize the CDN content
        * Pay only for what you use

---

## Lambda@Edge
* You can use Lambda to change CloudFront requests & responses:
    * After CloudFront receives a request from a viewer (viewer request)
    * Before CloudFront forwards the request to the origin (origin request)
    * After CloudFront receives the response from the origin (origin response)
    * Before CloudFront forwards the response to the viewer (viewer response)
* You can also generate responses to viewer without ever sending the request to the origin
    
### Diagram
[<img src="https://i.imgur.com/Bumd8BY.png">](https://i.imgur.com/Bumd8BY.png)

---

## Global application
[<img src="https://i.imgur.com/dyxbSs7.png">](https://i.imgur.com/dyxbSs7.png)

---

## Use Cases
* Website Security & Privacy
* Dynamic Web application at the Edge
* SEO
* Intelligently Route Across Origins & Data Centers
* Bot Mitigation at the Edge
* Real-time Image Transformation
* A/B Testing
* User Authentication & Authorization
* User Prioritization
* User Tracking & Analytics
