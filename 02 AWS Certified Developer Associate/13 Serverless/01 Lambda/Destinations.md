# Destinations

## Doc
* [Asynchronous invocation](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html)
* [AWS Lambda event source mappings](https://docs.aws.amazon.com/lambda/latest/dg/invocation-eventsourcemapping.html)

## Acronym
* SQS - Simple Queue Service
* SNS - Simple Notification Service
* DLQ - Dead Letter Queue

## Intro
* Nov 2019: can configure to send result to a **destination** (New feature)
* **Asynchronous invocations** - can define destinations for successful & failed event:
    * SQS
    * SNS
    * Lambda
    * EventBridge bus
* Note: AWS recommends you use destinations instead of DLQ now (but both can be used at the same time)
* **Event Source mapping**: for discarded event batches
    * SQS
    * SNS
* Note: you can send events to a DLQ directly from SQS
    
### Diagram
[<img src="https://i.imgur.com/dkZpnc9.png">](https://i.imgur.com/dkZpnc9.png)

[<img src="https://i.imgur.com/5srGVNp.png">](https://i.imgur.com/5srGVNp.png)
