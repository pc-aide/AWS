# Demo

## Acronym
* AZ - Availability Zone
* SG - Security group
* LB - Load Balancer
* ALB - Application Load Balancer
* TG - Target Group

## MySetup
* us-east with 3x instances on AZ differents

### EC2
[<img src="https://i.imgur.com/o7nO9wx.png">](https://i.imgur.com/o7nO9wx.png)

* Same SG for the instances:

[<img src="https://i.imgur.com/e5b9LuP.png">](https://i.imgur.com/e5b9LuP.png)

* ALB cfg:
    * AZ: 3 times
    * SG: LB-HTTP-IN-Any
    * Healthy (3 instances - TG) : empty - ASG taking this step...
    * Browser: ok
    
[<img src="https://i.imgur.com/hXuDE3m.png">](https://i.imgur.com/hXuDE3m.png)
[<img src="https://i.imgur.com/o86mhZX.png">](https://i.imgur.com/o86mhZX.png)
[<img src="https://i.imgur.com/zypiLa8.png">](https://i.imgur.com/zypiLa8.png)
[<img src="https://i.imgur.com/OmJm0MP.png">](https://i.imgur.com/OmJm0MP.png)
