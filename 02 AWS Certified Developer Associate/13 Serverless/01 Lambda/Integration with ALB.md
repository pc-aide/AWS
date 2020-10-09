# Integration with ALB

## Acronym
* ALB - Application Load Balancer
* TG - Target Group

## Doc

## Intro
* To expose a Lambda function as an HTTP(s) endpoint...
* You can use the **ALB** (or an API Gateway)
* The Lambda function must be registered in a **TG**

### Diagram
[<img src="https://i.imgur.com/lzVCzwZ.png">](https://i.imgur.com/lzVCzwZ.png)

---

## ALB to Lambda: HTTP to JSON
* Request Payload for Lambda Function
* example.json:
    * ELB information (ln 3)
    * HTTP Method & path (ln 7..8)
    * **Query String Parameters as Key/value pairs** (Ln 10)
    * **Headers as Key/Value pairs** (Ln 12)
    * **Body (for POUST, PUT, HEAD, ...) & isBase64Encoded** (Ln 21)
````json
{
    "reuestContext": {
        "elb": {
            "targetGroupArn": "arn:aws:elasticloadbalancing:us-east-2:1249e9d65c45c6791s"
        }
    },
    "httpMethod": "GET",
    "path": "/lambda",
    "queryStringParameters": {
        "query": "1234ABCD"
    },
    "headers": {
        "connection": "keep-alive",
        "host": "lambda-alb-123578498.us-east-2.elb.amazonaws.com",
        "user-agent": "Mozilla/5.0 (Windows NT 10.0; win64; x64) AppleWeb; Safari/537.36",
        "x-amzn-trace-id": "Root=1-5c536348-3d683b8b04734faae651f476",
        "x-forwarded-for": "72.12.164.125",
        "x-forwarded-port": "80",
        "x-forwarded-proto": "http",
    },
    "body": "",
    "isBase64Encoded": false
}
````

---

## Lambda to ALB conversions: json to HTTP
* Response from the Lambda Function
    * Status Code & description
    * Headers as Key/Value
    * body & isBase64Encoded
````json
{
    "statusCode": 200,
    "statusDescription": "200 OK",
    "headers": {
        "Content-Type": "text/html; charset=utf-8"
    },
    "body": "<h1>Hello world!</h1>",
    "isBase64Encoded": false
}
````

---

## ALB Multi-Header Values
* ALB can support multi header values (ALB setting)
* When you enable multi-value headers, **HTTP headers & query string parameters** that are sent with **multiple values**
  are shown **as arrays** within the Lambda event & response objects

### Diagram
[<img src="https://i.imgur.com/jObpeLZ.png">](https://i.imgur.com/jObpeLZ.png)
