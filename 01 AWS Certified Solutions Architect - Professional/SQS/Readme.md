# SQS

## Acronym
* SQS - Simple Queue Service
* DLQ - Dead Letter Queue
* ASG - Auto Scaling Group
* FIFO - First In, First Out
* IAM - Identity & Access Management

## Intro
* Serverless, managed queue, integrated with IAM
* Can handle extreme scale, no provisioning required
* Used to **decouple** services
* Message size of max 256KB (use a pointer to S3 for large messages)
* Can be read from EC2 (optional ASG), Lambda
* SQS could be used as write buffer for DynamoDB
* SQS FIFO:
  * receive messages in order they were sent
  * 300 messages/s without batching, 3k/s with batching
  
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
