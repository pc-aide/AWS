# configure

## Acronym
* IAM - Identity & Access Management

## Note
* AWS requires that all incoming requests are cryptographically signed
* Ensure that your computer's date and time are set correctly
* If you don't, and the date/time in the signature is too
  far off of the date/time recognized by the AWS service, AWS rejects the request

[<img src="https://i.imgur.com/NxScs6K.png">](https://i.imgur.com/NxScs6K.png)

## IAM
* AWS Console\IAM to create an user (key public & secret)

## switch
* list : list profile (IAM) + access_key + secret_key + region
````
aws configure list
````
[<img src="https://i.imgur.com/CsGHtNf.png">](https://i.imgur.com/CsGHtNf.png)

## Configure
1) Credential (user + keys)

2) Default OutPut format
    * json
    * yaml
    * text
    * table
  
3) AWS Region
    * us-east-2

### Profile
* AWS CLI stores this information in a profile (a collection of settings) named default

#### Default (no profile)
````Bash
aws configure 
````
[<img src="https://i.imgur.com/MEe4PSd.png">](https://i.imgur.com/MEe4PSd.png)

* with profile
````Bash
aws configure --profile User-S3
````

````Bash
aws configure list --profile User-S3
````
[<img src="https://i.imgur.com/cGNMp83.png">](https://i.imgur.com/cGNMp83.png)

* Tested your profile wiht s3

````Bash
# Syntax: aws <Available service> <command> <Optional --profile>
aws s3 ls --profile User-S3
````
[<img src="https://i.imgur.com/mfBnr2s.png">](https://i.imgur.com/mfBnr2s.png)


## Tranfert a file (S3)
````Bash
# hostname : client (no connected on SRV)
cat demo.txt
````
[<img src="https://i.imgur.com/cECFTBU.png">](https://i.imgur.com/cECFTBU.png)
