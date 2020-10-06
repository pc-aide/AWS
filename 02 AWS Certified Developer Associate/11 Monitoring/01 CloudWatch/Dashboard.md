# Dashboard

## Acronym
* EB - Elastic Beanstalk
* Cfg - Configuration
* ALB - Application Load Balancer
* TG - Target Group

## Doc

## Demo
* Name: NetworkIn

[<img src="https://i.imgur.com/RqmIPHU.png">](https://i.imgur.com/RqmIPHU.png)
[<img src="https://i.imgur.com/YEuLrUQ.png">](https://i.imgur.com/YEuLrUQ.png)


---

## Scope
* Don't choose scope that will be terminate
    * scope (metric): InstanceId: i-044f8e57...
    * EB\cfg\ASG: - EC2 can terminate or down
    * ALB: 
    
    
    
[<img src="https://i.imgur.com/rzxBig4.png">](https://i.imgur.com/rzxBig4.png)
[<img src="https://i.imgur.com/S1QWivi.png">](https://i.imgur.com/S1QWivi.png)
[<img src="https://i.imgur.com/tjC7mxr.png">](https://i.imgur.com/tjC7mxr.png)
[<img src="https://i.imgur.com/9o7c2A4.png">](https://i.imgur.com/9o7c2A4.png)
[<img src="https://i.imgur.com/3FPIWL9.png">](https://i.imgur.com/3FPIWL9.png)

* test: stop: i-044f8e571da79e991

[<img src="https://i.imgur.com/HcEPdz0.png">](https://i.imgur.com/HcEPdz0.png)
[<img src="https://i.imgur.com/cWEL69j.png">](https://i.imgur.com/cWEL69j.png)
[<img src="https://i.imgur.com/uFPpJOR.png">](https://i.imgur.com/uFPpJOR.png)

* Web page still up:

[<img src="https://i.imgur.com/eBcbB4K.png">](https://i.imgur.com/eBcbB4K.png)

* ALB (TG):

[<img src="https://i.imgur.com/unl5ixV.png">](https://i.imgur.com/unl5ixV.png)

* New EC2-ID
* old.EC2- (not exist anymore):

[<img src="https://i.imgur.com/AeqeX3u.png">](https://i.imgur.com/AeqeX3u.png)

* Check NetworkIn (old.ec2-id) - nothing:
* the site still up

[<img src="https://i.imgur.com/I7AlQPi.png">](https://i.imgur.com/I7AlQPi.png)

### Good Scope
* Correction\Edit
    * Metric\ApplicationELB\
    
[<img src="https://i.imgur.com/EPenL9A.png">](https://i.imgur.com/EPenL9A.png)
