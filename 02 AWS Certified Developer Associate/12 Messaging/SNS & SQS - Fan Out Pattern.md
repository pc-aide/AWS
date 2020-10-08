# SNS & SQS - Fan Out Pattern

## Doc

## Acronym
* SNS - Simple Notification Service
* SQS - Simple Queue Service
* FIFO - First In First Out
* S3 - Simple Storage Service

## Intro
* Push once in SNSn receive in all SQS queues that are subscribers
* Fully decoupled, no data loss
* SQS allows for: data persistence, delayed processing & retires of work
* Ability to add more SQS subscribers over time
* Make sure your SQS queue **access policy** allows for SNS to write
* <ins>SNS cannot send messages to SQS FIFO queues (AWS limitation)</ins>

[<img src="https://i.imgur.com/PTVjKKM.png">](https://i.imgur.com/PTVjKKM.png)

### Diagram
[<img src="https://i.imgur.com/0ZXIzgw.png">](https://i.imgur.com/0ZXIzgw.png)

---

## Application: S3 Events to multiple queues
* For the same combination of: **event type** (e.g. object create) & **prefix** (e.g. images/) you can only have <ins>one S3 Event rule</ins>
* If you want to send the same S3 event to many SQS queues, use fan-out

### Diagram
[<img src="https://i.imgur.com/6ZvrfNh.png">](https://i.imgur.com/6ZvrfNh.png)
