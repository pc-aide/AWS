# Messaging

## Acronym
* SQS - Simple Queue Service
* SNS - Simple Notification Service

## Doc

## Intro
* When we start deploying multiple applications, they will inevitably need to communicate with one another
* There are two patterns of application communication
    1) Synchronous communications (application to application)
    2) Asynchronous/ Event based (application to queue to application
* **Synchronous** between applications can be problematic if there are sudden spikes of traffic
* What if you need to suddenly encode 1k videos but usually it's 10?
* In that case, it's better to **decouple** your applications:
    * using SQS: queue model
    * using SNS: pub/sub model
    * using Kinesis: real-time streaming model
* These services can scale independently from our application
    
### Diagram
[<img src="https://i.imgur.com/JaOcZtM.png">](https://i.imgur.com/JaOcZtM.png)

