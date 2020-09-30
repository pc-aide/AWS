# Demo - CloudFront

## Acronym
* OAI - Origin Access Identity

## Doc
* [Amazon CloudFront](https://aws.amazon.com/cloudfront/)
* [Lambda@Edge Design Best Practices](https://aws.amazon.com/blogs/networking-and-content-delivery/lambdaedge-design-best-practices/?sc_ichannel=ha&sc_icontent=console_aws-console-cloudfront_cloudfront_cf-best-practices_awssm-3496&sc_icampaign=cf-best-practices&trk=ha_awssm-3496&sc_iplace=console_aws-console-cloudfront_cloudfront_INFOBAR)
* [Announcement: RTMP Support Discontinuing on December 31, 2020](https://forums.aws.amazon.com/ann.jspa?annID=7356)
    * End of Flash (by Adobe)

## Intro
* We'll create an S3 bucket
* We'll create a CloudFront distribution
* We'll create an OAI
* We'll limit the S3 bucket to be accessed only using this identity

---

## Demo
````bash
aws s3 mb s3://demo-01-cloudfront
````

* upload some file in this bucket:

[<img src="https://i.imgur.com/EFWbDrX.png">](https://i.imgur.com/EFWbDrX.png)

* CloudFront\Create Distribution\Web:

[<img src="https://i.imgur.com/JCBQtEN.png">](https://i.imgur.com/JCBQtEN.png)

* Create Distribution
    * Origin Domain Name: demo-01-cloudfront.s3.amazonaws.com
    * Origin Path: empty
    * Origin ID: don't touch
    * RadioButton: yes 'Restict Bucket Acess
    * Origin Access Identity: Create a New Identity
    * Comment: access-identity-demo
    * Grant Read Permissions on Bucket: Yes, Update Bucket Policy
    
[<img src="https://i.imgur.com/f5bSUOV.png">](https://i.imgur.com/f5bSUOV.png)

* Default Cache Behavior Settings
    * Viewer Protocol Policy: Redirect HTTP to HTTPS
