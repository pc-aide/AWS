# Quiz 02 - 65x questions

## Time
* 2h10m

## To pass
* 72%

## Questions
1. An organization has offices across multiple locations and the technology team has configured an ALB  across targets in multiple AZs. The team wants to analyze the incoming requests for latencies and the client's IP address patterns.<br/>Which feature of the Load Balancer will help collect the required information?
      * A. CloudWatch metrics
      * B. ALB access logs
      * C. CloudTrail logs
      * D. ALB request tracing
2. You are a developer for a web application written in .NET which uses the AWS SDK. You need to implement an authentication mechanism that returns a JWT (JSON Web Token).<br/>Which AWS service will help you with token handling and management?
      * A. Cognito Identity Pools
      * B. Cognito User Pools 
      * C. Cognito Sync
      * D. API Gateway
3. A media company has created a video streaming application and it would like their Brazilian users to be served by the company's Brazilian servers. Other users around the globe should not be able to access the servers through DNS queries.<br/>Which Route 53 routing policy meets this requirement?
      * A. Geolocation
      * B. Weighted
      * C. Latency
      * D. Latency
      * E. Failover
4. A developer has just completed configuring the ALB for the EC2 instances. Just as he started testing his configuration, he realized that he has missed assigning target groups to his ALB.<br/>Which error code should he expect in his debug logs?
      * A. HTTP 403
      * B. HTTP 504
      * C. HTTP 503
      * D. HTTP 500
5. A company is looking at optimizing their Amazon EC2 instance costs. Few instances are sure to run for a few years, but the instance type might change based on business requirements.<br/>Which EC2 instance purchasing option should they opt to meet the reduced cost criteria?
      * A. Convertible Reserved instance
      * B. Scheduled Reserved instances
      * C. Elastic Reserved instances
      * D. Standard Reserved instances
6. The Technical Lead of your team has reviewed a CloudFormation YAML template written by a new recruit and specified that an invalid section has been added to the template.<br/>Which of the following represents an invalid section of the CloudFormation template?
      * A. 'Conditions' section of the template
      * B. 'Resources' section of the template
      * C. 'Parameters' section of the template
      * D. 'Dependencies' section of the template
7. You are running workloads on AWS and have embedded RDS database connection strings within each web server hosting your applications. After failing a security audit, you are looking at a different approach to store your secrets securely and automatically rotate the database credentials.<br/>Which AWS service can you use to address this use-case?
      * A. KMS
      * B. Secrets Manager
      * C. Systems Manager
      * D. SSM Parameter Store
8. As an AWS Certified Developer Associate, you have configured the AWS CLI on your workstation. Your default region is us-east-1 and your IAM user has permissions to operate commands on services such as EC2, S3 and RDS in any region. You would like to execute a command to stop an EC2 instance in the us-east-2 region.<br/>What of the following is the MOST optimal solution to address this use-case?
      * A. Use the --region parameter
      * B. You need to override the default region by using aws configure
      * C. Use boto3 dependency injection
      * D. You should create a new IAM user just for that other region
9. You have deployed a Java application to an EC2 instance where it uses the X-Ray SDK. When testing from your personal computer, the application sends data to X-Ray but when the application runs from within EC2, the application fails to send data to X-Ray.<br/>Which of the following does NOT help with debugging the issue?
      * A. EC2 X-Ray Daemon
      * B. CloudTrail
      * C. X-Ray sampling
      * D. EC2 Instance Role
10. A developer has been asked to create a web application to be deployed on EC2 instances. The developer just wants to focus on writing application code without worrying about server provisioning, configuration and deployment.<br/>As a Developer Associate, which AWS service would you recommend for the given use-case?
      * A. Elastic Beanstalk
      * B. SAM
      * C. CodeDeploy
      * D. CloudFormation
11. The development team at an IT company would like to provision their own Docker images that can be used as input sources for CodeBuild. These images will contain cached dependencies as well as special tooling for builds that are proprietary to the company.<br/>Which of the following services can be used to store and deploy these Docker images?
      * A. ECS
      * B. S3
      * C. EBS
      * D. ECR
12. As an AWS Certified Developer Associate, you been asked to create an AWS Elastic Beanstalk environment to handle deployment for an application that has high traffic and high availability needs. You need to deploy the new version using Beanstalk while making sure that performance and availability are not affected.<br/>Which of the following is the MOST optimal way to do this while keeping the solution cost-effective?
      * A. Deploy using 'Immutable' deployment policy
      * B. Deploy using 'All at once' deployment policy
      * C. Deploy using 'Rolling with additional batch' deployment policy
      * D. Deploy using 'Rolling' deployment policy
13. Which of the following best describes how KMS Encryption works?
      * A. KMS generates a new CMK for each Encrypt call & encrypts the data with it
      * B. KMS receives CMK from the client at every Encrypt call, & encrypts the data with that
      * C. KMS sends the CMK to the client, which performs the encryption & then deletes the CMK
      * D. KMS stores the CMK, & receives data from the clients, which it encrypts & sends back
14. A Developer has been entrusted with the job of securing certain S3 buckets that are shared by a large team of users. Last time, a bucket policy was changed, the bucket was erroneously available for everyone, outside the organization too.<br/>Which feature/service will help the developer identify similar security issues with minimum effort?
      * A. Access Advisor feature on IAM console
      * B. S3 Object Lock
      * C. S3 Analytics
      * D. IAM Access Analyzer
15. A firm runs its technology operations on a fleet of Amazon EC2 instances. The firm needs a certain software to be available on the instances to support their daily workflows. The developer team has been told to use the user data feature of EC2 instances.<br/>Which of the following are true about the user data EC2 configuration? (**Select two**)
      * A. By default, user data is executed every time an EC2 instance is re-started
      * B. Be default, scripts entered as user data executed with root user privileges
      * C. By default, user data runs only during the boot cycle when you first launch an instance
      * D. Be default, scripts entered as user data don't have root user privileges for executing
16. You have created an Elastic Load Balancer that has marked all the EC2 instances in the target group as unhealthy. Surprisingly, when you enter the IP address of the EC2 instances in your web browser, you can access your website.<br/>What could be the reason your instances are being marked as unhealthy? (**Select two**)
      * A. Your web-app has runtime that is not supported by the ALB
      * B. The EBS volumes have been improperly mounted
      * C. You need to attach IP to the EC2 instances
      * D. The SG of the EC2 instance does not allow for traffic from the SG of the ALB
      * E. The route for the health check is misconfigured
17. An IT company is configuring Auto Scaling for its Amazon EC2 instances spread across different AZs and Regions.<br/>Which of the following scenarios are NOT correct about EC2 Auto Scaling? (**Select two**)
      * A. ASGs that span across multiple Region need to be enabled for all the Regions specified
      * B. an ASG can contain EC2 instances in one or more AZs within the same Region
      * C. An ASG can contain EC2 instances in only one AZ of a Region
      * D. Amazon EC2 Auto Scaling attempts to distribute instances evenly between the AZs that enabled for your ASG
      * E. For ASGs in a VPC, the EC2 instances are launched in subnets
18. The manager at an IT company wants to set up member access to user-specific folders in an Amazon S3 bucket - `bucket-a`. So, user x can only access files in his folder - `bucket-a/user/user-x/` and user y can only access files in her folder - `bucket-a/user/user-y/` and so on.<br/>As a Developer Associate, which of the following IAM constructs would you recommend so that the policy snippet can be made generic for all team members and the manager does not need to create separate IAM policy for each team member?
      * A. IAM policy principal
      * B. IAM policy condition
      * C. IAM policy resource
      * D. IAM policy variables
19. You're a developer doing contract work for the media sector. Since you work alone, you opt for technologies that require little maintenance, which allows you to focus more on your coding. You have chosen AWS Elastic Beanstalk to assist with the deployment of your applications. While reading online documentation you find that Elastic Beanstalk relies on another AWS service to provision your resources.<br/>Which of the following represents this AWS service?
      * A. CloudFormation
      * B. Systems Manager
      * C. CodeCommit
      * D. CodeDeploy
20. The development team at an IT company has configured an ALB with a Lambda function A as the target but the Lambda function A is not able to process any request from the ALB. Upon investigation, the team finds that there is another Lambda function B in the AWS account that is exceeding the concurrency limits.<br/>How can the development team address this issue?
      * A. Use a CloudFront Distribution instead of an ALB for Lambda function A
      * B. Set up provioned concurrency for the Lambda function B so that it throttles if it goes above a certain concurrency limit
      * C. Use an API Gateway instead of an ALB for Lambda function A
      * D. Set up reserved concurrency for the Lambda function B so that it throttles if it goes above a certain concurrency limit
21. To enable HTTPS connections for his web application deployed on the AWS Cloud, a developer is in the process of creating server certificate.<br/>Which AWS entities can be used to deploy SSL/TLS server certificates? (**Select two**)
      * A. ACM
      * B. AWS Secrets Manager
      * C. AWS Systems Manager
      * D. AWS CloufFormation
      * E. IAM
22. A SaaS company runs a HealthCare web application that is used worldwide by users. There have been requests by mobile developers to expose public APIs for the application-specific functionality. You decide to make the APIs available to mobile developers as product offerings.<br/>Which of the following options will allow you to do that?
      * A. Use AWS Billing Usage Plans
      * B. Use AWS Lambda Custom Authorizers
      * C. Use API Gateway Usage Plans
      * D. Use CloudFront Usage Plans
23. Your company has stored all application secrets in SSM Parameter Store. The audit team has requested to get a report to better understand when and who has issued API calls against SSM Parameter Store.<br/>Which of the following options can be used to produce your report?
      * A. Use AWS CloudTrail to get a record of action taken by a user
      * B. Use SSM Parameter Store Access Logs in CloudWath Logs to get a record of actions taken by user
      * C. Use SSM Parameter Store List feature to get a record of actions taken by a user
      * D. Use SSM Parameter Store Access Logs in S3 to get a record of actions taken by a user
24. A data analytics company wants to use clickstream data for Machine Learning tasks, develop algorithms, and create visualizations and dashboards to support the business stakeholders. Each of these business units works independently and would need real-time access to this clickstream data for their applications.<br/>As a Developer Associate, which of the following AWS services would you recommend such that it provides a highly available and fault-tolerant solution to capture the clickstream events from the source and then provide a simultaneous feed of the data stream to the consumer applications?
      * A. AWS Kinesis Data Streams
      * B. Amazon SQS
      * C. AWS Kinesis Data Analytics
      * D. AWS Kinesis Data Firehose
25. A multi-national company has just moved to AWS Cloud and it has configured forecast-based AWS Budgets alerts for cost management. However, no alerts have been received even though the account and the budgets have been created almost three weeks ago.<br/>What could be the issue with the AWS Budgets configuration?
      * A. Budget forecast has been created from an account that does not have enough privileges
      * B. Account has to be part of AWS Organizations to receive AWS Budgets alerts
      * C. Amazon CloudWatch could be down & hence alerts are not being sent
      * D. AWS requires approximately 5 weeks of usage data to generate budget forecasts
26. A development team at a social media company uses AWS Lambda for its serverless stack on AWS Cloud. For a new deployment, the Team Lead wants to send only a certain portion of the traffic to the new Lambda version. In case the deployment goes wrong, the solution should also support the ability to roll back to a previous version of the Lambda function, with MIMINUM downtime for the application.<br/>As a Developer Associate, which of the following options would you recommend to address this use-case?
      * A. Set up the application to use an alias that points to the current version. Deploy the new version of the code & configure alias to send all users to this new version. If the deployment goes wrong, reset the alias to point ot the current version
      * B. Set up the application to use an alias that points to the current version. Deploy the new version of the code & configure the alias to send 10% of the users to tthis new version. If the deployment goes wrong, reset the alias to point all traffic to the current version
      * C. Set up the application to directly deploy the new Lambda version. If the deployment goes wrong, reset the application back to rhe current version using the version number in the ARN
      * D. Set up the application to have multiple alias of the Lambda function. Deploy the new version of the code. Configure a new alias that points to the current alias of the Lambda function for handling 10% of the traffic. If the deployment goes wrong, reset the new alias to point all traffic to the most recent working alias of the Lambda function
27. The development team has just configured and attached the IAM policy needed to access AWS Billing and Cost Management for all users under the Finance department. But, the users are unable to see AWS Billing and Cost Management service in the AWS console.<br/>What could be the reason for this issue?
      * A. Only root user has access to AWS Billing & Cost Management console
      * B. IAM user should be created under AWS Billing & Cost Management & not under AWS account to have access to Billing console
      * C. The users might have another policy that restricts them from accessing the Billing information
      * D. You need to active IAM user access to the Billing & Cost Management console for all the users who need access
28. Which of the following security credentials can only be created by the AWS Account root user?
      * A. EC2 Instance Key Pairs
      * B. CloudFront Key Pairs
      * C. IAM User passwords
      * D. IAM User Access Keys
29. The development team at a company creates serverless solutions using AWS Lambda. Functions are invoked by clients via AWS API Gateway which anyone can access. The team lead would like to control access using a 3rd party authorization mechanism.<br/>As a Developer Associate, which of the following options would you recommend for the given use-case?
      * A. Lambda Authorizer
      * B. Cognito User Pools
      * C. API Gateway User Pools
      * D. IAM permissions with sigv4
30. The development team at an e-commerce company wants to run a serverless data store service on two docker containers using shared memory.<br/>Which of the following ECS configurations can be used to facilitate this use-case?
      * A. Put the two containers into a single task definition using an EC2 Launch Type
      * B. Put the two containers into two seperate task definition using a Fargate Launch Type
      * C. Put the two containers into two separate task defintions using an EC2 Launch Type
      * D. Put the two containers into a single task defintion using a Fargate Launch Type
31. A developer at a company is trying to create a digital signature for SSH'ing into the Amazon EC2 instances.<br/>Which of the following entities can be used to facilitate this use-case?
      * A. MFA
      * B. Access Keys
      * C. Root user credentials
      * D. Key pairs
32. A financial services company is undergoing a compliance audit by the regulator. The company has hundreds of IAM users that make API calls but specifically it needs to be determined who is making KMS API calls.<br/>Which of the following services should the audit team use?
      * A. CloudTrail
      * B. CloudWatch Metrics
      * C. X-Ray
      * D. Config
33. A retail company manages its IT infrastructure on AWS Cloud via Elastic Beanstalk. The development team at the company is planning to deploy the next version with MINIMUM application downtime and the ability to rollback quickly in case deployment goes wrong.<br/>As a Developer Associate, which of the following options would you recommend to the development team?
      * A. Deploy the new version to a separate environment via Blue/Green Deployment, & thw swap Route 53 records of the two environments to redirect traffic to the new version
      * B. Deploy the new application version using 'Rolling' deployment policy
      * C. Deploy the new application version using 'All at once' deployment policy
      * D. Deploy the new application version using 'Rolling with additional batch' deployment policy
34. Your company has configured AWS Organizations to manage multiple AWS accounts. Within each AWS account, there are many CloudFormation scripts running. Your manager has requested that each script output the account number of the account the script was executed in.<br/>Which Pseudo parameter will you use to get this information?
      * A. AWS::Region
      * B. AWS::NoValue
      * C. AWS::AcountId
      * D. AWS::StackName
35. A developer in your company has configured a build using AWS CodeBuild. The build fails and the developer needs to quickly troubleshoot the issue to see which commands or settings located in the BuildSpec file are causing an issue.<br/>Which approach will help them accomplish this?
      * A. Freeze the CodeBuild during its next execution
      * B. SSH into the CodeBuild Docker container
      * C. Run AWS CodeBuild locally
      * D. Enable detailed monitoring
36. In addition to regular sign-in credentials, AWS supports MFA for accounts with privileged access.<br/>Which of the following MFA mechanisms is NOT for root user authentication?
      * A. SMS text message-based MFA
      * B. Hardware MFA device
      * C. U2F Security Key
      * D. Virtual MFA devices
37. You have chosen AWS Elastic Beanstalk to upload your application code and allow it to handle details such as provisioning resources and monitoring.<br/>When creating configuration files for AWS Elastic Beanstalk which naming convention should you follow?
      * A. `.ebextensions_<mysettings>.config`
      * B. `.config_<mysettings>.ebextensions`
      * C. `.ebextensions/<mysettings>.config`
      * D. `.config/<mysettings>.ebextensins`
38. A development team lead is responsible for managing access for her IAM principals. At the start of the cycle, she has granted excess privileges to users to keep them motivated for trying new things. She now wants to ensure that the team has only the minimum permissions required to finish their work.<br/>Which of the following will help her identify unused IAM roles and remove them without disrupting any service? 
      * A. AWS Trusted Advisor
      * B. Access Advisor feature on IAM console
      * C. IAM Access Analyzer
      * D. Amazon Inspector
39. An IT company has a HealthCare application with data security requirements such that the encryption key must be stored in a custom application running on-premises. The company wants to offload the data storage as well as the encryption process to Amazon S3 but continue to use the existing encryption keys.<br/>Which of the following S3 encryption options allows the company to leverage Amazon S3 for storing data with given constraints?
      * A. Server-Side Encryption with Amazon S3-Managed Keys (SSE-S3)
      * B. Server-Side Encryption with CMKs Stored in AWS SSE-KMS
      * C. Client-Side Encryption with data encryption is done on the client-side before sending it to Amazon S3
      * D. Server-Side Encryption with Customer-Provided Keys (SSE-C)
40. An application is hosted by a 3rd party and exposed at yourapp.3rdparty.com. You would like to have your users access your application using www.mydomain.com, which you own and manage under Route 53.<br/>What Route 53 record should you create?
      * A. Create an Alias record
      * B. Create a CNAME record
      * C. Create an A record
      * D. Create a PTR record
41. A company uses Elastic Beanstalk to manage its IT infrastructure on AWS Cloud and it would like to deploy the new application version to the EC2 instances. When the deployment is executed, some instances should serve requests with the old application version, while other instances should serve requests using the new application version until the deployment is completed.<br/>Which deployment meets this requirement without incurring additional costs?
      * A. All at once
      * B. Rolling with additonal batches
      * C. Immutable
      * D. Rolling
42. An E-commerce business, has its applications built on a fleet of Amazon EC2 instances, spread across various Regions and AZs. The technical team has suggested using Elastic Load Balancer for better architectural design.<br/>What characteristics of an Elastic Load Balancer make it a winning choice? (Select two)
      * A. Build a HA system
      * B. Improve vertical scalability of the system
      * C. Deploy EC2 instances across multiple AWS Regions
      * D. Separate public traffic from private traffic
      * E. The LB communicates with the underlying EC2 instances using their pulbic IPs
43. As an AWS Certified Developer Associate, you are given a document written in YAML that represents the architecture of a serverless application. The first line of the document contains `Transform: 'AWS::Serverless-2016-10-31'`.<br/>What does the Transform section in the document represent?
      * A. Presence of `Transform` section indicates it is a SAM template
      * B. Presence of `Transform` section indicates it is a CloudFormation Parameter
      * C. It represents an intrisinc funtion
      * D. It represents a Lambda function definition
44. An e-commerce company has a fleet of EC2 based web servers running into very high CPU utilization issues. The development team has determined that serving secure traffic via HTTPS is a major contributor to the high CPU load.<br/>Which of the following steps can take the high CPU load off the web servers? (**Select two**)
      * A. Create an HTTP listener on the ALB with SSL termination
      * B. Create an HTTPS listener of the ALB with SSL termination
      * C. Configure an SSL/TLS certificate on an ALB via ACM
      * D. Create an HTTP listener on the ALB with SSL pass-through
      * E. Create an HTTPS listener on the ALB with SSL pass-trhough
45. A cybersecurity firm wants to run their applications on single-tenant hardware to meet security guidelines.<br/>Which of the following is the MOST cost-effective way of isolating their Amazon EC2 instances to a single tenant?
      * A. On-Deman Instances
      * B. Dedicated Hosts
      * C. Spot Instances
      * D. Dedicated Instances
46. An organization has hosted its EC2 instances in two AZs. AZ<sup>1</sup> has two instances and AZ<sup>2</sup> has 8 instances. The Elastic Load Balancer managing the instances in the two AZs has cross-zone load balancing enabled in its configuration.<br/>What percentage traffic will each of the instances in AZ1 receive?
      * A. 25
      * B. 10
      * C. 20
      * D. 15
47. Your global organization has an IT infrastructure that is deployed using CloudFormation on AWS Cloud. One employee, in us-east-1 Region, has created a stack 'Application1' and made an exported output with the name 'ELBDNSName'. Another employee has created a stack for a different application 'Application2' in us-east-2 Region and also exported an output with the name 'ELBDNSName'. The first employee wanted to deploy the CloudFormation stack 'Application1' in us-east-2, but it got an error. What is the cause of the error?
      * A. Output Values in CloudFormation must have unique names within a single Region
      * B. Exported Output Values in CloudFormation must have unique names across all Regions
      * C. Output Values in CloudFormation must have unique names across all Reggions
      * D. Exported Output Values in CloudFormation must have unique names within a single Region
48. CodeCommit is a managed version control service that hosts private Git repositories in the AWS cloud.<br/>Which of the following credential types is NOT supported by IAM for CodeCommit?
      * A. Git credentials
      * B. IAM username & password
      * C. SSH Keys
      * D. AWS Access Keys
49. A company has hired you as an AWS Certified Developer Associate to help with redesigning a real-time data processor. The company wants to build custom applications that process and analyze the streaming data for its specialized needs.<br/>Which solution will you recommend to address this use-case?
      * A. Use SQS to process the data streams as well as decouple the producers & consumers for the real-time data processor
      * B. Use Kinesis Data Firehose to process the data streams as well as decouple the producers & consumers for the real-time data processor
      * C. Use SNS process the data streams as well as decouple the producers & consumers for the real-time data processor
      * D. Use Kinesis Data Streams to process the data streams as well as decouple the producers & consumers for the real-time data processor
50. You have created a Java application that uses RDS for its main data storage and ElastiCache for user session storage. The application needs to be deployed using Elastic Beanstalk and every new deployment should allow the application servers to reuse the RDS database. On the other hand, user session data stored in ElastiCache can be re-created for every deployment.<br/>Which of the following configurations will allow you to achieve this? (**Select two**)
      * A. RDS db defined in `.ebextensions/`
      * B. RDS db defined externally & referenced through environment variables
      * C. ElastiCache defined in `.ebextensions/`
      * D. ElastiCache bundled with the application source code
      * E. ElastiCache db defined externally & referenced through environment variables
51. You're a developer working on a large scale order processing application. After developing the features, you commit your code to AWS CodeCommit and begin building the project with AWS CodeBuild before it gets deployed to the server. The build is taking too long and the error points to an issue resolving dependencies from a third-party. You would like to prevent a build running this long in the future for similar underlying reasons.<br/>Which of the following options represents the best solution to address this use-case?
      * A. Use AWS Lambda
      * B. Enable CodeBuild timeout
      * C. Use AWS CloudWatch Events
      * D. Use VPC Flow Logs
52. The development team at an IT company wants to make changes to a current application written in Node.js and deployed on a Linux server. The team lead would like to decouple the application into microservices, package the application to a Docker container which is then run on the AWS infrastructure.<br/>Which AWS service is best suited for this change?
      * A. ECS
      * B. Step Functions
      * C. Lambda
      * D. ECR
53. A Developer at a company is working on a CloudFormation template to set up resources. Resources will be defined using code and provisioned based on certain conditions.<br/>Which section of a CloudFormation template does not allow for conditions? 
      * A. Parameters
      * B. Resources
      * C. Conditions
      * D. OUtputs
54. A development team lead is configuring policies for his team at an IT company.<br/>Which of the following policy types only limit permissions but cannot grant permissions (**Select two**)?
      * A. ACL
      * B. Identity-based policy
      * C. Resource-based policy
      * D. Permissions boundary
      * E. AWS Organizations Service Control Policy (SCP)
55. You are creating a Cloud Formation template to deploy your CMS application running on an EC2 instance within your AWS account. Since the application will be deployed across multiple regions, you need to create a map of all the possible values for the base AMI.<br/>How will you invoke the !FindInMap function to fulfill this use case?
      * A. `!FindInMap [ MapName, TopLevelKey, SecondLevelKey, ThirdLevelKey ]`
      * B. `!FindInMap [ MapName ]`
      * B. `!FinInMap [ MapName, TopLevelKey ]`
      * C. `!FindInMap [ MapName, TopLevelKey, SecondLevelKey ]`
56. You are a developer working on AWS Lambda functions that are invoked via REST API's using Amazon API Gateway. Currently, when a GET request is invoked by the consumer, the entire data-set returned by the Lambda function is visible. Your team lead asked you to format the data response.<br/>Which feature of the API Gateway can be used to solve this issue?
     * A. Use an API Gateway Stage variable
     * B. Use API Gateway Mapping Templates
     * C. Use a Lambda custom interceptor
     * D. Deploy an interceptor shell script
57. A multi-national company has multiple business units with each unit having its own AWS account. The development team at the company would like to debug and trace data across accounts and visualize it in a centralized account.<br/>As a Developer Associate, which of the following solutions would you suggest for the given use-case?
     * A. CloudTrail
     * B. VPC Flow Logs
     * C. CloudWatch Events
     * D. X-Ray
58. The development team at a retail organization wants to allow a Lambda function in its AWS Account A to access a DynamoDB table in another AWS Account B.<br/>As a Developer Associate, which of the following solutions would you recommend for the given use-case?
     * A. Create a clone of the Lambda function in AWS Account B so that it can access the DynamoDB table in the same account
     * B. Create an IAM in Account B with access to DynamoDB. Modify the trust policy of the role in Account B to allow the execution role of Lambda to assume this role. Update the Lambda function code to add the AssumeRole API call
     * C. Add a resource policy to the DynamoDB table in AWS Account B to give access to the Lambda function in Account A
     * D. Create an IAM role in Account B with access to DynamoDB. Modify the trust policy of the execution role in Account A to allow the execution role of Lambda to assume the IAM role in Account B. Update the Lambda function code to add the AssumeRole API call
59. A developer has been asked to create an application that can be deployed across a fleet of EC2 instances. The configuration must allow for full control over the deployment steps using the blue-green deployment.<br/>Which service will help you achieve that?
     * A. CodeBuild
     * B. CodePipeline
     * C. CodeDeploy
     * D. EB
60. The development team at an IT company uses CloudFormation to manage its AWS infrastructure. The team has created a network stack containing a VPC with subnets and a web application stack with EC2 instances and an RDS instance. The team wants to reference the VPC created in the network stack into its web application stack.<br/>As a Developer Associate, which of the following solutions would you recommend for the given use-case?
     * A. Create a cross-stack reference & use the Outputs output filed to flag the value of VPC from the network stack. Then use Fn::ImportValue intrinsic function to import the value of VPC into the web application stack
     * B. Create a cross-stack reference & use the Export output filed to flag to value of VPC from the network stack. Then use Ref intrinsic function to reference the value of VPC into the web application stack
     * C. Create a cross-stack reference & use the Outputs output filed to flag the value of VPC from the network stack. Then Ref intrinsic function to reference the value of VPC into the web application stack
     * D. Create a cross-stack reference & use the Export output field to flag the value of VPC from the network stack. Then use Fn::ImportValue intrinsic function to import the value of VPC into the web application stack
61. A video encoding application running on an EC2 instance takes about 20 seconds on average to process each raw footage file. The application picks the new job messages from an SQS queue. The development team needs to account for the use-case when the video encoding process takes longer than usual so that the same raw footage is not processed by multiple consumers.<br/>As a Developer Associate, which of the following solutions would you recommend to address this use-case?
     * A. Use ChangeMessageVisibility action to extend a message's visibility timeout
     * B. Use DelaySeconds action to delay a message's visibility timeout
     * C. Use WaitTimeSeconds action to short poll & extend a message's visibility timeout
     * D. Use WaitTimeSeconds action to long poll & extend a message's visibility timeout
62. A photo-sharing application manages its EC2 server fleet running behind an Application Load Balancer and the traffic is fronted by a CloudFront distribution. The development team wants to decouple the user authentication process for the application so that the application servers can just focus on the business logic.<br/>As a Developer Associate, which of the following solutions would you recommend to address this use-case with minimal development effort?
     * A. Use Cognito Authentication via Cognito Identity Pools for your ALB
     * B. Use Cognito Authentication via Cognito User Pools for your ALB
     * C. Use Cognito Authentication via Cognito User Pools for your CloudFront distribution
     * D. Use Cognito Authentication via Cognito Identity Pools for your CloudFront distribution
63. As part of his development work, an AWS Certified Developer Associate is creating policies and attaching them to IAM identities. After creating necessary Identity-based policies, he is now creating Resource-based policies.<br/>Which is the only resource-based policy that the IAM service supports?
     * A. AWS Organization Service control Policies (SCP)
     * B. Trust policy
     * C. Permissions boundary
     * D. ACL
64. A startup with newly created AWS account is testing different EC2 instances. They have used Burstable performance instance - T2.micro - for 35 seconds and stopped the instance.<br/>At the end of the month, what is the instance usage duration that the company is charged for?
     * A. 0 seconds
     * B. 30 seconds
     * C. 60 seconds.
     * D. 35 seconds.
65. You are a developer in a manufacturing company that has several servers on-site. The company decides to move new development to the cloud using serverless technology. You decide to use the AWS SAM and work with an AWS SAM template file to represent your serverless architecture.<br/>Which of the following is NOT a valid serverless resource type?
     * A. AWS::Serverless::Function
     * B. AWS::Serverless::SimpleTable
     * C. AWS::Serverless::UserPool
     * D. AWS::Serverless::Api
* [Answers](https://i.imgur.com/v8BtBiF.png)
* Score:
    * [28-10-2020 AM] 44/65 = 67%
    * [31-10-2020 PM] 60/65 = 92%

