# Granting a User Permissions to Pass a Role to an AWS Service

## Doc

## Acronym
* IAM - Identity & Access Management
* ECS - Elastic Container Serivice
* STS - Security Token Service

## Intro
* To configure many AWS services, you must **pass* an IAM role to the service (this happens
  only once during setup)
* The service will later assume the role & perform actions
* Example of passing a role: 
    * To an EC2 instance
    * To an Lambda function
    * To an ECS task
    * To CodePipeline to allo it to invoke other services
* For this, you need the IAM permission **iam:PassRole**
* It often comes with iam:GetRole to view the role being passed

---

## IAM PassRole example
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:*"
      ],
      "Resources": "*"
    },
    {
      "Effect": "Allow",
      "Action": "iam:PassRole",
      "Resource": "arn:aws:iam:123456789012:role/S3Access"
    }
  ]
}
````

---

## Can a role be passed to any services?
* **No**: Roles can only be passed to hwat their <ins>trus</ins> allows 
* A **trust policy** for the role that allows the service to assume the role
````json
{
  "Version": "2012-10-17",
  "Statement": {
    "Sid": "TrusPolicyStatementThatAllowsEC2ServiceToAssumeTheAttacheRole",
    "Effect": "Allow",
    "Principal": {
      "Service": "ec2.amazonaws.com"
    },
    "Action": "sts:AssumeRole"
  }
}
````

---

## Console
* IAM\Roles\**Trusted entities**

[<img src="https://i.imgur.com/rMlrDOk.png">](https://i.imgur.com/rMlrDOk.png)

* Example\**AWSCodePipelineServic...**
    * show policy

[<img src="https://i.imgur.com/WAbF30M.png">](https://i.imgur.com/WAbF30M.png)
[<img src="https://i.imgur.com/ZL3YyWH.png">](https://i.imgur.com/ZL3YyWH.png)
