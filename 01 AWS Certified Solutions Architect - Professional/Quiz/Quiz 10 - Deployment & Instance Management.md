# Quiz 10 - Deployment & Instance Management

## Quiz
1) You are looking to migrate a Java Tomcat application from on-premise to AWS cloud, without changing the code. Which platform do you recommend?
   * A. Use Fargate
   * B. Use Elastic Beanstalk
   * C. Use Lambda
   * D. Use OpsWorks
2) You are deploying a Lambda function using CodeDeploy and would like to ensure it's properly working after some traffic has started to shift to it. To make sure it's working, you want to make sure the number of requests made on your DynamoDB instance remains stable. How do you suggest achieving this?
   * A. Create a Pre Traffic Hook as a Lambda function & link it to CodeDeploy
   * B. Create a Post Traffic Hook as a Fargate task & link it to CodeDeploy
   * C. Create a CW Alarm & link it to CodeDeploy
   * D. Deploy to a new Lambda function & use Route 53 for LB
3) You would like to make sure a DynamoDB table created using CloudFormation does not get deleted on stack deletion. What do you recommend?
   * A. Use a Stack Policy
   * B. Use a Deletion Policy for Snapshot
   * C. Use a Deletion Policy for Retain
   * D. Use StackSet
   * E. Use CloudFormer
4) You would like to ensure new employees have limited access to AWS and can only launch pre-defined CloudFormation stacks. How should you implement this?
   * A. Create an AWS Organization & use an SCP
   * B. Create a Stack Policy
   * C. Use Service Catalog
   * D. Create a Lambda function for each CloudFormation stack that will be invoked by your new employees to deploy stacks
5) You would like to deploy updates to your Windows instances using SSM. What do you recommend doing? 
   * A. In a maintenance windows, use the AWS-RunPatchBaseline command & the AWS-WindowsDefaultPatchBaseline patch baseline
   * B. In a maintenance window, use the AWS-WindowsRunPatchBaseline command & the AWS-WindowsDefaultPatchBaseline patch baseline
   * C. In a maintenance window, use the AWS-WindowsRunPatchBaseline command & the AWS-DefaultPatchBaseline patch baseline
   * D. In a maintenance window, use the AWS-RunPatchBaseline command & the AWS-DefaultPatchBaseline patch baseline
* [Answers](https://i.imgur.com/z1qCCyl.png)
* Score: 
  * [7-12-2020 PM] = 3/5 = 60%
