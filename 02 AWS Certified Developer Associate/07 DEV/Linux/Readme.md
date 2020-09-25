# AWS CLI on EC2

## Acronym
* IAM - Identity & access management
* EC2 - Elastic Compute Cloud

## Doc

## Into
* Never put your creds in any EC2
* IAM Roles can be attached to EC2 instances
* IAM Roles can come with a policy autorizing exactly what the EC2 instance should be able to do
* EC2 Instances can then use these profiles automatically without any additional configurations
* This is the best practice on AWS & you should 100% do this

### Diagram
[<img src="https://i.imgur.com/jJ2IZWX.png">](https://i.imgur.com/jJ2IZWX.png)
[<img src="https://i.imgur.com/epoTWIt.png">](https://i.imgur.com/epoTWIt.png)
