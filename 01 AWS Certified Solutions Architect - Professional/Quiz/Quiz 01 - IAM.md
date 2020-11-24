# Quiz 01 - IAM

## Questions
1) You have an application in account A that needs to read from a DynamoDB table in account A and continuously insert messages in an SQS queue in Account B. How can the application achieve this efficiently?
  * A. Create a cross-account role with PUT rights to SQS in Account B, & assume that role from the application in Account A
  * B. Create an SQS queue policy & authorize the role in account A
  * C. Create a multi-account role & use it as your EC2 instance role
2) Your company would like to integrate their Active Directory with AWS for user federation. Which STS API should they use?
  * A. AssumeRole
  * B. AssumeRoleWithSAML
  * C. AssumeRoleWithWebIdentity
  * D. GetSessionToken
3) Your company has an Active Directory on-premise and would like to set it up to multiple AWS accounts efficiently. How can this be done efficiently?
  * A. Create an IdP & integrate it with each AWS account
  * B. Create a Custom Identity Broker Application to automatically integrate it with each AWS account
  * C. Leverage AWS SSO, create an AD Connector & create a two-way forest trust between your AD connector & your AD
  * D. Leverage AWS SSO, create an AWS Managed Directory & create a two-way forest trust between your AD & AWS Managed Directory
4) You would like to limit an AWS account and prevent it from accessing the Amazon S3 service. How should you proceed?
  * A. Create a global S3 bucket policy
  * B. Create an IAM role & apply it to the account managed AdminPolicy
  * C. Create an SCP & apply it to the account
  * D. Create an AWS Organization & apply an SCP to the account
* [Answers](https://i.imgur.com/Ax45bsy.png)
* Score:
  * [24-11-2020 AM] 1/4 = 25%
