# API Gateway

## Acronym
* CRUD - Create/Read/Update/Delete
* SQS - Simple Queue Service
* ENI - Elastic Network Interface

## Doc

## Example: Building a Serverless API
[<img src="https://i.imgur.com/gmRWOAP.png">](https://i.imgur.com/gmRWOAP.png)

---

## API Gateway
* Lambda + API Gateway: No infrastructure to manage
* Support for the WebSocket Protocol
* Handle API versioning (v<sub>1</sub>, v<sub>2</sub>..., v<sub>n<sub>)
* Handle different environment (dev, test, prod...)
* Handle security (Authentication & Authorization) 
* Create API Key, handle request throttling
* Swagger/Open API import to quickly define APIs
* Transform & validate requests & responses
* Generate SDK & API specifications

---

## Integration High Level
* Lambda Function
    * Invoke Lambda function
    * Easy way to expose REST API backed by AWS Lambda
* HTTP
    * Expose HTTP endpoints in the backend
    * Example: internal HTTP API on premise, ALB...
    * Why? Add rate limiting, caching, user authentications, API keys, etc...
* AWS Service
    * Expose any AWS API through the API Gateway?
    * Example: start an AWS Step Function workflow, post a message to SQS
    * Why? Add authentication, deploy publicly, rate control...   
    
---

## Endpoint Types
1) **Edge-Optimized (default)**: For global clients
    * Requests are routed through the CloudFront Edge location (improves latency)
    * The API Gateway still lives in only one region
2) Regional:
    * For clients within the same region
    * Cloud manually combine with CloudFront (more control over the caching stategies & the distribution)
3) Private:
    * Can only be accessed from your VPC using an interface VPC endpoint (ENI)
    * Use a resource policy to define access
