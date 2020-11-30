# API Gateway

## Acronym
* CRUD - Create,Read,Update, & Delete operation in a DB
* CORS - Cross-Origin Resource Sharing
* SQS - Simple Queue Service

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
