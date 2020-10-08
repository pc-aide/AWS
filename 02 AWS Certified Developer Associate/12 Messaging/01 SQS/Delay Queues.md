# Delay Queues

## Acronym
* SQS - Simple Queue Service

## Doc
* [What is Amazon Simple Queue Service?](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html)

## Intro 
* Delay a message (consumers don't see it immediately) up to 15 minutes
* Default is 0 seconds (message is available right away)
* Can set a default at queue level
* Can overrride the default on send using the **DelaySeconds** parameter

### Diagram
[<img src="https://i.imgur.com/mAgIKMV.png">](https://i.imgur.com/mAgIKMV.png)

---

## Demo
* SQS\create queue
    * Name: Demo-Delay-Queue
    * Delivery delay: 15s
    
[<img src="https://i.imgur.com/HtXqK3k.png">](https://i.imgur.com/HtXqK3k.png)

* Demo-Delay-Queue\send & receive messages
* Message body: random message
* poll for messages

[<img src="https://i.imgur.com/kBZo5Er.png">](https://i.imgur.com/kBZo5Er.png)

* send message
* poll for message
* we need to wait 15s before to see this message in our queue

[<img src="https://i.imgur.com/HhNA1Yr.png">](https://i.imgur.com/HhNA1Yr.png)
[<img src="https://i.imgur.com/t1EOwnG.png">](https://i.imgur.com/t1EOwnG.png)
