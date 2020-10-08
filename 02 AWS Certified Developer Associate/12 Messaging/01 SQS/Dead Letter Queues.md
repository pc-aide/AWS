# Dead Letter Queues

## Acronym
* DLQ - Dead Letter Queue
* SQS - Simple Queue Service
* Cfg - Configuration

## Doc
* [SetQueueAttributes](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/APIReference/API_SetQueueAttributes.html)
* [Configuring a dead-letter queue (console)](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-configure-dead-letter-queue.html)

## Intro
* If a consumer fails to process a message within the Visibility Timeout...
    * the message goes back to the queue!
* We can set a threshold of how many times a message can go back to the queue
* After the **MaximumReceives** threshold is exceeded, the message goes into a dead letter queue (DLQ)
* Useful for <ins>debugging</ins>
* Make sure to process the messages in the DLQ before they expire:
    * Good to set a retention of 14 days i nthe DLQ
    
### Diagram
[<img src="https://i.imgur.com/f5grbOW.png">](https://i.imgur.com/f5grbOW.png)

---

## Demo
* SQS\Create queue (DLQ)
* Detail
    * Name: Demo-DLQ
* Cfg
    * Message retention period: 14 days
* Create queue
    
[<img src="https://i.imgur.com/dlyfioB.png">](https://i.imgur.com/dlyfioB.png)
[<img src="https://i.imgur.com/lxzaB8e.png">](https://i.imgur.com/lxzaB8e.png)

* Queues:

[<img src="https://i.imgur.com/IWyXxnG.png">](https://i.imgur.com/IWyXxnG.png)

* Setup 1st queue (Demo-SQS):
* Edit:
* cfg
    * Visibility timeout: 5s (for demo)
* Dead-letter queue: Enabled
* Queue ARN: Demo-DLQ
* Maximum receives: 3 (for demo)
    
[<img src="https://i.imgur.com/cc7Ztd6.png">](https://i.imgur.com/cc7Ztd6.png)
[<img src="https://i.imgur.com/6eWrEde.png">](https://i.imgur.com/6eWrEde.png)

* Demo-SQS\Send & receive message:
* Message body: this a test from Demo-SQS - we can said too another word to explain the crash for example
* poll for messages

[<img src="https://i.imgur.com/T5DQgbV.png">](https://i.imgur.com/T5DQgbV.png)
[<img src="https://i.imgur.com/d2ANxZW.png">](https://i.imgur.com/d2ANxZW.png)

* Demo-DLQ\poll for messages
* Message body

[<img src="https://i.imgur.com/ORQHgf9.png">](https://i.imgur.com/ORQHgf9.png)
[<img src="https://i.imgur.com/kglxpDT.png">](https://i.imgur.com/kglxpDT.png)
