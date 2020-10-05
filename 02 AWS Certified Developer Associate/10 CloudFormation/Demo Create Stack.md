# Demo Create Stack

## Acronym
* EIP - Elastic IP
* SG - Security Group
* EB - Elastic Beanstalk

## Doc
* [Getting started with AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/GettingStarted.html?icmpid=docs_cfn_console)

## Intro
* We're going to create a simple EC2 instance
* Then we're going to create to add an EIP to it
* And we're going to add 2 SGs to it

### Diagram
[<img src="https://i.imgur.com/0gtjIH0.png">](https://i.imgur.com/0gtjIH0.png)

---

## Demo
* CloudFormation\Demo-App (EB)\Template\View in Designer:

[<img src="https://i.imgur.com/UuNwO2D.png">](https://i.imgur.com/UuNwO2D.png)
[<img src="https://i.imgur.com/7qcjskc.png">](https://i.imgur.com/7qcjskc.png)
[<img src="https://i.imgur.com/GYwhu2Z.png">](https://i.imgur.com/GYwhu2Z.png)

* template language (json | yaml):

[<img src="https://i.imgur.com/GwwfBJn.png">](https://i.imgur.com/GwwfBJn.png)

* Choose N. Virginia (region) for the demo
* Create stack

[<img src="https://i.imgur.com/bM2sRar.png">](https://i.imgur.com/bM2sRar.png)

* Prepare template: Template is ready
* Upload a template file: 0-just-ec2.yml:
````yml
---
Resources:
  MyInstance:
    Type: AWS::EC2::Instance
    Properties:
      AvailabilityZone: us-east-1a
      ImageId: ami-a4c7edb2
      InstanceType: t2.micro
```

[<img src="https://i.imgur.com/NObJ0WS.png">](https://i.imgur.com/NObJ0WS.png)

* Stack name: First-Stack
* Next twice

[<img src="https://i.imgur.com/BahbyG1.png">](https://i.imgur.com/BahbyG1.png)

* Review\Create stack

[<img src="https://i.imgur.com/D2oU2lz.png">](https://i.imgur.com/D2oU2lz.png)
[<img src="https://i.imgur.com/TJZRxsm.png">](https://i.imgur.com/TJZRxsm.png)
[<img src="https://i.imgur.com/NbIaz1T.png">](https://i.imgur.com/NbIaz1T.png)
[<img src="https://i.imgur.com/DhWlzeG.png">](https://i.imgur.com/DhWlzeG.png)

* EC2 (N.Virginia):

[<img src="https://i.imgur.com/qEyx1GI.png">](https://i.imgur.com/qEyx1GI.png)

* EC2\Tags:

[<img src="https://i.imgur.com/V4Ko3zW.png">](https://i.imgur.com/V4Ko3zW.png)

* First-Stack\Resources:

[<img src="https://i.imgur.com/jN4Y5Mm.png">](https://i.imgur.com/jN4Y5Mm.png)

* template\view in Designer:

[<img src="https://i.imgur.com/PzYuy01.png">](https://i.imgur.com/PzYuy01.png)
[<img src="https://i.imgur.com/DaLRiDp.png">](https://i.imgur.com/DaLRiDp.png)
