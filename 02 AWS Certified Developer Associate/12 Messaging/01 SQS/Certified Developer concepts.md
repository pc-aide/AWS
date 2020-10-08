# Certified Developer concepts

## Acronym
* SQS - Simple Queue Service

## Doc
* [What is Amazon Simple Queue Service?](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html)

## SQS - Long Polling
* When a comsumer requests messages fro mthe queue, it can optionally "wait" for messages to arrive if there
  none in the queue
* This is called Long Polling
* **LongPolling** decreases the number of API calls made to SQS while increasing the efficiency & latency
  of your application
* The wait time can be between 1sec to 20sec (20 sec preferable)
* Long Polling is preferable to Short Polling
* Long polling can be enabled at the queue level or at the API level using **WaitTimeSeconds**

### Diagram
[<img src="https://i.imgur.com/dp2yP4x.png">](https://i.imgur.com/dp2yP4x.png)

---

## SQS Extended Client
* Message size limit is 256 KB, how to send large messages, e.g. 1GB?
    * example: a video file
* Using the SQS Extended Client(Java Library)

### Diagram
[<img src="https://i.imgur.com/lRr8ayx.png">](https://i.imgur.com/lRr8ayx.png)

---

## SQS - Must know API
* CreateQueue (MessageRetentionPeriod), DeleteQueue
* PurgeQueue: delete all the message in queue
* SendMessage (DelaySeconds), ReceiveMessage, DeleteMessage
* ReceiveMessageWaitTimeSeconds: Long Polling
* ChangeMessageVisibility: change the message timeout
* Batch APIs for **SendMessage, DeleteMessage, ChangeMessageVisibility** helps decrease your costs

---

## Demo
* Edit SQS\Demo-SQS
* Receive message wait time: 20 sec
    * we need to wait 20s if the queue is empty for new message

[<img src="https://i.imgur.com/UthwyCp.png">](https://i.imgur.com/UthwyCp.png)

* Send & receive messages
* Poll for messages (ahead & start a **consumer**)
* message body: long polling
* send message

[<img src="https://i.imgur.com/ZuXXaOE.png">](https://i.imgur.com/ZuXXaOE.png)
[<img src="https://i.imgur.com/xUr2ei8.png">](https://i.imgur.com/xUr2ei8.png)
