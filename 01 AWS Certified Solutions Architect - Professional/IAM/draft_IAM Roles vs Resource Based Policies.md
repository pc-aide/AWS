# IAM Roles vs Resource Based Policies

## Intro
* Attach a policy to a resource (ex: **S3 bucket policy**) versus attaching of a uisng a role as a proxy
* When you assume a **IAM Role** (user, application or service), you give up your orignal permissions & take the permissions assigned to the role
* When using a resource **based policy**, the pincipal doesn't have to give up any permissions
* <ins>Example</ins>: User in account A needs to scan a DynamoDB table in Account A & dump it in an S3 bucket in Account B
* Supported by: 
    * S3 bucket
    * SNS topics
    * SQS

### Diagram
[<img src="https://i.imgur.com/hf6LWph.png">](https://i.imgur.com/hf6LWph.png)

### Ex 01 - scan DynamoDB table & O/P to a S3
[<img src="https://i.imgur.com/QBsxZgi.png">](https://i.imgur.com/QBsxZgi.png)
