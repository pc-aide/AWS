# Beanstalk Cloning

## Acronym
* LB - Load Balancer
* RDS - Relational Database Service

## Doc
* [Clone an Elastic Beanstalk environment](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.managing.clone.html?icmpid=docs_elasticbeanstalk_console)

## Intro
* Clone an environment with the exact same configuration
* Useful for deploying a "test" version of your application
* All resources & configuration are presserved:
    * LB type & configuration
    * RDS database type (but the data is not preserved)
    * Environment variables
* After cloning an environment, you can change settings

### Diagram
[<img src="https://i.imgur.com/CW9HgKJ.png">](https://i.imgur.com/CW9HgKJ.png)

---

## Demo
* Beanstalk\
  * clone my Beanstalk-env
  
[<img src="https://i.imgur.com/idfhp9k.png">](https://i.imgur.com/idfhp9k.png)

* New environment:

[<img src="https://i.imgur.com/VwcgZfu.png">](https://i.imgur.com/VwcgZfu.png)
