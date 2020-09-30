# Security

## Acronym
* DB - database
* OAI - Origin Access Identity

## Doc
* [Restricting Access to Amazon S3 Content by Using an Origin Access Identity](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html)

## Geo Restriction
* You can restrict who can access your distribution
    * **Whitelist**: Allow your users to access your content only if they're in one of the countries on a list of approuved countries
    * **Blacklist**: Prevent your users from accessing your content if they're in one of the countries on a blacklist of banned countries
* The "country" is determined using a 3rd party Geo-IP db
* Use case: Copyright Laws to control access to content

---

## HTTPS
* Viewer Protocol Policy:
    * **Redirect HTTP to HTTPS**
    * Or use HTTPS only
* Origin Protocol Policy (HTTP or S3):
    * HTTPS only
    * Or Match Viewer
        * HTTP => HTTP & HTTPS => HTTPS
* Note:
    * S3 bucket: "websites" don't support HTTPS
    
[<img src="https://i.imgur.com/PAwRgQZ.png">](https://i.imgur.com/PAwRgQZ.png)

### Diagram
[<img src="https://i.imgur.com/VQEPmSs.png">](https://i.imgur.com/VQEPmSs.png)

---

## Demo
* CloudFront\Origin Access identity:

[<img src="https://i.imgur.com/ThNNzZJ.png">](https://i.imgur.com/ThNNzZJ.png)

* BucketPolicy:

[<img src="https://i.imgur.com/Ue6fFNy.png">](https://i.imgur.com/Ue6fFNy.png)

* CloudFront\Distributions\Orings & Origins Groups:

[<img src="https://i.imgur.com/yQD0CRG.png">](https://i.imgur.com/yQD0CRG.png)
[<img src="https://i.imgur.com/AbVwFUj.png">](https://i.imgur.com/AbVwFUj.png)

* Edit Behaviours:

[<img src="https://i.imgur.com/wOrKgfH.png">](https://i.imgur.com/wOrKgfH.png)
[<img src="https://i.imgur.com/bmuQiCZ.png">](https://i.imgur.com/bmuQiCZ.png)

* Restrictions:

[<img src="https://i.imgur.com/K770AWA.png">](https://i.imgur.com/K770AWA.png)
[<img src="https://i.imgur.com/k7R5Mx8.png">](https://i.imgur.com/k7R5Mx8.png)

* Go to Toronto:

[<img src="https://i.imgur.com/L3xbyco.png">](https://i.imgur.com/L3xbyco.png)
