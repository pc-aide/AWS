# URLs

## Acronym
* S3TA- S3 Transfer Acceleration

## Table
| N | Name                                                                        | E.g. |
| - | --------------------------------------------------------------------------- | ---- |
| 1 | [AWS Policy Generator](http://awspolicygen.s3.amazonaws.com/policygen.html) | S3,  |
| 2 | [AWS CLI - all-services](https://docs.aws.amazon.com/cli/latest/reference/#available-services) |s3, |
| 3 | [IAM Policy Simulator](https://policysim.aws.amazon.com/) | |
| 4 | [list-cloudfront-ips](http://d7uri8nf7uskq.cloudfront.net/tools/list-cloudfront-ips) | |
| 5 | [hub docker](https://hub.docker.com/) | ex: httpd-v2.4 | 
| 6 | [Sample apps (Beanstalk)](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/RelatedResources.html) | ex.: Node.js |
| 7 | [Simple Monthly Calculator](https://calculator.s3.amazonaws.com/index.html?) | ex: https://calculator.s3.amazonaws.com/index.html?key=cloudformation/c3686d8c-397a-40f7-9bc5-c9394748d5c0 |
| 8 | [epoch time](https://www.epochconverter.com/) | DynamoDB with expire_on |
| 9 | [Insomnia Core](https://insomnia.rest/download/core/?&ref=) | plan usage $$$ (API Gateway) [`Insomnia Core`](#InsomniaCore) |
| 10 | [Encryption SDK CLI](https://docs.aws.amazon.com/encryption-sdk/latest/developer-guide/crypto-cli.html) | |
| 11 | [serverless-app-examples](https://github.com/amazon-archives/serverless-app-examples/tree/master/python) | sample-app-python (SAM) |
| 12 | [Service Health Dashboard](https://status.aws.amazon.com/) | [`Serivice Health Dashboard`](#ServiceHealthDashboard) |
| 13 | [Infrastructure](https://infrastructure.aws/) |[`Infrastructure`](#Infrastructure) |
| 14 | [CloudFormation(user guide: properties of AWS service](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-stack.html) |
| 15 | [aws (github)](https://github.com/aws) | |
| 16 | [AWS Lab (github)](https://github.com/awslabs) | |
| 17 | [mailinator (email-test)](https://www.mailinator.com/) | |
| 18 | [doc-javaScript-sdk](https://docs.aws.amazon.com/AWSJavaScriptSDK/latest/AWS/S3.html)|[`JavaScript-sdk`](#JavaScript-sdk) |

---

## InsomniaCore
[<img src="https://i.imgur.com/aige3Mz.png">](https://i.imgur.com/aige3Mz.png)

## ServiceHealthDashboard
[<img src="https://i.imgur.com/xp4FZbZ.png">](https://i.imgur.com/xp4FZbZ.png)
[<img src="https://i.imgur.com/QaC3IaL.png">](https://i.imgur.com/QaC3IaL.png)

### My Dashboard
[<img src="https://i.imgur.com/R5Trxqz.png">](https://i.imgur.com/R5Trxqz.png)

---

## Infrastructure
[<img src="https://i.imgur.com/hcOql8b.png">](https://i.imgur.com/hcOql8b.png)

* S3TA:
[<img src="https://i.imgur.com/RDPhRSB.png">](https://i.imgur.com/RDPhRSB.png)

---

## CloudFormation
* SG :
````json
{
  "Type" : "AWS::EC2::SecurityGroup",
  "Properties" : {
      "GroupDescription" : String,
      "GroupName" : String,
      "SecurityGroupEgress" : [ Egress, ... ],
      "SecurityGroupIngress" : [ Ingress, ... ],
      "Tags" : [ Tag, ... ],
      "VpcId" : String
    }
}
````

---

## JavaScript-sdk

[<img src="http://pix.toile-libre.org/upload/original/1604848770.png">](http://pix.toile-libre.org/upload/original/1604848770.png)
