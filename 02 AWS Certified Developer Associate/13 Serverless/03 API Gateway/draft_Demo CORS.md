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

* Browser
      * 403 Forbidden

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

* test brwoser
      * 404 not found
      
[<img src="https://i.imgur.com/8JMlvsO.png">](https://i.imgur.com/8JMlvsO.png)      

* index.html:
````html
<html>
    <head>
        <title>CORS Demo API Gateway</title>
    </head>
    <body>
        <h1>Making a CORS request to API Gateway...</h1>
        <div id="tofetch"/>
    </body>


    <!-- CORS demo -->
    <script>
       <!-- tofetch: GET house (prod) -->
        var tofetch = document.getElementById("tofetch");

        fetch('https://ps7zttc39h.execute-api.us-east-1.amazonaws.com/PROD/houses')
        .then((response) => { 
            return response.text();
        })
        .then((html) => {
            tofetch.innerHTML = html     
        });
    </script>
</html>
````

[<img src="https://i.imgur.com/kKzVqDX.png">](https://i.imgur.com/kKzVqDX.png)
[<img src="https://i.imgur.com/Oud0Fsl.png">](https://i.imgur.com/Oud0Fsl.png)

* AWS CLI
````bash
aws s3 cp index.html s3://demo-cors-apigw
````
[<img src="https://i.imgur.com/vYV0Aze.png">](https://i.imgur.com/vYV0Aze.png)

* Browser mode DEV
      * Access to fetch at ... from oriing has been blocked by CORS
      * API Gateway gives a content
      * we need CORS for API Gateway

[<img src="https://i.imgur.com/5H3sowc.png">](https://i.imgur.com/5H3sowc.png)
[<img src="https://i.imgur.com/hlU1eql.png">](https://i.imgur.com/hlU1eql.png)

* API Gateway\Resources\
      * /house\Actions\**Enable CORS**
         * Access-Control-Allow-Origin: <domainS3> - * for anydomain
            * 'http://demo-cors-apigw.s3-website-us-east-1.amazonaws.com/'
      
[<img src="https://i.imgur.com/S4f5u2p.png">](https://i.imgur.com/S4f5u2p.png)
[<img src="https://i.imgur.com/RlmYWt4.png">](https://i.imgur.com/RlmYWt4.png)
[<img src="https://i.imgur.com/FcK2PPx.png">](https://i.imgur.com/FcK2PPx.png)
[<img src="https://i.imgur.com/97UPZwd.png">](https://i.imgur.com/97UPZwd.png)

* options - was created

[<img src="https://i.imgur.com/GjsxKB3.png">](https://i.imgur.com/GjsxKB3.png)

* deploy api
      * Deployment stage: prod
      
[<img src="https://i.imgur.com/Pk2ZUG6.png">](https://i.imgur.com/Pk2ZUG6.png)
[<img src="https://i.imgur.com/k3zWZig.png">](https://i.imgur.com/k3zWZig.png)

* browser
      * invoke url (stage: prod) - still working
      * S3.website - no working
      
[<img src="https://i.imgur.com/5GhdSoH.png">](https://i.imgur.com/5GhdSoH.png)
[<img src="https://i.imgur.com/zKzyyD6.png">](https://i.imgur.com/zKzyyD6.png)

* States\house\GET\Enable CORS
      * Access-Control-Allow-Origin: '*'
      
[<img src="https://i.imgur.com/yKAShYe.png">](https://i.imgur.com/yKAShYe.png)
[<img src="https://i.imgur.com/2b2iFpf.png">](https://i.imgur.com/2b2iFpf.png)

* deploy api
      * deployment stage: prod
      * wait a little bit, F5 browser - still no working
      
[<img src="https://i.imgur.com/S1FPXku.png">](https://i.imgur.com/S1FPXku.png)

*  Resources
      * /mapping
    
      
[<img src="https://i.imgur.com/yFtmrBr.png">](https://i.imgur.com/yFtmrBr.png)
[<img src="https://i.imgur.com/i5u3MEJ.png">](https://i.imgur.com/i5u3MEJ.png)

* Lambda-APIGW-Proxy-House-GET\
      * edit code for allow 'Access-Control-Allow-Origin'
````json
import json

def lambda_handler(event, context):
    body = "Test from house!"
    statusCode = 200
    return {
        "statusCode": statusCode,
        "body": json.dumps(body),
        "headers":{
            "Content-Type": "application/json",
            'Access-Control-Allow-Origin': '*'
        }
    }

````

* F5 Browser - working

[<img src="https://i.imgur.com/eQs95Am.png">](https://i.imgur.com/eQs95Am.png)
