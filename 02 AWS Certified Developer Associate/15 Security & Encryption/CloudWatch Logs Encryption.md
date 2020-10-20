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

[<img src="https://i.imgur.com/5mcKLMs.png">](https://i.imgur.com/5mcKLMs.png)
