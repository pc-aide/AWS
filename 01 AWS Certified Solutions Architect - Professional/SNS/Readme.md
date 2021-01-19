# SNS

## Acronym
* SNS - Simple Notification Service
* Pub/Sub - Publish/Subscribe
* SQS - Simple Queue Service
* SSE - Server-Side-Encryption

---

## Intro
* Coordinates & manages delivery & sending of messages to subscribers through resources called topics
* There are two types of clients know as subscribers & publishers, they're also known as consumers & producers
* Subscribers consume messages & notifications that are published via supported protocol, like HTTP/S or email
* Policies can be put into place to control who can publish messages to the topic

---

## Pub/Sub
* What if you want to send one message to many receivers?

### Diagram
[<img src="https://i.imgur.com/gWOs71K.png">](https://i.imgur.com/gWOs71K.png)
[<img src="https://i.imgur.com/DssRwFS.png">](https://i.imgur.com/DssRwFS.png)

---

## AWS SNS
* The "event producer" only sneds message to one SNS topic
* As many "event receivers" (subscriptions) as we want to listen to the SNS topic notifications
* Each subscriber to the topic will get all the messages (note: new feature to filter messages)
* Up to 10M suscriptions per topic
* 100k topics limit
* Subscribers can be:
  1) SQS
  2) HTTP/HTTPS (with delivery retries - how many times)
  3) Lambda
  4) Email
  5) SMS messages
  6) Mobile Notifications (SNS Mobile Push - Android, Apple, Fire OS, Windows...)
  
---

## SNS + SQS: Fan Out
* Push once in SNS, receive in many SQS queues
* Fully decoupled, no data loss, ability to add receivers of data later
* SQS allows for delayed processing, retries of work
* May have many workers on one queue & one worker on the other queue

### Diagram
[<img src="https://i.imgur.com/GIHkdUS.png">](https://i.imgur.com/GIHkdUS.png)

---

## Encryption
* SNS provides **in-transit** encryption by default
* Enabling SSE add **at-rest** encryption to your topics
