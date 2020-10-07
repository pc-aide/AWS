# X-Ray

## Doc

## Acronym
* CW - CloudWatch
* SLA - Service-Level Agreement
* EB - Elastic Beanstalk
* ECS - Elastic Container Service
* ELB - Elastic Load Balancer
* IAM - Identity & Access Management
* KMS - Key Management Service
* SQS - Simple Queue Service

## Intro
* Debugging in Production, the good old way:
    * Test locally
    * Add log statements everywhere
    * Re-deploy in production
* Log formats differ across application using CW & analytics is hard
* Debuggin: monolith "easy", distributed services "hard"
* No common views of your entire architecture


---

## X-Ray - Visual analysis of our applications
[<img src="https://i.imgur.com/gzV0btG.png">](https://i.imgur.com/gzV0btG.png)

---

## Advantages
* Troubleshooting performance (bottlenecks)
* Understand dependencies in a microservice architecture
* Pinpoint service issues
* Review request behavior
* Find errors & exceptions
* Are we meeting time SLA?
* Where I am throttled?
* Identify users that are impacted

---

## Compatibility
* Lambda
* EB
* ECS
* ELB
* API Gateway
* EC2 Instances or any application server (even on premise)

---

## Leverages Tracing
* Tracing is an end to end way to following a "request"
* Each component dealing with the request adds its own "trace"
* Tracing is mage of segments (+ sub segments)
* Annotations can be added to traces to provide extra-information
* Ability to trace:
    * Every request
    * Sample reuest (as a % for example or a rate per minute)
* X-Ray Security:
    * IAM for authorization
    * KMS for encryption at rest
    
---

## How to enable it?
1) Your code (Java, Python, Go, Node.js, .NET) must import the AWS X-Ray SDK
    * Very little code modification needed
    * The application SDK will then capture:
      * Calls to AWS services
      * HTTP/HTTPS requests
      * Database Calls (MySQL, PostreSQL, DynamoDB)
      * Queue call (SQL)
2) Install the X-Ray daemon or enable X-Ray AWS Integration
    * X-Ray daemon works as a low level UDP packet interceptor
      * Linux/Windows/Mac
    * Lambda / other AWS service already run the X-Ray daemon for you
    * Each application must have the IAM rights to write data to X-Ray
    
### Diagram
[<img src="https://i.imgur.com/ZicRrNG.png">](https://i.imgur.com/ZicRrNG.png)

---

## Magic
 * X-Ray service collects data from all the different service
 * Service map is computed from all the segments & traces
 * X-Ray is graphical, os even non technical people can help troubleshoot
 
 ### Diagram
 [<img src="https://i.imgur.com/Ejjkgmm.png">](https://i.imgur.com/Ejjkgmm.png)
 
 ---
 
 ## Troubleshooting
 * If X-Ray is not working on EC2
    * Ensure the EC2 IAM Role has the proper permissions
* To enable on Lambda:
    * Ensure it has an IAM execution role iwth proper policy (AWSX-RayWriteOnlyAccess)
    * Ensure that X-Ray is imported in the code
