# SQS

## Acronym
* SQS - Simple Queue Service
* Std - Standard
* RDS - Relational Database Service
* DB - Database
* ASG - Auto-Scaling Group
* IAM - Identity & Access Management

## Doc

## What's a queue?
[<img src="https://i.imgur.com/PD7If3O.png">](https://i.imgur.com/PD7If3O.png)

---

## Std Queue
* Oldest offering (over 10 years old)
* Fully managed service, used to **decouple applications**
* Attributes:
    * Unlimited throughput, unlimited number of messages in queue
    * Default retention of messages: 4 days, maximum of 14 days
    * Low latency (<10 ms on publish & receive)
    * Limitation of 256 KB per message sent
* Can have duplicate messages (at lest once delivery, occasionally)
* Can have out of order messages (best effort ordering)

---

## SQS - Producing Messages
* Produced to SQS using the SDK (SendMessage API)
* The message is **perisisted** in SQS until a consumer deletes it
* Message retention: default 4 days, up to 14 days
* Example: send order to be processed
    * Order id
    * Customer id
    * Any attributes you want
* SQS std: unlimited throughput

### Diagram
[<img src="https://i.imgur.com/Z56UWbX.png">](https://i.imgur.com/Z56UWbX.png)

---

## SQS - Consuming Messages
* Consumers (running on EC2 instances, servers, or AWS Lambda)...
* Poll SQS for messagers (receive up to 10 messages at a time)
* Process the messages (example: insert the message into an RDS db)
* Delete the messages using the DeleteMessage API

### Diagram
[<img src="https://i.imgur.com/YS40SHO.png">](https://i.imgur.com/YS40SHO.png)

---

## SQS - Multiple EC2 Instances Consumers
* Consumers receive & process messages in parallel
* At least once delivery
* Best-effort message ordering
* Consumers delete messages after processing them
* We can scale consumers horizontally to improve throughput of processing

### Diagram
[<img src="https://i.imgur.com/kUctK9G.png">](https://i.imgur.com/kUctK9G.png)

---

## SQS with ASG
[<img src="https://i.imgur.com/Noa2GMO.png">](https://i.imgur.com/Noa2GMO.png)

---

## SQS to decouple between application tiers 
[<img src="https://i.imgur.com/aXzvsN9.png">](https://i.imgur.com/aXzvsN9.png)

---

## SQS - Security
* Encryption:
      * In-flight encryption using HTTPS API
      * At-rest encryption using KMS keys
      * Client-side encryption if the client wants to perform encryption/decryption itself
* **Access Controls**: IAM policies to regulate access to the SQS API
* **SQS Access Policies** (similar to S3 bucket policies)
      * Useful for corss-account access to SQS queues
      * Useful for allowing other service (SNS, S3...) to write to an SQS queue
