# FIFO Queues

## Acronym
* FIFO - First In First Out (ordering of messages in the queue)

## Doc
* [Amazon SQS FIFO (First-In-First-Out) queues](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html)

## Intro
* FIFO
* Limited throughput: 300 msg/s without batcing, 3000 msg/s with
* Exactly-once send capability (by removing duplicates)
* Messages are processed in order by the consumer

### Diagram
[<img src="https://i.imgur.com/yJlNqf7.png">](https://i.imgur.com/yJlNqf7.png)

---

## Demo
* create queue
* Type: FIFO
* Name: Demo.fifo
    * Note: You have to end it with "dot" fifo otherwise, you will not have the ability to create this queue
* Create queue

[<img src="https://i.imgur.com/KLcxaC8.png">](https://i.imgur.com/KLcxaC8.png)
[<img src="https://i.imgur.com/01xy32B.png">](https://i.imgur.com/01xy32B.png)

* Send & receive messages
* Message body: this is a test for fifo 1
* Message group id: demo
* Message deduplication ID: 1
* Send message

[<img src="https://i.imgur.com/K6a4u88.png">](https://i.imgur.com/K6a4u88.png)

* just increment the number (message body & Message deduplication ID):
* stop at the number 4

[<img src="https://i.imgur.com/kPflAmj.png">](https://i.imgur.com/kPflAmj.png)
[<img src="https://i.imgur.com/KxTwqM0.png">](https://i.imgur.com/KxTwqM0.png)

* Receive messages:
* Poll for messages

[<img src="https://i.imgur.com/0gMQfeX.png">](https://i.imgur.com/0gMQfeX.png)
[<img src="https://i.imgur.com/7pFl5li.png">](https://i.imgur.com/7pFl5li.png)

* check first message ID:

[<img src="https://i.imgur.com/ACDfDz6.png">](https://i.imgur.com/ACDfDz6.png)

* check bottom one message ID:
* second botton message ID:

[<img src="https://i.imgur.com/lneWZZk.png">](https://i.imgur.com/lneWZZk.png)
[<img src="https://i.imgur.com/LgOzO2W.png">](https://i.imgur.com/LgOzO2W.png)
