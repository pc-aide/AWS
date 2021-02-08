# LAB-01 - S3 Policy Block Specific User

## Account - STS-1h (temporary)
* ARN: arn:aws:iam::355954123170:user/pluralsight-bfb7b75d
* Account ID:  Random, change after 1h
* IAM user name: pluralsight-bfb7b75d
* PWD: random, change after 1h

## Acronym
* O/P - OutPut

## URL
* https://awspolicygen.s3.amazonaws.com/policygen.html

---

## New user
* Name: Jim
* AWS Access type:
	* Programmatic access 
    * AWS Management Console acces
* PWD: P@sSw0Rd!
* UncheckBox: Require password reset
* Set permissions
	* Attach existing policies directly
    * search: S3
    * Select: AmazonS3FullAccess
* Access key ID: AKIAZUAZ453ASU7RHOKV
* Secret access key: 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
* ARN: arn:aws:iam::661479288513:user/Jim

---

## S3
* Bucket: acme-hr-confidential-ljt9l5t7
* Permissions\Bucket policy\Add statement:
	* Effect: Deny
    * Principal: <ARN>
    * Action: *
    * Amazon Resource name (ARN_bucket)
````json
{
  "Id": "Policy1612814149806",
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Stmt1612814145939",
      "Action": "s3:*",
      "Effect": "Deny",
      "Resource": "arn:aws:s3:::acme-hr-confidential-ljt9l5t7",
      "Principal": {
        "AWS": [
          "arn:aws:iam::661479288513:user/Jim"
        ]
      }
    }
  ]
}
````
---

## Test with Jim S3 bucket policy

* O/P - Jim can't acces this bucket:
* Jim can upload a file for example

[<img src="https://i.imgur.com/MeLXzkt.png">](https://i.imgur.com/MeLXzkt.png)
[<img src="https://i.imgur.com/xFPtRbR.png">](https://i.imgur.com/xFPtRbR.png)
