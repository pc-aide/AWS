# Demo Basics

## Doc

## Acronym
* CW - CloudWatch


## Intro
* API Gateway:
    * Choose an API type: **Rest API**
    * RadioButton: New API
    * API name: Demo-API
    * Endpoint Type: Regional
* Create API
    

[<img src="https://i.imgur.com/PqnmBmV.png">](https://i.imgur.com/PqnmBmV.png)
[<img src="https://i.imgur.com/DC831y4.png">](https://i.imgur.com/DC831y4.png)
[<img src="https://i.imgur.com/RPFMhH2.png">](https://i.imgur.com/RPFMhH2.png)

* Actions\**Create Method**
    * GET

[<img src="https://i.imgur.com/F56Xox0.png">](https://i.imgur.com/F56Xox0.png)
[<img src="https://i.imgur.com/JXZ7I7j.png">](https://i.imgur.com/JXZ7I7j.png)

* CheckBox: Use Lambda Proxy integration

* Create new function:
    * RadioButton: Author from scratch
    * function name: Lambda-APIGW-Proxy
    * Runtime: Python
* Edit this code for our lambda:
````python
import json

def lambda_handler(event, context):
    body = "Test from Lambda!"
    statusCode = 200
    return {
        "statusCode": statusCode,
        "body": json.dumps(body),
        "headers":{
            "Content-Type": "application/json"
        }
    }
````
* Test:

[<img src="https://i.imgur.com/EdMNCsy.png">](https://i.imgur.com/EdMNCsy.png)

* API Gateway
    * Lambda function
* save

[<img src="https://i.imgur.com/HY2TNro.png">](https://i.imgur.com/HY2TNro.png)
[<img src="https://i.imgur.com/arjG0dz.png">](https://i.imgur.com/arjG0dz.png)
[<img src="https://i.imgur.com/9NuSUAv.png">](https://i.imgur.com/9NuSUAv.png)

* Lambda-APIGW-Proxy\Permissions
    * **Resource-based policy**

[<img src="https://i.imgur.com/EBY0n9k.png">](https://i.imgur.com/EBY0n9k.png)
[<img src="https://i.imgur.com/cNahWHk.png">](https://i.imgur.com/cNahWHk.png)

* API Gateway\**Test**
    * Test

[<img src="https://i.imgur.com/ccVV9qe.png">](https://i.imgur.com/ccVV9qe.png)
[<img src="https://i.imgur.com/w2HXgtq.png">](https://i.imgur.com/w2HXgtq.png)
[<img src="https://i.imgur.com/8euI58g.png">](https://i.imgur.com/8euI58g.png)

* Request
    * Status: 200
    * Body
    * Headers
    
* Add "print(evnet) to code lambda before the body:
````python
import json

def lambda_handler(event, context):
    print(event)
    body = "Test from Lambda!"
    statusCode = 200
    return {
        "statusCode": statusCode,
        "body": json.dumps(body),
        "headers":{
            "Content-Type": "application/json"
        }
    }
````

* API Gateway\Test again

[<img src="https://i.imgur.com/1rgKxxo.png">](https://i.imgur.com/1rgKxxo.png)

* Lambda\view logs in CW\log stream
    * statements
````log
{'resource': '/', 'path': '/', 'httpMethod': 'GET', 'headers': None, 'multiValueHeaders': None, 'queryStringParameters': None, 'multiValueQueryStringParameters': None, 'pathParameters': None, 'stageVariables': None, 'requestContext': {'resourceId': 'hl8rj16jp9', 'resourcePath': '/', 'httpMethod': 'GET', 'extendedRequestId': 'UbRTPFZ2IAMF_KA=', 'requestTime': '15/Oct/2020:00:19:58 +0000', 'path': '/', 'accountId': '427263915585', 'protocol': 'HTTP/1.1', 'stage': 'test-invoke-stage', 'domainPrefix': 'testPrefix', 'requestTimeEpoch': 1602721198254, 'requestId': 'fae0d477-9524-4717-b286-d14784afd775', 'identity': {'cognitoIdentityPoolId': None, 'cognitoIdentityId': None, 'apiKey': 'test-invoke-api-key', 'principalOrgId': None, 'cognitoAuthenticationType': None, 'userArn': 'arn:aws:iam::427263915585:user/Paul', 'apiKeyId': 'test-invoke-api-key-id', 'userAgent': 'aws-internal/3 aws-sdk-java/1.11.848 Linux/4.9.217-0.3.ac.206.84.332.metal1.x86_64 OpenJDK_64-Bit_Server_VM/25.262-b10 java/1.8.0_262 vendor/Oracle_Corporation', 'accountId': '427263915585', 'caller': 'AIDAWG6XJ6ZASQMYJ3QHN', 'sourceIp': 'test-invoke-source-ip', 'accessKey': 'ASIAWG6XJ6ZA7PS4VNHA', 'cognitoAuthenticationProvider': None, 'user': 'AIDAWG6XJ6ZASQMYJ3QHN'}, 'domainName': 'testPrefix.testDomainName', 'apiId': 'ps7zttc39h'}, 'body': None, 'isBase64Encoded': False}
````
    
[<img src="https://i.imgur.com/UG25R83.png">](https://i.imgur.com/UG25R83.png)

* Create second mehtod:
    * Actions\**Create resource**
      * Resource name: houses
* Create resource

[<img src="https://i.imgur.com/YFq2PIP.png">](https://i.imgur.com/YFq2PIP.png)
[<img src="https://i.imgur.com/T96SwL3.png">](https://i.imgur.com/T96SwL3.png)
