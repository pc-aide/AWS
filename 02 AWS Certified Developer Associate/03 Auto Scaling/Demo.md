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
    * TG (listener) - **empty** - it's ASG will take this stepp..
    * Browser: 503
    
[<img src="https://i.imgur.com/hXuDE3m.png">](https://i.imgur.com/hXuDE3m.png)
[<img src="https://i.imgur.com/o86mhZX.png">](https://i.imgur.com/o86mhZX.png)
[<img src="https://i.imgur.com/cHW2X33.png">](https://i.imgur.com/cHW2X33.png)
[<img src="https://i.imgur.com/ADAXEzP.png">](https://i.imgur.com/ADAXEzP.png)
[<img src="https://i.imgur.com/S1toodM.png">](https://i.imgur.com/S1toodM.png)
