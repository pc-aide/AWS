# SQS

## Acronym
* SQS - Simple Queue Service
* Std - Standard

## Doc

## What's a queue?
[<img src="https://i.imgur.com/PD7If3O.png">](https://i.imgur.com/PD7If3O.png)

---

## Std Queue
* Oldest offering (over 10 years old)
* Fully managed service, used to **decouple applications**
* Attributes:
    * Unlimited throughput, unlimited number of messages in queue
    * Default retention of messages: 4 days, maximum of 14 days
    * Low latency (<10 ms on publish & receive)
    * Limitation of 256 KB per message sent
* Can have duplicate messages (at lest once delivery, occasionally)
* Can have out of order messages (best effort ordering)

---

## SQS - Producing Messages
* Produced to SQS using the SDK (SendMessage API)
* The message is **perisisted** in SQS until a consumer deletes it
* Message retention: default 4 days, up to 14 days
* Example: send order to be processed
    * Order id
    * Customer id
    * Any attributes you want
* SQS std: unlimited throughput

### Diagram
[<img src="https://i.imgur.com/Z56UWbX.png">](https://i.imgur.com/Z56UWbX.png)

---

## SQS - Consuming Messages
