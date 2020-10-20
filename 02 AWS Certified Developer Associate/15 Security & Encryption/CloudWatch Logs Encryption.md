# CloudWatch Logs Encryption

## Doc

## Acronym
* KMS - Key Management Service
* CMK - Custom Master Key

## Intro
* You can encrypt CloudWatch logs with KMS keys
* Encryption is enabled at hte log group level, by associating a CMK with a log group, either when
  you create the log group of after it exists
* You can't associate a CMK with a log group using the CloudWatch console
* You must use the CloudWatch Logs API (CLI):
    * **associate-kms-key**: if the log group already exists
    * **create-log-group**: if the log group doesn't exist yet
    
---

## Demo
* CloudWatch\Log groups
    * take any one 
      * KMS key ID: empty & **can't associate with a KMS key**

[<img src="https://i.imgur.com/huEkCrt.png">](https://i.imgur.com/huEkCrt.png)
[<img src="https://i.imgur.com/H8tZTUb.png">](https://i.imgur.com/H8tZTUb.png)

* associte this key: Demo-KMS
* we need used the CLI

[<img src="https://i.imgur.com/uDY9dus.png">](https://i.imgur.com/uDY9dus.png)

* associate with existing log group
````bash
aws logs associate-kms-key \
--log-group-name /aws/lambda/Lambda-SSM \
--kms-key-id arn:aws:kms:ca-central-1:427263915585:key/6a7e9076-461d-47c7-992f-eed92365b0f7 \
--region ca-central-1
````
* AccessDeniedException
    * is not allowed to be used with LogGroup
    * we need to add key policy to Demo-KMS

[<img src="https://i.imgur.com/5mcKLMs.png">](https://i.imgur.com/5mcKLMs.png)

* KMS\Demo-KMS\Key policy
    * Default policy
    * add this after Resouce Ln:
````json
{
    "Id": "key-consolepolicy-3",
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Enable IAM User Permissions",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::427263915585:root"
            },
            "Action": "kms:*",
            "Resource": "*"
        },
        {
    		"Effect": "Allow",
    		"Principal": { "Service": "logs.ca-central-1.amazonaws.com" },
    		"Action": [
        	"kms:Encrypt*",
        	"kms:Decrypt*",
        	"kms:ReEncrypt*",
        	"kms:GenerateDataKey*",
        	"kms:Describe*"
    ],
            "Resource": "*"
}
    ]
}
````

[<img src="https://i.imgur.com/FPA2J6A.png">](https://i.imgur.com/FPA2J6A.png)
[<img src="https://i.imgur.com/RquGEQA.png">](https://i.imgur.com/RquGEQA.png)

* Try again our CLI
````bash
aws logs associate-kms-key \
--log-group-name /aws/lambda/Lambda-SSM \
--kms-key-id arn:aws:kms:ca-central-1:427263915585:key/6a7e9076-461d-47c7-992f-eed92365b0f7 \
--region ca-central-1
````
[<img src="https://i.imgur.com/ltaQxKi.png">](https://i.imgur.com/ltaQxKi.png)

* CW\log groups\
    * KMS Key ID - this log groups now fully encrypted with this KMS key ID
    
[<img src="https://i.imgur.com/04R6B8D.png">](https://i.imgur.com/04R6B8D.png)

* Create new log group
````bash
aws logs create-log-group \
--log-group-name /example-encrypted \
--kms-key-id arn:aws:kms:ca-central-1:427263915585:key/6a7e9076-461d-47c7-992f-eed92365b0f7 \
--region ca-central-1
````
[<img src="https://i.imgur.com/B55CgqE.png">](https://i.imgur.com/B55CgqE.png)
[<img src="https://i.imgur.com/TzlEWGQ.png">](https://i.imgur.com/TzlEWGQ.png)

* log group
    * /example-encryted
    
[<img src="https://i.imgur.com/p0DjES9.png">](https://i.imgur.com/p0DjES9.png)
