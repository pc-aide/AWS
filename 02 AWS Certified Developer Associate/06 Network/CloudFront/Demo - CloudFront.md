# Demo - CloudFront

## Acronym
* OAI - Origin Access Identity

## Doc
* [Amazon CloudFront](https://aws.amazon.com/cloudfront/)
* [Lambda@Edge Design Best Practices](https://aws.amazon.com/blogs/networking-and-content-delivery/lambdaedge-design-best-practices/?sc_ichannel=ha&sc_icontent=console_aws-console-cloudfront_cloudfront_cf-best-practices_awssm-3496&sc_icampaign=cf-best-practices&trk=ha_awssm-3496&sc_iplace=console_aws-console-cloudfront_cloudfront_INFOBAR)
* [Announcement: RTMP Support Discontinuing on December 31, 2020](https://forums.aws.amazon.com/ann.jspa?annID=7356)
    * End of Flash (by Adobe)
* [How to set up a CloudFront distribution for Amazon EC2](https://aws.amazon.com/cloudfront/getting-started/EC2/?sc_ichannel=ha&sc_icontent=console_aws-console-cloudfront_cloudfront_cf-dynamic-content_awssm-3496&sc_icampaign=cf-dynamic-content&trk=ha_awssm-3496&sc_iplace=console_aws-console-cloudfront_cloudfront_INFOBAR)
* [AWS Cloudfront redirecting to S3 bucket](https://stackoverflow.com/questions/38735306/aws-cloudfront-redirecting-to-s3-bucket)

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
    * leave ohter options: default
* Create Distribution

[<img src="https://i.imgur.com/R47g1ir.png">](https://i.imgur.com/R47g1ir.png)
[<img src="https://i.imgur.com/4gscaJf.png">](https://i.imgur.com/4gscaJf.png)
[<img src="https://i.imgur.com/6zehY3y.png">](https://i.imgur.com/6zehY3y.png)

* It can take few minutes or 10 minutes:

[<img src="https://i.imgur.com/5Rhk62L.png">](https://i.imgur.com/5Rhk62L.png)

* Deployed:

[<img src="https://i.imgur.com/FAbNecl.png">](https://i.imgur.com/FAbNecl.png)
[<img src="https://i.imgur.com/9Khmgiw.png">](https://i.imgur.com/9Khmgiw.png)

* OAI:

[<img src="https://i.imgur.com/Yf6cZSe.png">](https://i.imgur.com/Yf6cZSe.png)

* Bucket\policy:

[<img src="https://i.imgur.com/DqlLINz.png">](https://i.imgur.com/DqlLINz.png)

* test my content (3 files uploads):

[<img src="https://i.imgur.com/vACPNdL.png">](https://i.imgur.com/vACPNdL.png)
[<img src="https://i.imgur.com/UOmpIOo.png">](https://i.imgur.com/UOmpIOo.png)
[<img src="https://i.imgur.com/e7bSeMa.png">](https://i.imgur.com/e7bSeMa.png)

* But a AccessDenied (from Origin):

[<img src="https://i.imgur.com/7iGK0zx.png">](https://i.imgur.com/7iGK0zx.png)

* Make a file public:

[<img src="https://i.imgur.com/473VMW5.png">](https://i.imgur.com/473VMW5.png)
[<img src="https://i.imgur.com/3NPn9OD.png">](https://i.imgur.com/3NPn9OD.png)
[<img src="https://i.imgur.com/uh3DllV.png">](https://i.imgur.com/uh3DllV.png)

* Domain Name vs Origin (not same permissions):

[<img src="https://i.imgur.com/ay9iBzd.png">](https://i.imgur.com/ay9iBzd.png)
[<img src="https://i.imgur.com/7BnOhVW.png">](https://i.imgur.com/7BnOhVW.png)
[<img src="https://i.imgur.com/LOhTVVH.png">](https://i.imgur.com/LOhTVVH.png)

* dig Domain Name:
* you need to **wait 3-4 hours** for basically the DNS to propagate properly 
  before you get the CloudFront access to your images & your files directly using the CloudFront URL
  instead of using the S3 URL
* You can test with curl -I http://YOUR_CF_DOMAINNAME.cloudfront.net
      * -I (switch curl) Head

[<img src="https://i.imgur.com/19pg0Jz.png">](https://i.imgur.com/19pg0Jz.png)
[<img src="https://i.imgur.com/V7pODJP.png">](https://i.imgur.com/V7pODJP.png)

* dig Origin:

[<img src="https://i.imgur.com/dFK9o3f.png">](https://i.imgur.com/dFK9o3f.png)
[<img src="https://i.imgur.com/UkyBE1C.png">](https://i.imgur.com/UkyBE1C.png)

* Remove public (cat.jpg):

[<img src="https://i.imgur.com/7f4LUdG.png">](https://i.imgur.com/7f4LUdG.png)
[<img src="https://i.imgur.com/EUWsaXK.png">](https://i.imgur.com/EUWsaXK.png)

* DNS Name (private):

[<img src="https://i.imgur.com/GoLl1Qn.png">](https://i.imgur.com/GoLl1Qn.png)
[<img src="https://i.imgur.com/Ko2IsE8.png">](https://i.imgur.com/Ko2IsE8.png)
[<img src="https://i.imgur.com/fhaiRtM.png">](https://i.imgur.com/fhaiRtM.png)
