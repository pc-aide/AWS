# ASG Scaling Policies

## Acronym
* ASG - Auto Scaling Group

## Doc
* [Scaling cooldowns for Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/Cooldown.html?icmpid=docs_ec2as_help_panel)

## Introduction
* Target Tracking Scaling
    * Most simple & easy to set-up
    * Ex.: I want the average ASG CPU to stay at around 40%
* Simple / Step Scaling
    * When a CloudWatch alarm is triggered (ex.: CPU > 70%), then add 2 units (instances)
    * When a CloudWatch alarm is triggered (ex.: CPU < 30%), then remove 1 unit
* Scheduled Actions
    * Anticipate a scaling base on kown usage patterns
    * Ex.: increase the min capacity to 10 at 5 pm on Sunday (watch NFL)
    
## ASG - Scaling Cooldowns
* The cooldown period helps to ensure that your ASG doesn't launch or terminate additional instances before the previous activity takes effect
* In addition to default cooldown for ASG, we can create cooldowns that apply to a specific **simple scaling policy**
* A scaling-specific cooldown period overrides the default cooldown period
* One common use for scaling-specific cooldowns is with a scle-in policy --a policy that terminates instances based on a specific criteria
  or metric. Because this policy terminates instances, Amazon EC2 Auto scaling needs less time to determine wheteher to terminated additional
  instances
* If the default cooldown period of 300 seconds is too long -- you can reduce costs by applying a scling-specific cooldown period of 180 seconds
  to the scale-in policy
* If your application is scaling-up & down multiples times each hour, modify the ASG cooldown timers & the CloudWatch Alarm Period that
  triggers the scale-in
  
## Logic
[<img src="https://i.imgur.com/2839U0U.png">](https://i.imgur.com/2839U0U.png)

## Demo
* ASG\SimpleAppTestASG\**Automatic scaling**
* Scaling policies: empty
* Scaling action: empty

[<img src="https://i.imgur.com/UwmEH9C.png">](https://i.imgur.com/UwmEH9C.png)

### Scaling polices
* Add policy\
  * 3x types:
    * Target tracking scaling
    * Step scaling
    * Simple scaling
    
[<img src="https://i.imgur.com/KfWvjuN.png">](https://i.imgur.com/KfWvjuN.png)

* Policy type: Target tracking scaling
* Metric: Average CPU utilisation
* Target value: 40
* Create

[<img src="https://i.imgur.com/otGC82u.png">](https://i.imgur.com/otGC82u.png)
[<img src="https://i.imgur.com/6x1mJir.png">](https://i.imgur.com/6x1mJir.png)

* for the demo
  * Instances need: 10 seconds
  
[<img src="https://i.imgur.com/Al4HECo.png">](https://i.imgur.com/Al4HECo.png)

* So i have one EC2:

[<img src="https://i.imgur.com/5ECXgP8.png">](https://i.imgur.com/5ECXgP8.png)
[<img src="https://i.imgur.com/1HHxIY6.png">](https://i.imgur.com/1HHxIY6.png)

* if now my desired capacity: 2

[<img src="https://i.imgur.com/MaKOkSI.png">](https://i.imgur.com/MaKOkSI.png)
[<img src="https://i.imgur.com/XqD5L5u.png">](https://i.imgur.com/XqD5L5u.png)
[<img src="https://i.imgur.com/sRr2cwl.png">](https://i.imgur.com/sRr2cwl.png)
[<img src="https://i.imgur.com/GlyeeGA.png">](https://i.imgur.com/GlyeeGA.png)
[<img src="https://i.imgur.com/uJyEyhZ.png">](https://i.imgur.com/uJyEyhZ.png)
[<img src="https://i.imgur.com/D9iy7hk.png">](https://i.imgur.com/D9iy7hk.png)

* it'll be remote second instance in couple time:

[<img src="https://i.imgur.com/5oKrI3h.png">](https://i.imgur.com/5oKrI3h.png)

* CloudWatch :

[<img src="https://i.imgur.com/JXODQyt.png">](https://i.imgur.com/JXODQyt.png)
[<img src="https://i.imgur.com/S8YsMEC.png">](https://i.imgur.com/S8YsMEC.png)

* alarm

[<img src="https://i.imgur.com/WeXxkV2.png">](https://i.imgur.com/WeXxkV2.png)

* safeguard: default: 15min
* wainting couple time (draining) :

[<img src="https://i.imgur.com/CUzs0iU.png">](https://i.imgur.com/CUzs0iU.png)
[<img src="https://i.imgur.com/fbvhfs3.png">](https://i.imgur.com/fbvhfs3.png)
[<img src="https://i.imgur.com/0yosyAs.png">](https://i.imgur.com/0yosyAs.png)
[<img src="https://i.imgur.com/bWJaKL7.png">](https://i.imgur.com/bWJaKL7.png)

* now our Desired cpacity drop from 2 to 1
* because target tracking policy

[<img src="https://i.imgur.com/l2wIOJG.png">](https://i.imgur.com/l2wIOJG.png)
[<img src="https://i.imgur.com/0CWCOD9.png">](https://i.imgur.com/0CWCOD9.png)
[<img src="https://i.imgur.com/QmzzTI0.png">](https://i.imgur.com/QmzzTI0.png)
