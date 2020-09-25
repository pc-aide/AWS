# AWS CLI Dry Runs

## Acronym

## Doc

## Intro
* Sometimes, we'd just like to make sure we have ther permissions...
* But not actually run the run the commands!
* Some AWS CLI commands (such as EC2) can become expensive if they succeed, say if we wanted to try to create an EC2 Instance
* Some AWS CLI commands (not all) contain a **--dry-run** options to simulate API calls

### Demo
````bash
aws ec2 run-instances help
````
[<img src="https://i.imgur.com/ICKGmgP.png">](https://i.imgur.com/ICKGmgP.png)

````bash
aws ec2 run-instances --dry-run --image-id ami-020caff809d5a5307 --instance-type t2.micro
````
[<img src="https://i.imgur.com/shhd4w5.png">](https://i.imgur.com/shhd4w5.png)
[<img src="https://i.imgur.com/ppXqI50.png">](https://i.imgur.com/ppXqI50.png)
[<img src="https://i.imgur.com/au3lwIT.png">](https://i.imgur.com/au3lwIT.png)
