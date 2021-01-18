# SQS

## Acronym
* SQS - Simple Queue Service
* DLQ - Dead Letter Queue
* ASG - Auto Scaling Group
* FIFO - First In, First Out
* IAM - Identity & Access Management

## Intro
* SQS was the very first service offered by AWS
* Serverless, managed queue, integrated with IAM
* Can handle extreme scale, no provisioning required
* Used to **decouple** services
* Message size of max 256KB (use a pointer to S3 for large messages)
* Can be read from EC2 (optional ASG), Lambda
* SQS could be used as write buffer for DynamoDB
* SQS FIFO:
  * receive messages in order they were sent
  * 300 messages/s without batching, 3k/s with batching
* No requirement of message brokers
  
---

## Queues
1) Standard
2) FIFO

### Diagram

[<img src="https://i.imgur.com/TMoMj6f.png">](https://i.imgur.com/TMoMj6f.png)
  
---

## Solution Architecture Idempotency
* Messages can processed twice by consumer (in case of failures, timeouts, etc)
* to hedge against that problem, implement **idempotency** at the consumer level
* Idempotency:
  * Means the same action done twice by the consumer won't duplicate the effect
  
### Diagram
[<img src="https://i.imgur.com/opP8ye9.png">](https://i.imgur.com/opP8ye9.png)

---

## Lambda - Event Source Mapping SQS & SQS FIFO
* Event Source Mapping will poll SQS (Long Polling)
* Specify **batch size** (1-10 messages)
* Recommended: Set the queue visibility temout to 6x the timeout of your Lambda function
* To use a **DLQ**:
  * set-up on the SQS queue, not Lambda (DLQ for Lambda is only for **asyn invocation**)
  * Or use a Lambda destination for failures

### Diagram
[<img src="https://i.imgur.com/n96KLUR.png">](https://i.imgur.com/n96KLUR.png)

---

## Solution Architecture | Request/Response queue (async)
* Decoupling
* Fault-Tolerance
* Load Balancing

### Diagram
[<img src="https://i.imgur.com/xjYpJDL.png">](https://i.imgur.com/xjYpJDL.png)

---

## Visibility Timeout
* Receiving a message simply **hides** it based on this **visibility time out**
* E.g visibilit Timeout (value):
 * 0 - never hide (min)
 * 12h - 12h to wait before to see the message

### Diagram
[<img src="https://i.imgur.com/1IX7wKW.png">](https://i.imgur.com/1IX7wKW.png)

---

## Queue Attributes 
* Retention
  * Number of days before the message will be delete forever
  * Min: 1m
  * Max: 14d
* Maximum Message Size
  * Min: 1KB
  * Max: 256KB
* Receive message Wait Time
  * 0 = Short Polling
  * 1-20 = Long Polling
  
### Diagram
[<img src="https://i.imgur.com/57J9rtr.png">](https://i.imgur.com/57J9rtr.png)

* Other e.g.

[<img src="https://i.imgur.com/HLKOXbP.png">](https://i.imgur.com/HLKOXbP.png)
