# CloudWatch

## Switchs
* aws logs help

## Syntax
* associate-kms-key --log-group-name <value>
* create-group-log-group --log-group-name <value>

## Examples
### 01 - Associate with existing log group
````bash
# Don't forget policy: kms\<kmsName>\**default policy** change it for allow
aws logs associate-kms-key \
--log-group-name /aws/lambda/Lambda-SSM \
--kms-key-id arn:aws:kms:ca-central-1:427263915585:key/6a7e9076-461d-47c7-992f-eed92365b0f7 \
--region ca-central-1
````
[<img src="https://i.imgur.com/ltaQxKi.png">](https://i.imgur.com/ltaQxKi.png)
[<img src="https://i.imgur.com/X8DKmcL.png">](https://i.imgur.com/X8DKmcL.png)

### 02 - Create new log group
````bash
aws logs create-log-group \
--log-group-name /example-encrypted \
--kms-key-id arn:aws:kms:ca-central-1:427263915585:key/6a7e9076-461d-47c7-992f-eed92365b0f7 \
--region ca-central-1
````
[<img src="https://i.imgur.com/B55CgqE.png">](https://i.imgur.com/B55CgqE.png)
