# s3

## Doc
* [s3 - AWS CLI](https://docs.aws.amazon.com/cli/latest/reference/s3/)
* [GET Bucket (List Objects) version 2](https://docs.aws.amazon.com/AmazonS3/latest/API/archive-v2-RESTBucketGET.html)
* [Encrypting existing Amazon S3 objects with the AWS CLI](https://aws.amazon.com/blogs/storage/encrypting-existing-amazon-s3-objects-with-the-aws-cli/)

## Switch
* ls - list segment
* cp - copy
* rm - remove
* mb - make a bucket
* website
* mv - move or rename
* sync
* rb - remove bucket

## api
*  aws s3api help --enabled e.g versioning
    * mfa-delete --Need root account

## help
````bash
aws s3 help
````

````bash
aws s3 cp help
````

## syntax
* aws s3 \<switch\>

## Examples
```bash
aws s3 ls --profile \<UserName\>
````
[<img src="https://i.imgur.com/bO4t6JX.png">](https://i.imgur.com/bO4t6JX.png)

````bash
aws s3 mb s3://\<NewNameLowerCas\>
````
[<img src="https://i.imgur.com/vg02p0R.png">](https://i.imgur.com/vg02p0R.png)

````bash
aws s3 rb s3://\<BucketName\> --profile \<UserName\>
````

````bash
aws s3 ls s3://\<bucketname\>
````
[<img src="https://i.imgur.com/W5Mg1Dm.png">](https://i.imgur.com/W5Mg1Dm.png)

````bash
aws s3 cp s3://MyBucket/MyFile.png
````
[<img src="https://i.imgur.com/e5aXNMD.png">](https://i.imgur.com/e5aXNMD.png)

````bash
aws s3 mb s3://mfa-delete-demo-01 --profile mfa-delete
# Syntax: aws s3api put-bucket-versioning --bucket mfa-delete-demo-01 --versioning-configuration Status=Enabled,MFADelete=Enabled --mfa "arn:.. mfa-codeFromYourDevice " --profile mfa-delete
# to disabled, just put "Disabled" for MFADelete
````
[<img src="https://i.imgur.com/vmz2AVA.png">](https://i.imgur.com/vmz2AVA.png)
[<img src="https://i.imgur.com/BUXJVQ4.png">](https://i.imgur.com/BUXJVQ4.png)
[<img src="https://i.imgur.com/mirP8Jp.png">](https://i.imgur.com/mirP8Jp.png)
[<img src="https://i.imgur.com/5Yky46S.png">](https://i.imgur.com/5Yky46S.png)

````bash
# Encrypted file | other option aws:kms
aws s3 cp s3://demo-01-monitored/beach.jpeg s3://demo-01-monitored/beach.jped --sse AES256
````

````bash
# Enabled versioning
aws s3api put-bucket-versioning --bucket demo-01-monitored --versioning-configuration Status=Enabled
````

````bash
# Disabled versioning
aws s3api put-bucket-versioning --bucket demo-01-monitored --versioning-configuration Status=Suspended
````
[<img src="https://i.imgur.com/BTBUOI7.png">](https://i.imgur.com/BTBUOI7.png)

````bash
# Delete bucket with versioning
aws s3 rb s3://demo-01-monitored --force
````
[<img src="https://i.imgur.com/cVL8Bjn.png">](https://i.imgur.com/cVL8Bjn.png)

````bash

````
