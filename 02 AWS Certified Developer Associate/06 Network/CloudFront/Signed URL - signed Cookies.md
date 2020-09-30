# Signed URL - signed Cookies

## Acronym
* OAI - Origin Access Identity
* IAM - Identity & access management

## Doc

## Intro
* You want to distribute paid shared content to premium users over the world
* We can use CloudFront Signed URL/Cookies. We attach a policy with:
    * Includes URL expiration
    * Inludes IP ranges to access the data from
    * Trusted signers (which AWS accounts can create signed URLs)
* How long should the URL be valid for?
    * Shared content (movie, music): make it short (a few minutes)
    * Private content (private to the user): you can make it last for years
* Signed URL = access to individual files (one signed URL per file)
* Singed Cookes = access to multiples files (one signed cookie for many files)

### Diagram
* Signed URL:

[<img src="https://i.imgur.com/vMcgsF6.png">](https://i.imgur.com/vMcgsF6.png)

---

## Signed URL vs S3 Pre-Signed URL
* CloudFront Signed URL:
    * Allow access to a path, no matter the origin
    * Account wide key-pair, only the root can manage it
    * Can filter by IP, path, date, expiration
    * Can leverage caching features
* S3 Pre-Signed URL:
    * Issue a request as the person who pre-signed the URL
    * Uses the IAM key of the signing IAM principal
    * Limited lifetime
    
### Diagram
[<img src="https://i.imgur.com/WnZ1hF8.png">](https://i.imgur.com/WnZ1hF8.png)
