# FIFO Queues Advanced

## Acronym
* FIFO - First In First Out - ordering messages
* SQS - Simple Queue Service

## Doc

## SQS FIFO - Deduplication
* De-duplication interval is 5 minutes
* Two de-duplication methods:
    1) Content-based deduplication: will do a SHA-256 hash of the message body
    2) Explicitly provide a Message Deduplication ID
    
### Diagram
[<img src="https://i.imgur.com/C7HVfPS.png">](https://i.imgur.com/C7HVfPS.png)

---

## SQS FIFO - Message Grouping
* If you specify the same value of **MessageGroupID** in an SQS FIFO queue, you can only have one consumer, & all the 
  messages are in order
* To get ordering at the level of a subset of messages, specify different values for **MessageGroupID**
    * Messages that share a common Message Group ID will be in order within the group
    * Each Group ID can have a different consumer (parallel processing)
    * Ordering across groups is not guaranteed
    
### Diagram
[<img src="https://i.imgur.com/u76vrij.png">](https://i.imgur.com/u76vrij.png)

---

## Demo
* Go back to Demo.fifo  & Edit
* Enable: Content-based deduplication

[<img src="https://i.imgur.com/DundiWG.png">](https://i.imgur.com/DundiWG.png)

* Send & receive messages
* Message body: this is a test for content-based deduplication 1
* Message group ID: Demo
* Send message

[<img src="https://i.imgur.com/2rsec60.png">](https://i.imgur.com/2rsec60.png)

* if i send message again
* still one message in message id
* poll for message

[<img src="https://i.imgur.com/D4xyvkc.png">](https://i.imgur.com/D4xyvkc.png)
[<img src="https://i.imgur.com/YkKUZPA.png">](https://i.imgur.com/YkKUZPA.png)
