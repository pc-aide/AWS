# Alarms

## Acronym
* SNS - Simple Notification Service
* EB - Elastic Beanstalk
* ASG - Auto-Scaling Group

## Doc

## Intro
* Alarms are used to trigger notifications for any metric
* Alarms can go to Auto Scaling, EC2 Actions, SNS notifications
* Various options (sampling, %, max, min, etc...)
* Alarm States:
    1) OK
    2) INSUFFICIENT_DATA
    3) ALARM
* Period:
    * Length of time in seconds to evaluate the metric
    * High resolution custom metrics: can only choose 10 sec or 30 sec
    
---

## Demo
* Alarms\default nothing 

[<img src="https://i.imgur.com/ksCzyWR.png">](https://i.imgur.com/ksCzyWR.png)

* Create an EB
* Check againt Alarm

* Browser:

[<img src="https://i.imgur.com/xPFKlPA.png">](https://i.imgur.com/xPFKlPA.png)

* ASG\Policies\ScalingScale{Down, up} Policy:

[<img src="https://i.imgur.com/UAO5Mku.png">](https://i.imgur.com/UAO5Mku.png)
[<img src="https://i.imgur.com/1YN8eDx.png">](https://i.imgur.com/1YN8eDx.png)

* Create Alarm:

[<img src="https://i.imgur.com/e3F9LKG.png">](https://i.imgur.com/e3F9LKG.png)

* Select metric\EC2\Per-Instance Metrics\NetworkIn (EB-env):

[<img src="https://i.imgur.com/W5AoEZg.png">](https://i.imgur.com/W5AoEZg.png)
[<img src="https://i.imgur.com/PF6m5ky.png">](https://i.imgur.com/PF6m5ky.png)

* Specify metric & conditions:

[<img src="https://i.imgur.com/RS1ipbS.png">](https://i.imgur.com/RS1ipbS.png)

* Conditions:
  * NetworkIn (Bytes)
  * average: ~28k 
  * Threshold: > 70k 
  * datapoints: 1 out of 1 
  
[<img src="https://i.imgur.com/64O9DmX.png">](https://i.imgur.com/64O9DmX.png)
[<img src="https://i.imgur.com/Qj2vagF.png">](https://i.imgur.com/Qj2vagF.png)

* Browser:

[<img src="https://i.imgur.com/jOIMnuH.png">](https://i.imgur.com/jOIMnuH.png)

* Configure actions:

[<img src="https://i.imgur.com/VSfkBUq.png">](https://i.imgur.com/VSfkBUq.png)

* Create a topic:

[<img src="https://i.imgur.com/Yd5I9wI.png">](https://i.imgur.com/Yd5I9wI.png)

* Name & description (Alarm)

[<img src="https://i.imgur.com/fvTJOFS.png">](https://i.imgur.com/fvTJOFS.png)

* INSUFFICIENT (pending confirmation - Action):

[<img src="https://i.imgur.com/FZmY8Nu.png">](https://i.imgur.com/FZmY8Nu.png)
[<img src="https://i.imgur.com/7jRdVj1.png">](https://i.imgur.com/7jRdVj1.png)

* OK (Alarms):

[<img src="https://i.imgur.com/4x0NdPR.png">](https://i.imgur.com/4x0NdPR.png)
