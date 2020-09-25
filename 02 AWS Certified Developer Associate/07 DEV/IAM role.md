# IAM role

## Acronym
* IAM - Identity & access management


## Doc
* [Common Scenarios for Roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios.html?icmpid=docs_iam_console)
* [Tutorial: Setting Up Cross Account Access](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html?icmpid=docs_iam_console)
* [IAM Roles Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html?icmpid=docs_iam_console)
* [IAM Roles FAQ](https://aws.amazon.com/iam/faqs/)

## Intro
* IAM roles\create role\AWS service\EC2
* Next
* Filter policy: AmazonS3ReadOnlyAccess
* Next twice
* Role name: S3ReadOnly
* Create role

[<img src="https://i.imgur.com/1ELhLug.png">](https://i.imgur.com/1ELhLug.png)

* EC2\your instance\attach IAM Role

[<img src="https://i.imgur.com/lMwgXgo.png">](https://i.imgur.com/lMwgXgo.png)
[<img src="https://i.imgur.com/RPDGi7z.png">](https://i.imgur.com/RPDGi7z.png)

### Test
* nothing credentilas (*/.aws/{config,credentials) in EC2

````bash
aws s3 ls
````
[<img src="https://i.imgur.com/QknlKHS.png">](https://i.imgur.com/QknlKHS.png)
[<img src="https://i.imgur.com/AfyxKaE.png">](https://i.imgur.com/AfyxKaE.png)

````bash
aws s3 ls s3://\<BucketName\>
````
[<img src="https://i.imgur.com/0sAeUn1.png">](https://i.imgur.com/0sAeUn1.png)

* test iam policy with remove 
````bash
aws s3 rm s3://s3-ca-website/error.html
````
[<img src="https://i.imgur.com/I2BQMCY.png">](https://i.imgur.com/I2BQMCY.png)

* Or new bucket
````bash
aws s3 mb s3://kjfdsjfkdsifdsksdja
````
[<img src="https://i.imgur.com/JPsXDsh.png">](https://i.imgur.com/JPsXDsh.png)
