# Beanstalk

## Acronym
* EB - Elastic Beanstalk
* IAM - Identity & Access Management

## Doc

## X-Ray with EB
* AWS EB platforms include the X-Ray daemon
* You can run the daemon by setting an option in the EB console or with a configuration file (in .ebextensions/xray-daemon.config)
* example.yml:
````yml
option_settings:
    aws:elasticbeanstalk:xray:
        XRayEnabled: true
````
* Make sure to give your instance profile the correct IAM permissions so that the X-Ray daemon can function correctly
* Then make sure your application code is instrumented with the X-Ray SDK
* Note: The X-Ray daemon is not provided for Multicontainer Docker

---

## Demo
* EB\\<Your env\>\configuration\software\X-Ray:
* no downtime (web srv)

[<img src="https://i.imgur.com/qDqULqb.png">](https://i.imgur.com/qDqULqb.png)
[<img src="https://i.imgur.com/TtOjLbX.png">](https://i.imgur.com/TtOjLbX.png)
[<img src="https://i.imgur.com/8k6qIkA.png">](https://i.imgur.com/8k6qIkA.png)

* Check if my Instance with good IAM Role
* health

[<img src="https://i.imgur.com/H47aBkY.png">](https://i.imgur.com/H47aBkY.png)

* EC2\IAM Role:

[<img src="https://i.imgur.com/njIoepi.png">](https://i.imgur.com/njIoepi.png)

* IAM Role:
    * AWSElasticBeanstalkWebTier
      * Policy summary
        * **X-Ray**
    * AWSElasticBeanstalkMulticontainerDocker
    * AWSElasticBeanstalkWorkerTier
    

[<img src="https://i.imgur.com/FMTcDe8.png">](https://i.imgur.com/FMTcDe8.png)
[<img src="https://i.imgur.com/EeBuqdz.png">](https://i.imgur.com/EeBuqdz.png)
[<img src="https://i.imgur.com/Aeq3yMC.png">](https://i.imgur.com/Aeq3yMC.png)

* X-Ray.json (IAM-Role):

[<img src="https://i.imgur.com/HeIZLMU.png">](https://i.imgur.com/HeIZLMU.png)
[<img src="https://i.imgur.com/6m5DCFC.png">](https://i.imgur.com/6m5DCFC.png)
