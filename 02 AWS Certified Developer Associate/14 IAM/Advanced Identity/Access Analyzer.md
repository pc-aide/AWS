# Access Analyzer

## Acronym
* IAM - Identity & Access Managment

## Doc

## Terminology
* Federated User

## Diagram

## Console
* IAM\Access Analyzer
        * Active - all resources
        * Archived
        * Resolved
        * All
        
[<img src="https://i.imgur.com/Jrgeyf3.png">](https://i.imgur.com/Jrgeyf3.png)        

---

## Demo
* S3\Create policy for your bucket:
* Demo.json:
````json
{
    "Version": "2012-10-17",
    "Id": "Policy1234567890121",
    "Statement": [
        {
            "Sid": "Stmt1234567890129",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:Get*",
            "Resource": "arn:aws:s3:::bucket-BucketName/*",
            "Condition": {
                "IpAddress": {
                    "aws:SourceIp": "10.24.34.0/24"
                }
            }
        },
        {
            "Sid": "Stmt1234567890124",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:*",
            "Resource": "arn:aws:s3:::BucketName-ip/*",
            "Condition": {
                "StringEquals": {
                    "aws:SourceVpc": "vpc-abc"
                }
            }
        }
    ]
}
````

* Create Analyzer:
* you should see your **Bucket policy**:

[<img src="https://i.imgur.com/QIYAfta.png">](https://i.imgur.com/QIYAfta.png)

* Details
    * Access level (API action)
      * Write
        * S3:AboutMultipartUpload
        * s3:PutObject
        * ect
      * Tagging
        * s3:DeleteOjectTagging
        * etc
      * Read
        * s3:GetAccelerateConfiguration
        * etc
      * List
        * s3:ListBucket
      * Permissions
        * s3:ObjectOwnwerOverrrideToBucketOwner
        * etc
        
[<img src="https://i.imgur.com/itKlT3u.png">](https://i.imgur.com/itKlT3u.png)

### Access analyzer for s3
* s3\Access analyzer for s3
       * view finding -> iam\access analyzer\<Finding ID>

[<img src="https://i.imgur.com/8pI822K.png">](https://i.imgur.com/8pI822K.png)
[<img src="https://i.imgur.com/WifA1Pp.png">](https://i.imgur.com/WifA1Pp.png)
