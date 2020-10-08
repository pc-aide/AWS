# Synchronous Invocations

## Doc

## Acronym
* ALB - Application Load Balancer
* ELB (Elastic Load Balancer)

## Intro
* Synchronous: CLI, SDK, API Gateway, ALB
    * Results is returned righ away
    * Error handling must happen client side (retries, exponential backoff, etc...)
    
### Diagram
[<img src="https://i.imgur.com/SWLxgo3.png">](https://i.imgur.com/SWLxgo3.png)

---

## Synchronous Invocations - Services
* User Invoked:
    * ELB (ALB)
    * API Gateway
    * CloudFront (Lambda@Edge)
    * S3 Batch
* Service Invoked:
    * Cognito
    * Step Functions
* Other Services:
    * Lex
    * Alexa
    * Kinesis Data Firehose
