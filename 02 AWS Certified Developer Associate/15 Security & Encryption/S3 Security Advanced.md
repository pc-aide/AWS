# S3 Security Advanced

## Acronym
* KMS - Key Management Service
* SSE- Server-Side-Encryption
* SSE-C - SSE-Customer
* IAM - Identity & Access Management
* SSL - Secure Sockets Layers

## Doc
* [What S3 bucket policy should I use to comply with the AWS Config rule s3-bucket-ssl-requests-only?](https://aws.amazon.com/premiumsupport/knowledge-center/s3-bucket-policy-for-config-rule/)

## S3 Encryption for Objects
* There are 4 mehtods of encrypting object in S3 
    1. SSE-S3: encrypts S3 objects using keys handled & managed by AWS
    2. SSE-KMS: leverage AWS KM to manage encryption keys
    3. SSE-C: when you want to manage your own encryption keys
    4. Client Side Encryption
* It's important to understand which ones are adapted to which sitauation for the exam

---

## SSE-KMS
* SSE-KMS: encryption using keys handled & managed by KMS
* KMS Advantages: user control + audit trail
* Object is encrypted server side
* Must set header: "**x-amz-service-side-encryption": "aws:kms"

### Diagram
[<img src="https://i.imgur.com/23unkg0.png">](https://i.imgur.com/23unkg0.png)

---

## SSE-KMS Deep Dive
* SSE-KMS leverages the **GenerateDataKey & Decrypt** KMS API calls
* These KMS API calls will show up in CloudTrail, helpful for logging
* To perform SSE-KMS, you need:
    * A KMS Key Policy that authorizes the user/role
    * An IAM policy that authorizes access to KMS
    * Otherwise you will get an access denied error
* S3 calls to KMS for SSE-KMS count against your KMS limits
    * If throttling, try exponential backoff
    * If throttling, you can request an incrase in KMS limits
    * The service throttling is KMS, not S3
    
---

## S3 Bucket Policies - Force SSL
* To force SSL, create an S3 bucket policy with a **DENY** on the condition **aws:SecureTransport = false**
* Note: Using an allow on aws:SecureTransport = true would allow anonymous GetObject if using SSL
````json
{
    "Id": "ExamplePolicy",
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AllowSSLRequestsOnly",
            "Action": "s3:*",
            "Effect": "Deny",
            "Resource": [
                "arn:aws:s3:::awsexamplebucket",
                "arn:aws:s3:::awsexamplebucket/*"
            ],
            "Conditions": {
                "Bool": {
                    "aws:SecureTransport": "false"
                }
            },
            "Principal": "*"
        }
    ]
}
````

---

## S3 Bucket Policy - Force Encryption of SSE-KMS
1. Deny incorrect encryption header: make sure it includes aws:kms (== SSE-KMS) <- Ln13
2. Deny no encryption header to ensure objects aren't uploaded un-encrypted <- Ln22
* Note: could swap 2) for S3 default encryption of SSE-KMS
````json
{
    "Version": "2012-10-17",
    "Id": "PutObjPolicy",
    "Statement": [
        {
            "Sid": "DenyIncorrectEncryptionHeader",
            "Effect": "Deny",
            "Principal": "*",
            "Action": "s3:PutOject",
            "Resource": "arn:aws:s3:::<bukect_name>",
            "Condition": {
                "StringNotEquals": {
                    "s3:x-amz-server-side-encryption": "aws:kms"
                }
            }
        },
        {
            "Sid": "DenyUnEncryptedObjectUploads",
            "Effect": "Deny",
            "Principal": "*",
            "Action": "s3:PutOject",
            "Resource": "arn:aws:s3:::<bukect_name>/*",
            "Condition": {
                "Null": {
                    "s3:x-amz-server-side-encryption": true
                }
            }
        }
    ]
}
````
