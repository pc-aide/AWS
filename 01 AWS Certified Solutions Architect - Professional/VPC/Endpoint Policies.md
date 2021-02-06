# Endpoint Policies

## Acronym
* API - Application Programming Interface
* EIP - Elastic IP
* IAM - Identity Access Management
* Sid - Statement ID
* SQS - Simple Queue Service
* VPC - Virtual Private Cloud
* vpce - VPC Endpoint

## Intro
* Endpoint Policies are JSON documents to control access to services
* Does not overrride or replace IAM user policies or service-specific policies (such as S3 bucket policies)
* eg:
````json
{
  "Statement": [{
    "Action": ["sqs:SendMessage"],
    "Effect": "Allow",
    "Resource": "arn:aws:sqs:us-east-2:123456789012:MyQueue",
    "Principal": {
      "AWS": "arn:aws:iam:123456789012:user:MyUser"
    }
  }]
}
````
* **Note**: 
  * the IAM user can still use other SQS API from outside the VPC Endpoint
* You could add an SQS queue policy to deny any action not done through th VPC endpoint

---

## S3 bucket policy
* VPC Endpoint Policy to restric access to bucket "my_secure_bucket"
````json
{
  "Statement": [
    {
      "Sid": "Access-to-specific-bucket-only",
      "Principal": "*",
      "Action": [
        "s3:GetObject",
        "s3:PutObject"
      ],
      "Effect": "Allow",
      "Resource": [
        "arn:aws:s3:::my_secure_bucket",
        "arn:aws:s3:::my_secure_bucket/*"
      ]
    }
  ]
}
````
* VPC Endpoint Policy to allow access to Amazon Linux 2 repositories
````json
{
  "Statement": [
    {
      "Sid": "AmazonLinux2AMIRepositoryAccess",
      "Principal": "*",
      "Action": [
        "s3:GetObject"
      ],
      "Effect": "Allow",
      "Resource": [
        "arn:aws:s3:::amazonlinux.*.amazonaws.com/*"
      ]
    }
  ]
}
````

---

## Example S3 bucket policies
* S3 bucket poliy may have
  * Condition: "**aws:sourceVpce**":"**vpce-1a2b3c4d**" to Deny any traffic that doesn't come from a specific VPC endpoint (more secure)
  * Condition: "**aws:sourceVpc**": "**vpc-111bbb22**" for a specific VPC
* The **aws:sourceVpc** condition only works for VPC Endpoints, in case you have multiple endpoints & want to manage access to your S3 buckets for all your endpoints
* The S3 bucket policies can restrict access only form a specific **public IP** address or an EIP.<ins>You can't restrict based on private IP</ins>
* Therefore aws:SourceIp condition doesn't apply for VPC endpoints
* S3 bucket policy to restrict to one specific VPC Endpoint
````json
{
  "Version": "2012-10-17",
  "Id": "Policy1415115909152",
  "Statement": [
    {
      "Sid": "Access-to-specific-VPCE-only",
      "Principal": "*",
      "Action": "s3:*",
      "Effect": "Deny",
      "Resource": [
        "arn:aws:s3:::my_secure_bucket",
        "arn:aws:s3:::my_secure_bucket/*"
      ],
      "Condition": {
        "StringNotEquals": {
          "aws:sourceVpce": "vpce-1a2b3c4d"
        }
      }
    }
  ]
}
````
* S3 bucket policy to restict to an entire VPC (multiple VPC Endpoints)
````json
{
  "Version": "2012-10-17",
  "Id": "Policy1415115909152",
  "Statement": [
    {
      "Sid": "Access-to-specific-VPC-only",
      "Principal": "*",
      "Action": "s3:*",
      "Effect": "Deny",
      "Resource": [
        "arn:aws:s3:::my_secure_bucket",
        "arn:aws:s3:::my_secure_bucket/*"
      ],
      "Condition": {
        "StringNotEquals": {
          "aws:sourceVpc": "vpc-111bbb22"
        }
      }
    }
  ]
}
````

---

## S3 Troubleshooting
[<img src="https://i.imgur.com/8yODdJk.png">](https://i.imgur.com/8yODdJk.png)
