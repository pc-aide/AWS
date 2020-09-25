# ec2

## Switch
* run-instance

## Syntax

## help
````bash
aws ec2 run-instances help
````

## Examples
````bash
 aws ec2 run-instances --dry-run --image-id ami-020caff809d5a5307 --instance-type t2.micro --profile \<UserName\>
````
[<img src="https://i.imgur.com/ppXqI50.png">](https://i.imgur.com/ppXqI50.png)

````bash
 aws ec2 run-instances --image-id ami-020caff809d5a5307 --instance-type t2.micro --profile \<UserName\>
````
[<img src="https://i.imgur.com/ppXqI50.png">](https://i.imgur.com/ppXqI50.png)

````bash
 aws ec2 run-instances --dry-run \
  --image-id ami-020caff809d5a5307 \
  --instance-type t2.micro \
  --key-name EC2Ama-ca-central \
  --security-group-ids sg-\<id\> \
  --user-data file://my_script.txt \
  --tag-specifications 'ResourceType=instance,Tags=[{Key=Name,Value=EC2Ama-01}]'
  --profile \<UserName\>
````
[<img src="https://i.imgur.com/83JPLwq.png">](https://i.imgur.com/83JPLwq.png)
