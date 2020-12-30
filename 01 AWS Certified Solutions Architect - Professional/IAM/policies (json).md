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

## Limit Actions to a Region
* Denies all actions on all resources if the requested region is not "us-west-2"
````json
{
  "Effect": "Deny",
  "Action": "*",
  "Resource": "*",
  "Condition": {
    "StringNotEquals": {
      "aws:RequestedRegion": [
        "us-west-2"
      ]
    }
  }
}
````

--- Exclude some action from deny
* Denies all actions on all resources EXCEPT EC2 if the requested region is not "us-west-2"
* Does not grant any permissions; just block the effect of the deny
````json
{
  "Effect": "Deny",
  "NotAction": ["ec2:*"],
  "Resource": "*",
  "Condition": {
    "StringNotEquals": {
      "aws:RequestedRegion": [
        "us-west-2"
      ]
    }
  }
}
````
---

## WhiteList
* e.g.:
````json
{
  "Effect": "Allow",
  "Action": [
    "ec2:Describe*",
    "ec2:RebootInstances",
    "ec2:StartInstances",
    "ec2:StopInstances",
  ],
  ...
}
````

---

## LimitActionUSWest2
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "LimitActionUSwest2",
      "Effect": "Deny",
      "Action": "*",
      "Resource": "*",
      "Condition": {
        "StringNotEquals": {
          "aws:RequestedRegion": [
            "us-west-2"
          ]
        }
      }
    }
  ]
}
````

---

## LimitActionsUSwest2ExceptEC2"
* Role: E1-limit region
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "LimitActionsUSwest2ExceptEC2",
      "Effect": "Deny",
      "NotAction": [
        "ec2:*"
      ],
      "Resource": "*",
      "Condition": {
        "StringNotEquals": {
          "aws:RequestedRegion": [
            "us-west-2"
          ]
        }
      }
    }
  ]
}
````
[<img src="https://i.imgur.com/mzIe2nO.png">](https://i.imgur.com/mzIe2nO.png)

---

## AllowOnlyEC2Describe
* Role: E3-whiteList describe EC2
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "LimitEC2Action",
      "Effect": "Allow",
      "Action": [
        "ec2:Describe*"
      ],
      "Resource": "*"
    }
  ]
}
````
[<img src="https://i.imgur.com/WrlnJVL.png">](https://i.imgur.com/WrlnJVL.png)
[<img src="https://i.imgur.com/dFtl5c1.png">](https://i.imgur.com/dFtl5c1.png)

* if try to launch EC2 instance or look up S3- error


[<img src="https://i.imgur.com/iHxpT4M.png">](https://i.imgur.com/iHxpT4M.png)
[<img src="https://i.imgur.com/nTMtmpB.png">](https://i.imgur.com/nTMtmpB.png)

---

## Allow All EC2 except Termnate & Delete
* Role: E4-blacklist delete tags and terminate
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowAllEC2",
      "Effect": "Allow",
      "Action": [
        "ec2:*"
      ],
      "Resource": "*"
    },
    {
      "Sid": "DenySomeEC2Actions",
      "Effect": "Deny",
      "Action": [
        "ec2:TermninateInstances",
        "ec2:DeleteTags"
      ],
      "Resource": "*"
    }
  ]
}
````
[<img src="https://i.imgur.com/sjvnkcq.png">](https://i.imgur.com/sjvnkcq.png)
[<img src="https://i.imgur.com/4ebzBj5.png">](https://i.imgur.com/4ebzBj5.png)
[<img src="https://i.imgur.com/uwVeqJp.png">](https://i.imgur.com/uwVeqJp.png)
[<img src="https://i.imgur.com/kZ8nqqO.png">](https://i.imgur.com/kZ8nqqO.png)
