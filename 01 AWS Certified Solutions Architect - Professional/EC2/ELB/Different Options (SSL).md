# Different Options (SSL)

## Acronym
* ALB - Application Load Balancer
* LB - Load Balancer

## Intro
* if cert on ALB
  * SSL Offloading (SSL termination)
* if cert on EC2
  * SSL Pass-Throug
    * need more compute: for encrypt & decrypt at level instance & LB

### Diagram
[<img src="https://i.imgur.com/Br3dzKI.png">](https://i.imgur.com/Br3dzKI.png)
