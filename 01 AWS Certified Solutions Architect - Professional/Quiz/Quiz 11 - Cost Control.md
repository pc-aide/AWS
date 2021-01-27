# Quiz 11 - Cost Control

## Questions
1) You would like to programmatically monitor Trusted Advisor limits and if possible place automated service limits increase requests. What should you do?
  A) Use the AWS free support plan<br>Use AWS Lambda to use the Trusted Advisor API to get the current limits<br>Use AWS Lambda with the AWS Support API to increase limits automatically
  B) Use the AWS business support plan<br>Use AWS Lambda to use the Trusted Advisor API to get the current limits<br>Use AWS Lambda with the AWS Support API to increase limits automatically
  C) Use the AWS free support plan<br>Use AWS Lambda to use the Trusted Advisor API to get the current limits & send a message to an SNS topic in case you're reaching a limit. The SNS topic is linked to an email notification. Manually place requests to increase limits
  D) Use the AWS business support plan<br>Use AWS Lambda to use the Trusted Advisor API to get the current limits & send a message to an SNS topic in case you're reaching a limit. The SNS topcis is linked to an email notifcation. Manually place requests to increase limits
2) You would like to be notified when objects in your S3 bucket are being made public, as soon as possible. What do you recommend?
  A) Upgrade the AWS support plan to business & use Trusted Advisor
  B) Use S3 events linked to a Lambda function that will check the object's ACL
  C) Create a CloudWatch event linked to a Lambda function that will scan the S3 bucket for public objects
3) Your S3 bucket contains large datasets meant to be shared with many of your customers. You want to make sure you are only paying for storage costs and not the network transfer costs for the download of these datasets. How can you do it?
  A) Use S3 Request Pays feature & tell your customers to give them their IAM role ARN so you can add that to your S3 bucket policy
  B) Use S3 Request Pays feature & tell your customers to assume a role in your account to download the S3 files
  C) Setup S3 CRR into your target customers bucket
  D) Create pre-signed URLs for your objects
* [Answers](https://i.imgur.com/FCLMqkm.png)
  
* Score:
  * [27-01-2021] - 2/3 = 66%
