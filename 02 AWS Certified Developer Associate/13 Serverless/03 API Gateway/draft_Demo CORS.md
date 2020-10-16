# Demo CORS

## Acronym
* CORS - Cross-Origin Resource Sharing

## Doc
* [Bucket Policy Examples](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html#example-bucket-policies-use-case-2)

## CORS
* CORS must be enabled when you receive API calls from another domain
* The OPTiONS pre-flight request must contain the following headers:
    * Access-Control-Allow-Methods
    * Access-Control-Allow-Headers
    * Access-Control-Allow-Origin
* CORS can be enabled through the console

---

## CORS - Enabled on the API Gateway
[<img src="https://i.imgur.com/U4QVkIL.png">](https://i.imgur.com/U4QVkIL.png)

---

## Demo
* Create S3
````bash
aws s3 mb s3://demo-cors-apigw --region us-east-1
````
* put-public-block
````bash
aws s3api put-public-access-block \
--bucket demo-cors-apigw \
--public-access-block-configuration  BlockPublicAcls=true,IgnorePublicAcls=true,BlockPublicPolicy=true,RestrictPublicBuckets=true
````

* Enabled Static website hosting

[<img src="https://i.imgur.com/hkGsyTc.png">](https://i.imgur.com/hkGsyTc.png)

* Bucket policy:
````json
{
  "Version":"2012-10-17",
  "Statement":[
    {
      "Sid":"PublicRead",
      "Effect":"Allow",
      "Principal": "*",
      "Action":["s3:GetObject","s3:GetObjectVersion"],
      "Resource":["arn:aws:s3:::demo-cors-apigw/*"]
    }
  ]
}
````

[<img src="https://i.imgur.com/WjVdzdw.png">](https://i.imgur.com/WjVdzdw.png)
