# API Gateway

## Acronym
* CRUD - Create,Read,Update, & Delete operation in a DB
* CW - CloudWatch
* CORS - Cross-Origin Resource Sharing
* IAM - Identity & Access Management
* IAM - Identity & Access Management
* CIDR - Classless Inter-Domain Routing
* SSL - Secure Sockets Layer
* TTL - Time To Live
* CORS - Cross-Origin Resource Sharing
* SQS - Simple Queue Service
* WAF - Web Application Firewall
* ENI - Elatic Network Interface

## Intro
* Helps expose Lambda, HTTP & AWS Services as an API
* API versioning, authorization, traffic management (API keys, throttles), huge scale, serverless, req/resp transformations, OpenAPI spec, CORS
* **Limits** to know:
  * 29 sec timeout
  * 10MB max payload size

### Diagram
[<img src="https://i.imgur.com/IMku6LQ.png">](https://i.imgur.com/IMku6LQ.png)

---

## Deployment Stages
* API changes are deployed to "Stages" (as many as you want)
* Use the naming you like for stages (dev,test,prod)
* Stages can be rolled back as a history of deployments is kept

### Diagram
[<img src="https://i.imgur.com/brVpDLr.png">](https://i.imgur.com/brVpDLr.png)

---

## Integrations
* HTTP
  * Expose HTTP endpoints in the backend
  * Example: internal HTTP API on premise, ALB...
  * Why? Add rate limiting, caching, user authentications, API keys, etc..
* Lambda Function
  * Invoke Lambda function
  * Easy way to expose REST API backed by Lambda
* AWS Service
  * Expose any AWS API through the API Gateway?
  * Example: start an AWS Step Function workflow, post a message to SQS
  * Why? Add authentication, deploy publicly, rate control...
  
---

## API Gateway in front of S3
* You will be impacted by the **10MB payload size limit**

### Diagram
[<img src="https://i.imgur.com/4Z52Kjs.png">](https://i.imgur.com/4Z52Kjs.png)

---

## Endpoint Types
* Edge-Optimized (default): For global clients
  * Requests are routed through the CloudFront Edge locations (improves latency)
  * The API Gateway still lives in only one region
* Regional:
  * For clients within the same region
  * Cloud manually combine with CloudFront (more control over the caching strategies & the distribution)
* Private:
  * Can only be accessed from your VPC using an interface VPC endpoint (ENI)
  * Use a resource policy to define access
  
---

## Caching API responses
* Caching reduces the number of calls made to the backend
* Default **TTL** is 300 seconds (min:0s,  max 3600s)
* Caches are defined **per stage**
* Possible to override cache settings **per method**
* Clients can invalidate the cache with headers:
  * **Cache-Control:max-age=0** (with proper IAM authorization)
* Able to flush the entire cache (invalidate it) immediately
* Cache encryption option
* Cache capacity between 0.5GB to 237GB

### Diagram
[<img src="https://i.ibb.co/ckx5M3S/image.png">](https://i.ibb.co/ckx5M3S/image.png)

---

## Erros
* 4xx means **Client** Errors
  * 400: Bad Request
  * 403: Forbidden, Access Denied, WAF filtered
  * 404: Not Found
  * 429: Quota exceeded, Throttle
* 5xx means **Server** Errors
  * 502: Bad Gateway
    * Exception, usually for an incompatible output returned from a Lambda proxy integration backend & occasionally for out-of-order invocations due to heavy loads
  * 503: Service Unavailable
  * 504: Integration Failure
    * ex Endpoint Request Timed-out Exception, **API Gateway reqeusts time out after 29s maximum**
    
---

## Security
* Load SSL certificates & use Route 53 to define a CNAME
* Resource Policy (~S3 Bucket Policy):
  * control who can access the API
  * Users from AWS accounts, IP or CIDR blocks, VPC or VPC Endpoints
* IAM Execution Roles for API Gateway at the API level
  * To invoke a Lambda Function, an AWS service...
* CORS:
  * Browser based security
  * Control which domains can call your API
  
---

## Authentication
1) IAM based access
  * Good for providing access within your own infrastructure
  * Pass IAM credentials in headers through SigV4
2) Lambda Authrorizer (formerly Custom Authorizer)
  * Use Lambda to verify a custom OAuth/SAML/3<sup>rd</sup> party authentication
3) Cognito User Pools
  * Client authenticates with Cognito
  * Client passes the token to API Gateway
  * API Gateway knows out-of-the-box how to verify to token
  
### Diagram
[<img src="https://i.ibb.co/VwCxTzM/image.png">](https://i.ibb.co/VwCxTzM/image.png)

---

## Logging, Monitoring, Tracing
* CloudWatch Logs:
  * Enable CloudWatch logging at the Stage level (with Log Level - ERROR, INFO)
  * Can log full requests/responses data
  * Can send API Gateway Access Logs (customizable)
  * Can send logs directly into Kinesis Data Firehose (as an alternative to CW logs)
* CW Metrics:
  * Metrics are by stage, possibility to enable detailed metrics
  * IntegrationLatency, Latency, CacheHitCount, CacheMissCount
* X-Ray:
  * Enable tracing to get extra information about requests in API Gateway
  * X-Ray API Gateway + Lambda gives you the full picture
