# Demo EventBridge

## Acronym
* CW - CloudWatch
* SNS - Simple Notification Service

## Doc

## Intro
* CW\Rules
    * 2x rules:
      * CodePipelineFailure
      * AWSCodeStarNotifications-rule

[<Img src="https://i.imgur.com/4wDynIW.png">](https://i.imgur.com/4wDynIW.png)

* EventBridge:

[<img src="https://i.imgur.com/A9q9VqC.png">](https://i.imgur.com/A9q9VqC.png)

* Event Buses:

[<img src="https://i.imgur.com/ztJBYHY.png">](https://i.imgur.com/ztJBYHY.png)

* Creat Event bus
    * Name: Demo-Bus
    
[<img src="https://i.imgur.com/5ry5fph.png">](https://i.imgur.com/5ry5fph.png)
[<img src="https://i.imgur.com/tjxg4VB.png">](https://i.imgur.com/tjxg4VB.png)

---

## Partner event sources
[<img src="https://i.imgur.com/QKt8Eyv.png">](https://i.imgur.com/QKt8Eyv.png)

---

## Event buses
* Defalt: 

[<img src="https://i.imgur.com/JlgWYQo.png">](https://i.imgur.com/JlgWYQo.png)

EventBridge Rules (default) = CW rules:


[<img src="https://i.imgur.com/tgHbFxb.png">](https://i.imgur.com/tgHbFxb.png)
[<img src="https://i.imgur.com/KSy7Fp1.png">](https://i.imgur.com/KSy7Fp1.png)

* EventBridge\Rules\Create rule
    * name: DemoCodePipeline
    * Define pattern: Event pattern
    * Event matching pattern: Pre-defined pattern by service
    * Service provider: AWS
    * Service name: CodePipeline
    * Event type: CodePipeline Pipeline Execution State Change
    * Target: SNS topic
    * Topic: codecommit-lab
    
[<img src="https://i.imgur.com/vUV9KRF.png">](https://i.imgur.com/vUV9KRF.png)
[<img src="https://i.imgur.com/3BeKj5u.png">](https://i.imgur.com/3BeKj5u.png)

---

## Schema registry
[<img src="https://i.imgur.com/ta9dJme.png">](https://i.imgur.com/ta9dJme.png)

* Schemas:

[<img src="https://i.imgur.com/WinD0tm.png">](https://i.imgur.com/WinD0tm.png)

* Search all schemas\aws.codepipeline:
    * aws.codepipeline@CodePipelineActionExecutionStateChange

[<img src="https://i.imgur.com/GG0RS46.png">](https://i.imgur.com/GG0RS46.png)
[<img src="https://i.imgur.com/XmzAp2K.png">](https://i.imgur.com/XmzAp2K.png)
