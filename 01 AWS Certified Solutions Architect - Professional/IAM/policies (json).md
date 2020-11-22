# policies (json)

## AdministratorAccess
* default for adminGroup
````json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "*",
            "Resource": "*"
        }
    ]
}
````

---

## PowerUserAccess
* Note how "NotAction" is used instead of Deny
````json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "NotAction": [
                "iam:*",
                "organizations:*",
                "account:*"
            ],
            "Resource": "*"
        },
        {
            "Effect": "Allow",
            "Action": [
                "iam:CreateServiceLinkedRole",
                "iam:DeleteServiceLinkedRole",
                "iam:ListRoles",
                "organizations:DescribeOrganization",
                "account:ListRegions"
            ],
            "Resource": "*"
        }
    ]
}
````

---

## Conditions
* Syntax:
````json
"Condition" : {"{condition-operator}" : {"{condition-key}" : "{condition-value}"}}
````
* Operators
    1) String (StringEquals, StringNotEquals, StingLike...)
````json
"Condition" : {"StringEquals" : {"aws:PrincipalTag/job-category": "iamuser-admin"}}
````
````json
"Condition" : {"StirngLike" : {"s3:prefix": [ "", "home/", "home/${aws:username}/" ]}}
`````
   2) Numeric (NumericEquals, NumericNotEquals, NumericLessThan...)
   3) Data (DateEquals, DateNotEquals, DateLessThan...)
   4) Boolean
````json
"Condition" : {"Bool" : {"aws:SecureTransport": "true"}}
````
````json
"Condition" : {"Bool" : {"aws:MultiFactorAuthPresent": "true"}}
````
  5) (Not)IpAddress:
````json
"Condition" " {"IpAddress": {"aws:SourceIp": "203.0.113.0/24"}}
````
  6) ArnEquals, ArnLike
  7) Null:
````json
"Condition": {"Null": {"aws:TokenIssueTime": "true"}}
````

---

## Variables
* Example: ${aws:username}
````json
"Resource": ["arn:aws:s3:::mybucket/${aws:username}/*"]
````
* AWS Specific:
    * aws:CurrentTime,
    * aws:TokenIssueTime
    * aws:principaltype
    * aws:SecureTransport
    * aws:SourceIp
    * aws:userid
    * ec2:SourceInstanceARN
* Service Specific:
    * s3:prefix
    * s3:max-keys
    * s3:x-amz-acl
    * sns:Endpoint
    * sns:Protocol
* Tag Based:
    * iam:ResourceTag/key-name
    * aws:PrincipalTag/key-name
    
---

## IAM Roles vs Resource Based Policies
* Attach a policy to a resource (ex: **S3 bucket policy**) versus attaching of a uisng a role as a proxy
* When you assume a **IAM Role** (user, application or service), you give up your orignal permissions & take the permissions assigned to the role
* When using a resource **based policy**, the pincipal doesn't have to give up any permissions
* <ins>Example</ins>: User in account A needs to scan a DynamoDB table in Account A & dump it in an S3 bucket in Account B
* Supported by: 
    * S3 bucket
    * SNS topics
    * SQS

### Diagram
[<img src="https://i.imgur.com/hf6LWph.png">](https://i.imgur.com/hf6LWph.png)

### Ex 01 - scan DynamoDB table & O/P to a S3
[<img src="https://i.imgur.com/QBsxZgi.png">](https://i.imgur.com/QBsxZgi.png)
