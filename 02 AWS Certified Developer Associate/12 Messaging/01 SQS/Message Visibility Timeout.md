# Message Visibility Timeout

## Doc
* [What is Amazon Simple Queue Service?](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html)

## Acronym
* SQS - Simple Queue Service

## Intro
* After a message is polled by a consumer, it becomes **invisible** to other consumers
* By default, the "message visibility timeout" is **30 seconds**
* That means the message has 30 seconds to be processed
* After the messge visibility timeout is over, the message is "visible" in SQS

### Diagram
[<img src="https://i.imgur.com/TGAUzHq.png">](https://i.imgur.com/TGAUzHq.png)
[<img src="https://i.imgur.com/FeatCGJ.png">](https://i.imgur.com/FeatCGJ.png)

---

## SQS - Message Visibility Timeout
* If a message is not processed within the visibility timeout, it will be processed **twice** 
    * it will be received by two different consumers or twice by the same consumer
* A consumer could call the **ChangeMessageVisibility** API to get more time
* If visibility timeout is high (hours), & consumer crashes, re-processing will take time
* If visibility timeout is too low (seconds), we may get duplicates

### Diagram
[<img src="https://i.imgur.com/TGAUzHq.png">](https://i.imgur.com/TGAUzHq.png)

---

## Demo
* SQS\Send & receive messages:

* Message body: this is a test on (30s - polling duration)

[<img src="https://i.imgur.com/34F4arX.png">](https://i.imgur.com/34F4arX.png)

* Poll for messages (User01)
* note: open second onglet for simulate another user or the same user

[<img src="https://i.imgur.com/CCNdL9k.png">](https://i.imgur.com/CCNdL9k.png)

* Second User02:
* poll for message
* onto 30s - nothing
* after this timeout, twice the same message

[<img src="https://i.imgur.com/PWnccDV.png">](https://i.imgur.com/PWnccDV.png)
[<img src="https://i.imgur.com/iqpX7Yj.png">](https://i.imgur.com/iqpX7Yj.png)

* If want change the 30s timeout (visibility)
* edit
    * Visibility timeout:

[<img src="https://i.imgur.com/cfKOYvy.png">](https://i.imgur.com/cfKOYvy.png)
[<img src="https://i.imgur.com/6Td3o5s.png">](https://i.imgur.com/6Td3o5s.png)

* if you want that no other user see this message, just increase visibility timeout
