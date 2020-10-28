# Quiz 01 - 65x questions

## Time
* 2h10min

## Pass
* 72%

## Questions
1. The development team at a retail organization wants to allow a Lambda function in its AWS Account A to access a DynamoDB table in another AWS Account B.<br/>As a Developer Associate, which of the following solutions would you recommend for the given use-case?
   * A. Create a clone of the Lambda function in AWS Account B so that it can access the DynamoDB table in the same account
   * B. Create an IAM role in Account B with access to DynamoDB. Modify the trust policy of the execution role in Account A to allow the execution role of Lambda to assume the IAM role in Account B. Update the Lambda function code to add the AssurmeRole API call
   * C. Create an IAM in Account B with Access to DynamoDB. Modify the trust policy of the role in Account B to allow the exeution role of Lambda to assume this role Update the Lambda function code to add the AssumeRole API call
   * D. Add a ressouce poly to the DynamoDB table in AWS Account B to give access to the Lambda function in Account A
   
2. A multi-national enterprise uses AWS Organizations to manage its users across different divisions. Even though CloudTrail is enabled on the member accounts, managers have noticed that access issues to CloudTrail logs across different divisions and AWS Regions is becoming a bottleneck in troubleshooting issues. They have decided to use the organization trail to keep things simple.<br/>
What are the important points to remember when configuring an organization trail? (**Select two**)
   * A. Member accounts will be able to see the Organization trail, but can't modify or delete it
   * B. By default, CloudTrail event log files are not encrypted
   * C. Member accounts don't have access to organization trail, neither do they have access to the Amazon S3 bucket that logs the files
   * D. By default, CloudTrail tracks only bucket-level actions. To tracks object-level action, you need to enable Amazon S3 data events
   * E. There is nothing called Organization trail. The master account can, however, enable CloudTrail logging, to keep track of all activities acroos AWS accounts
3. A cyber forensics application, running behind an ALB, wants to analyze patterns for the client IPs.<br/>Which of the following headers can be used for this requirement?
   * A. X-Forwarded-Port
   * B. X-Forwarded-For
   * C. X-Forwarded-IP
   * D. X-Forwarded-Proto
4. A developer at a university is encrypting a large XML payload transferred over the network using AWS KMS and wants to test the application before going to production.<br/>What is the maximum data size supported by AWS KMS?
   * A. 16KB
   * B. 10MB
   * C. 4KB
   * D. 1MB
5. A video encoding application running on an EC2 instance takes about 20 seconds on average to process each raw footage file. The application picks the new job messages from an SQS queue. The development team needs to account for the use-case when the video encoding process takes longer than usual so that the same raw footage is not processed by multiple consumers.<br/>As a Developer Associate, which of the following solutions would you recommend to address this use-case?
   * A. Use ChangeMessageVisibility action to extend a message's visibility timeout
   * B. Use WaitTimeSeconds action to long poll & extend a message's visibility timeout
   * C. Use WaitTimeSeconds action to hosrt poll & extend a message's visibility timeout
   * D. Use DelaySecond action to dely a message's visibility timeout
6. As an AWS Certified Developer Associate, you have been hired to consult with a company that uses the NoSQL database for mobile applications. The developers are using DynamoDB to perform operations such as GetItem but are limited in knowledge. They would like to be more efficient with retrieving some attributes rather than all.<br/>Which of the following recommendations would you provide?
   * A. Specify a ````ProjectionExpression````
   * B. Use the ````--query```` parameter
   * C. Use a ````Scan````
   * D. Use a ````FilterEpression````
7. As a site reliability engineer, you are responsible for improving the company’s deployment by scaling and automating applications. As new application versions are ready for production you ensure that the application gets deployed to different sets of EC2 instances at different times allowing for a smooth transition.<br/>Using AWS CodeDeploy, which of the following options will allow you to do this?
   * A. CodeDeploy Agent
   * B. CodeDeploy Deployment Groups
   * C. Define multiple CodeDeploy Applications
   * D. CodeDeploy Hooks
8. A development team at a social media company uses AWS Lambda for its serverless stack on AWS Cloud. For a new deployment, the Team Lead wants to send only a certain portion of the traffic to the new Lambda version. In case the deployment goes wrong, the solution should also support the ability to roll back to a previous version of the Lambda function, with MIMINUM downtime for the application. <br/>As a Developer Associate, which of the following options would you recommend to address this use-case?
   * A. Set up the application to use an alias that points to the current version. Deploy the new version of the code & configure the alias to send 10% of the users to this new version. If the deployment goes wrong, reset the alias to point all traffic to the current version
   * B. Set up the application to directly deploy the new Lambda version. If the deployement goes wrong, reset the application back to te current version using the version number in the ARN
   * C. Setup the application to use an alias that points to the current version. Deploy the new version of the code & configure alias to send all users to this new version. If the deployment goes wrong, reset the alias to point the current version
   * D. Setup the application to have multiple alias of the Lambda function. Deploy the new version of the code. Cofnigure a new alias that points to the current alias of the Lambda function for handling 10% of the traffic. If the deployment goes wrong, reset the new alias to point all the traffic to the most recent working alias of the Lambda function
9. You are working for a technology startup building web and mobile applications. You would like to pull Docker images from the ECR repository called demo so you can start running local tests against the latest application version. <br/>Which of the following commands must you run to pull existing Docker images from ECR? (**Select two**)
   * A. ````$(aws ecr get-login --no-include-email)````
   * B. ````aws docker pus1234567890.dkr.ecr.eu-west-1.amazonaws.com/demo:latest````
   * C. ````docker build -t 1234567890.dkr.ecr.eu-west-1.amazonaws.com/demo:latest````
   * D. ````docker pull 1234567890.dkr.ecr.eu-west-1.amazonaws.com:latest````
   * C. ````docker login -u $AWS_ACCESS_KEY_ID -p $AWS_SECRET_ACCESS_KEY````
10. You work as a developer doing contract work for the government on AWS gov cloud. Your applications use Amazon SQS for its message queue service. Due to recent hacking attempts, security measures have become stricter and require you to store data in encrypted queues. <br/>Which of the following steps can you take to meet your requirements without making changes to the existing code?
    * A. Enable SQS KMS Encryption
    * B. Use Client side encryption
    * C. Use Secret Manager
    * D. Use the SSL endpoint
11. Your company has embraced cloud-native microservices architectures. New applications must be dockerized and stored in a registry service offered by AWS. The architecture should support dynamic port mapping and support multiple tasks from a single service on the same container instance. All services should run on the same EC2 instance.<br/>Which of the following options offers the best-fit solution for the given use-case?
    * A. ALB + Beanstalk
    * B. CLB + Beanstalk
    * C. CLB + ECS
    * D. ALB + ECS
12. A photo-sharing application manages its EC2 server fleet running behind an Application Load Balancer and the traffic is fronted by a CloudFront distribution. The development team wants to decouple the user authentication process for the application so that the application servers can just focus on the business logic.<br/>As a Developer Associate, which of the following solutions would you recommend to address this use-case?
    * A. Use Cognito Authentication via Cognito User Pools for your CloudFront distribution
    * B. Use Cognito Authentication via Cognito Idenity Pools for your CloudFront distribution
    * C. Use Cognito Authentication via Cognito User Pools for your ALB
    * D. Use Cognito Authentication via Cognito Identity Pools for your ALB
13. You have migrated an on-premise SQL Server database to an Amazon Relational Database Service (RDS) database attached to a VPC inside a private subnet. Also, the related Java application, hosted on-premise, has been moved to an Amazon Lambda function.<br/>Which of the following should you implement to connect AWS Lambda function to its RDS instance?
    * A. Use Lambda layers to connect the internet & RDS separately
    * B. Use Env variables to pass in the RDS connection string
    * C. Configure lambda to connect to the public subnet that will give internet access & use SG to access RDS inside the privae subnet
    * D. Configure Lambda to connect to VPC with private subnet & SG needed to access RDS
14. The development team at an e-commerce company is preparing for the upcoming Thanksgiving sale. The product manager wants the development team to implement appropriate caching strategy on Amazon ElastiCache to withstand traffic spikes on the website during the sale. A key requirement is to facilitate consistent updates to the product prices and product description, so that the cache never goes out of sync with the backend.<br/>As a Developer Associate, which of the following solutions would you recommend for the given use-case?
    * A. Use a caching strategy to write to the backed first & then invalidate the cache
    * B. Use a caching stategy to update the cache & the backend at the same time
    * C. Use a caching strategy to write to the cache directly & sync the backend at a later time
    * D. Use a caching strategy to write to the backend first & wait for the cache to expire via TTL
15. A new recruit is trying to understand the nuances of EC2 Auto Scaling. As an AWS Certified Developer Associate, you have been asked to mentor the new recruit.<br/>Can you identify and explain the correct statements about Auto Scaling to the new recruit? (**Select two**).
    * A. Amazon EC2 Auto Scaling works with bot ALB & NLB
    * B. Every time your create an ASG from an existing instance, it creates a new AMI
    * C. You can't use Amazon EC2 Auto Scaling for health checks (to replcate unhealthy instances) if you are not using ELB
    * D. EC2 ASG are regional constructs. They span across AZs & regions
    * E. Amazon EC2 Auto Scaling can't add a volume to an existing instance if the existing volume is approaching capacity
16. A large firm stores its static data assets on Amazon S3 buckets. Each service line of the firm has its own AWS account. For a business use case, the Finance department needs to give access to their S3 bucket's data to the Human Resources department.<br/>Which of the below options is NOT feasible for cross-account access of S3 bucket objects?
    * A. Use Cross-account IAM roles for programmatic & console access to S3 bucket objects
    * B. Use IAM role & resource-based policies delegate access across accounts within different partitions via programmatic access only
    * C. Use Resource-based ACL & IAM policies for programmatic-only access to S3 bucket objects
    * D. Use Resource-based policies & AWS IAM policies for programmatic-only access to S3 bucket objects
17. A Developer is configuring Amazon EC2 Auto Scaling group to scale dynamically.<br/>Which metric below is NOT part of Target Tracking Scaling Policy?
    * A. ALBRequestCountPerTarget
    * B. ASGAverageNetworkOut
    * C. ApproximateNumberOfMessagesVisibles
    * D. ASGAverageCPUUtilization
18. A startup manages its Cloud resources with Elastic Beanstalk. The environment consists of few Amazon EC2 instances, an ASG, and an Elastic Load Balancer. Even after the Load Balancer marked an EC2 instance as unhealthy, the ASG has not replaced it with a healthy instance.<br/>As a Developer, suggest the necessary configurations to automate the replacement of unhealthy instance.
    * A. The ping path field of the LB is configured incorrectly
    * B. Health check parameters were configured for checking the instance health alone. The instance failed because of application failure which was not configured as a parameter for health check status
    * C. ASG doesn't automatically replcae the unhealthy instances marked by the LB. They have to be manually replaced from AWS Console
    * D. The health check type of your instance's ASG, must be changed from EC2 to ELB using a configuration file
19. ou are working for a shipping company that is automating the creation of ECS clusters with an Auto Scaling Group using an AWS CloudFormation template that accepts cluster name as its parameters. Initially, you launch the template with input value 'MainCluster', which deployed five instances across two availability zones. The second time, you launch the template with an input value 'SecondCluster'. However, the instances created in the second run were also launched in 'MainCluster' even after specifying a different cluster name.<br/>What is the root cause of this issue?
    * A. The cluster name Parameter has not been updated in the file /etc/ecs/ecs.config during bootstrap
    * B. The EC2 instance is missing IAM permissions to join the other clusters
    * C. The SGs on the EC2 instance are pointing to the wrong ECS cluster
    * D. The ECS agent Docker image must be re-built to connect to the other clusters
20. Your e-commerce company needs to improve its software delivery process and is moving away from the waterfall methodology. You decided that every application should be built using the best CI/CD practices and every application should be packaged and deployed as a Docker container. The Docker images should be stored in ECR and pushed with AWS CodePipeline and AWS CodeBuild.<br/>When you attempt to do this, the last step fails with an authorization issue. What is the most likely issue?
    * A. CodeBuild can't talk to ECR because of SG issues
    * B. The ECR repository is stale, you must delete & re-create it
    * C. The IAM permissions are wrong for the CodeBuild service
    * D. The ECS instances are misconfigured & must contain additional data in /etc/ecs/ecs.cofig
21. You are a developer handling a deployment service that automates application deployments to Amazon EC2 instances. Most of the deployments consist of code, but sometimes web and configuration files. One of your deployments failed and was rolled back by AWS CodeDeploy to the last known good application revision.<br/>During rollback which of the following instances did AWS CodeDeploy deploy first to?
    * A. To the new instance
    * B. You can't rollback a CodeDeploy deployment
    * C. To the failed instances
    * D. To the non-failed instances
22. A retail company manages its IT infrastructure on AWS Cloud via Elastic Beanstalk. The development team at the company is planning to deploy the next version with MINIMUM application downtime and the ability to rollback quickly in case deployment goes wrong.<br/>As a Developer Associate, which of the following options would you recommend to the development team?
    * A. Deploy the new version to a separate environment via Blue/Green Deployment, & then swap Route 53 records of the 2 envronments to redirect traffic to the new version
    * B. Deploy the new application version using 'Rolling' deployment policy
    * C. Deploy the new appliaction version suing 'Rolling with additional batch' deployment policy
    * D. Deploy the new application version using 'all at once' deployment policy
23. The development team at an e-commerce company wants to run a serverless data store service on two docker containers using shared memory.<br/>Which of the following ECS configurations can be used to facilitate this use-case?
    * A. Put the 2 containers into 2 separate task definitions using a fargate Launch Type
    * B. Put the 2 containers into a single task definition using an EC2 Lanch Type
    * C. Put the 2 containers ino a single task definition using a Fargate Lanch Type
    * D. Put the 2 containers ino 2 separate task definitions using an EC2 Lanch Type
24. Your company leverages Amazon CloudFront to provide content via the internet to customers with low latency. Aside from latency, security is another concern and you are looking for help in enforcing end-to-end connections using HTTPS so that content is protected.<br/>Which of the following options is available for HTTPS in AWS CloudFront?
    * A. Between clients & CloudFront only
    * B. Between clients & CloudFront as well as between CloudFront & backen
    * C. Neither between clients & CloudFront nor between CloudFront & backend
    * D. Between CloudFront & backend only
25. A popular mobile app retrieves data from an AWS DynamoDB table that was provisioned with RCU’s that are evenly shared across four partitions. One of those partitions is receiving more traffic than the other partitions, causing hot partition issues.<br/>What technology will allow you to reduce the read traffic on your AWS DynamoDB table with minimal effort?
    * A. ElastiCache
    * B. DynamoDB DAX
    * C. More partitions
    * D. DynamoDB Streams
26. An e-commerce company has a fleet of EC2 based web servers running into very high CPU utilization issues. The development team has determined that serving secure traffic via HTTPS is a major contributor to the high CPU load.<br/>Which of the following steps can take the high CPU load off the web servers? (**Select two**)
    * A. Configure an SSL/TLS certificate on an ALB via ACM
    * B. Create an HTTPS listener on the ALB with SSL pass-through
    * C. Create an HTTPS listener on the ALB with SSL termination
    * D. Create an HTTP listener on the ALB with SSL termination
27. A client has hired you as an AWS Certified Developer Associate for a consulting project. The client wants to weigh their options of choosing between an Amazon SQS standard queue and Amazon SWF.<br/>Which of the following statements are correct regarding the two services? (**Select two**)
    * A. SWF has task-oriented APIs & SQS has message-oriented APIs
    * B. SQS ensures the task is assigned only once while SWF may deliver the message multiple times
    * C. SQS has task-oriented APIs & SWF message-oriented APIs
    * D. SWS offer synchronous programming option whenreas SQS offers an asynchronous facility
    * E. SWF ensures the task is assigned only once while SQS may deliver the message multiple times
28. You are getting ready for an event to show off your Alexa skill written in JavaScript. As you are testing your voice activation commands you find that some intents are not invoking as they should and you are struggling to figure out what is happening. You included the following code ````console.log(JSON.stringify(this.event))```` in hopes of getting more details about the request to your Alexa skill.<br/>You would like the logs stored in an Amazon S3 bucket named ````MyAlexaLog````. How do you achieve this?
    * A. Use CloudWatch integration feature with S3
    * B. Use CloudWatch integration feature wih Lambda
    * C. Use CloudWatch feature with Kinesis
    * D. Use CloudWatch integration feature with Glue
29. You are planning to build a fleet of EBS-optimized EC2 instances to handle the load of your new application. Due to security compliance, your organization wants any secret strings used in the application to be encrypted to prevent exposing values as clear text.<br/>The solution requires that decryption events be audited and API calls to be simple. How can this be achieved? (**select two**) 
    * A. Audit using SSM Audit Trail
    * B. Store the secret as SecureString in SSM Parameter Store
    * C. Encrypt first with KMS then store in SSM Parameter store
    * D. Audit using CloudTrail
    * E. Store the secret as PlainText in SSM Parameter Store
30. Your web application front end consists of 5 EC2 instances behind an Application Load Balancer. You have configured your web application to capture the IP address of the client making requests. When viewing the data captured you notice that every IP address being captured is the same, which also happens to be the IP address of the Application Load Balancer.<br/>What should you do to identify the true IP address of the client?
    * A. Look into the X-Forwarded-For header in the backend
    * B. Look into the X-Forwarded-Proto header in the backend
    * C. Look into the client's cookie
    * D. Modify the front-end of the website so that the users send their IP in the requests
31. A company has a workload that requires 14,000 consistent IOPS for data that must be durable and secure. The compliance standards of the company state that the data should be secure at every stage of its lifecycle on all of the EBS volumes they use.<br/>Which of the following statements are true regarding data security on EBS?
    * A. EBS volumes support-in-flight-encryption but does not support encryption at rest
    * B. EBS volumes don't support any encryption
    * C. EBS volumes don't support in-flight encryption but do support encryption at rest using KMS
    * D. EBS volumes support in-flight encryption & encryption at rest using KMS
32. A developer from your team has configured the load balancer to route traffic equally between instances or across Availability Zones. However, ELB routes more traffic to one instance or Availability Zone than the others.<br/>Why is this happening and how can it be fixed? (**Select two**)
    * A. Sticky sessions are enabled for hte LB
    * B. Instances of a specific type aren't equally distributed across AZs
    * C. There could be short-lived TCP connections between clients & instances
    * D. After you didable an AZ, the targets in that AZ remain registered with the LB, thereby receiving random bursts of traffic
    * E. For ALB, cross-zone LB is disabled by default
33. A security company is requiring all developers to perform server-side encryption with customer-provided encryption keys when performing operations in AWS S3. Developers should write software with C# using the AWS SDK and implement the requirement in the PUT, GET, Head, and Copy operations.<br/>Which of the following encryption methods meets this requirement?
    * A. SSE-C
    * B. SSE-S3
    * C. SSE-KMS
    * D. Client-Side Encryption
34. AWS CloudFormation helps model and provision all the cloud infrastructure resources needed for your business.<br/>Which of the following services rely on CloudFormation to provision resources (**Select two**)?
    * A. AWS CodeBuild
    * B. AWS AutoScaling
    * C. AWS SAM
    * D. Lambda
    * E. AWS Elastic Beanstalk
35. Your company has been hired to build a resilient mobile voting app for an upcoming music award show that expects to have 5 to 20 million viewers. The mobile voting app will be marketed heavily months in advance so you are expected to handle millions of messages in the system. You are configuring Amazon SQS queues for your architecture that should receive messages from 20 KB to 200 KB.<br/>Is it possible to send these messages to SQS?
    * A. Yes, the max message size is 256KB
    * B. Yes, the max message size is 512KB
    * C. No, the max message size is 128KB
    * D. No, the max message size is 64KB
36. A company has AWS Lambda functions where each is invoked by other AWS services such as Amazon Kinesis Data Firehose, Amazon API Gateway, Amazon Simple Storage Service, or Amazon CloudWatch Events. What these Lambda functions have in common is that they process heavy workloads such as big data analysis, large file processing, and statistical computations.<br/>What should you do to improve the performance of your AWS Lambda functions without changing your code?
    * A. Increase the Lambda function timeout
    * B. Increase the RAM assigned to your Lambda function
    * C. Change the instance type for your Lambda function
    * D. Change your Lambda function runtime to use Golang
37. An ASG has a maximum capacity of 3, a current capacity of 2, and a scaling policy that adds 3 instances.<br/>When executing this scaling policy, what is the expected outcome?
    * A. Amazon EC2 Auto Scaling add 3 instance to the group
    * B. Amazon EC2 Auto Scaling does not add any instances to the group, but suggests changing the scaling policy to add one instance
    * C. Amazon EC2 Auto Scaling adds only 1 instance to the group
    * D. Amazon EC2 Auto Scaling adds 3 instances to the group & scales down 2 of those instances eventually
38. You were assigned to a project that requires the use of the AWS CLI to build a project with AWS CodeBuild. Your project's root directory includes the buildspec.yml file to run build commands and would like your build artifacts to be automatically encrypted at the end.<br/>How should you configure CodeBuild to accomplish this?
    * A. Specify a KMS key to use
    * B. Use in Flight encryption (SSL)
    * C. Use an AWS Lambda Hook
    * D. Use the AWS Encryption SDK
39. An IT company uses AWS CloudFormation templates to provision their AWS infrastructure for Amazon EC2, Amazon VPC, and Amazon S3 resources. Using cross-stack referencing, a developer creates a stack called ````NetworkStack```` which will export the ````subnetId```` that can be used when creating EC2 instances in another stack.<br/>To use the exported value in another stack, which of the following functions must be used?
    * A. ````!Sub````
    * B. ````!GetAtt````
    * C. ````!ImportValue````
    * D. ````!Ref````
40. You are a developer working at a cloud company that embraces serverless. You have performed your initial deployment and would like to work towards adding API Gateway stages and associate them with existing deployments. Your stages will include prod, test, and dev and will need to match a Lambda function variant that can be updated over time.<br/>Which of the following features must you add to achieve this? (**select two**)
    * A. Lambda Versions
    * B. Stage Variables
    * C. Mapping Templates
    * D. Lambda Aliases
    * E. Lambda X-Ray integration
41. A firm runs its technology operations on a fleet of Amazon EC2 instances. The firm needs a certain software to be available on the instances to support their daily workflows. The developer team has been told to use the user data feature of EC2 instances.<br/>Which of the following are true about the user data EC2 configuration? (**Select two**)
    * A. By default, scripts entered as user data don't have root user privileges for executing
    * B. By default, user data is executed every time an EC2 instance is re-started
    * C. By default, user data runs ony during the boot cycle when your first launch an instance
    * D. When an instance is running, you can update user data by using root user credentials
    * E. By default, scripts entered as user data are executed with user privileges
42. DevOps engineers are developing an order processing system where notifications are sent to a department whenever an order is placed for a product. The system also pushes identical notifications of the new order to a processing module that would allow EC2 instances to handle the fulfillment of the order. In the case of processing errors, the messages should be allowed to be re-processed at a later stage and never lost.<br/>Which of the following solutions can be used to address this use-case?
    * A. SNS + SQS
    * B. SNS + Lambda
    * C. SQS + SES
    * D.  SNS + Kinesis
43. Your team has just signed up an year-long contract with a client maintaining a three-tier web application, that needs to be moved to AWS Cloud. The application has steady traffic throughout the day and needs to be on a reliable system with no down-time or access issues. The solution needs to be cost-optimal for this startup.<br/>Which of the following options should you choose?
    * A. On-premises EC2 instance
    * B. Amazon EC2 On Demand Instances
    * C. Amazon EC2 Spot Instances
    * D. Amazon EC2 Reserved Instances
44. A development team has created AWS CloudFormation templates that are reusable by taking advantage of input parameters to name resources based on client names.<br/>You would like to save your templates on the cloud, which storage option should you choose?
    * A. S3
    * B. EFS
    * C. ECR
    * D. EBS
45. A company developed an app-based service for citizens to book transportation rides in the local community. The platform is running on AWS EC2 instances and uses Amazon RDS for storing transportation data. A new feature has been requested where receipts would be emailed to customers with PDF attachments retrieved from Amazon S3.<br/>Which of the following options will provide EC2 instances with the right permissions to upload files to Amazon S3 and generate S3 Signed URL?
    * A. EC2 User Data
    * B. CloudFormation
    * C. Run ````aws configure```` on the EC2 instance
    * D. Create an IMA Role for EC2
46. You are a DynamoDB developer for an aerospace company that requires you to write 6 objects per second of 4.5KB in size each.<br/>What WCU is needed for your project?
    * A. 24
    * B. 46
    * C. 15
    * D. 30
47. A team lead has asked you to create an AWS CloudFormation template that creates EC2 instances and RDS databases. The template should be reusable by allowing the user to input a parameter value for an Amazon EC2 AMI ID.<br/>Which of the following intrinsic function should you choose to reference the parameter?
    * A. ````!Param````
    * B. ````!GetAtt````
    * C. ````!Ref````
    * D. ````!Join````
48. A data analytics company wants to use clickstream data for Machine Learning tasks, develop algorithms, and create visualizations and dashboards to support the business stakeholders. Each of these business units works independently and would need real-time access to this clickstream data for their applications.<br/>As a Developer Associate, which of the following AWS services would you recommend such that it provides a highly available and fault-tolerant solution to capture the clickstream events from the source and then provide a simultaneous feed of the data stream to the consumer applications?
    * A. AWS Kinesis Data Firehose
    * B. AWS Kinesis Data Analytics
    * C. Amazon SQS
    * D. AWS Kinesis Data Streams
49. You are designing a high-performance application that requires millions of connections. You have several EC2 instances running Apache2 web servers and the application will require capturing the user’s source IP address and source port without the use of X-Forwarded-For.<br/>Which of the following options will meet your needs? 
    * A. ALB
    * B. NLB
    * C. CLB
    * D. ELB
50. You are responsible for an application that runs on multiple Amazon EC2 instances. In front of the instances is an Internet-facing load balancer that takes requests from clients over the internet and distributes them to the EC2 instances. A health check is configured to ping the index.html page found in the root directory for the health status. When accessing the website via the internet visitors of the website receive timeout errors.<br/>What should be checked first to resolve the issue?
    * A. The ALB is warning up
    * B. IAM Roles
    * C. The application is down
    * D. SGs
51. The development team at an IT company has configured an ALB with a Lambda function A as the target but the Lambda function A is not able to process any request from the ALB. Upon investigation, the team finds that there is another Lambda function B in the AWS account that is exceeding the concurrency limits.<br/>How can the development team address this issue?
    * A. Use a CloudFront Distribution instead of an ALB for Lambda function A
    * B. Set up reserved concurrency for the Lambda function B so that it throttles if it goes above a certain concurrency limit
    * c. Set up provisioned concurrency for the Lambda function B so that it throttles if it goes above a certain concurrency limit
    * D. Use an API Gateway instead of an ALB for Lambda function A
52. Your team-mate has configured an Amazon S3 event notification for an S3 bucket that holds sensitive audit data of a firm. As the Team Lead, you are receiving the SNS notifications for every event in this bucket. After validating the event data, you realized that few events are missing.<br/>What could be the reason for this behavior and how to avoid this in the future?
    * A. If two are made to a single non-versioned object at the same time, it's possible that only a single event notification will be sent
    * B. Versioning is enabled on the S3 bucket & event notifications are getting fired for only one version
    * C. Someone could have created a new notification configuration & that has overridden your existing configuration
    * D. Your notification action is writting to the same bucket that triggers the notification
53. The development team at an IT company uses CloudFormation to manage its AWS infrastructure. The team has created a network stack containing a VPC with subnets and a web application stack with EC2 instances and an RDS instance. The team wants to reference the VPC created in the network stack into its web application stack.<br/>As a Developer Associate, which of the following solutions would you recommend for the given use-case?
    * A. Create a cross-stack & use the Output output field to flag the value of VPC from the network stack. Then use Ref instrinsic function to reference the value of VPC into the web application stack
    * B. Create a cross-stack reference & use the Export output field to flag the value of VPC from the network stack. Then use Fn::ImportValue intrinsic function to import the value of VPC into the web application stack
    * C. Create a cross-stack reference & use the Export output filed to flag the value of VPC from the network stack. Then use Ref inttrinsic function to reference the value of VPC the web application stack
    * D. Create a cross-stack reference & use the outputs output field to flag the value of VPC from the network stack. Then use Fn::ImportValue intrinsic function to import the value of VPC into the web application stack
54. A .NET developer team works with many ASP.NET web applications that use EC2 instances to host them on IIS. The deployment process needs to be configured so that multiple versions of the application can run in AWS Elastic Beanstalk. One version would be used for development, testing, and another version for load testing.<br/>Which of the following methods do you recommend?
    * A. Use only one Beanstalk environment & perform configuration changes using an Ansible script
    * B. Define a dev environment with a single instance & a 'load test' environment that has settings close to production environment
    * C. Create an ALB to route based on hostname so you can pass on parameters to the development Elastic beanstalk environment. Create a file in .ebentensions/ to know how to handle the traffic comming from the ALB
    * D. You can't have multiple development environments in Elastic Beanstalk, just one development & one production environment
55. As an AWS certified developer associate, you are working on an AWS CloudFormation template that will create resources for a company's cloud infrastructure. Your template is composed of three stacks which are Stack-A, Stack-B, and Stack-C. Stack-A will provision a VPC, a security group, and subnets for public web applications that will be referenced in Stack-B and Stack-C.<br/>After running the stacks you decide to delete them, in which order should you do it?
    * A. Stack A, Stack C then Stack B
    * B. Stack C then Stack A then Stack B
    * C. Stack A, then Stack B, then Stack C
    * D. Stak B, then Stack C, then Stack A
56. A company that specializes in cloud communications platform as a service allows software developers to programmatically use their services to send and receive text messages. The initial platform did not have a scalable architecture as all components were hosted on one server and should be redesigned for high availability and scalability.<br/>Which of the following options can be used to implement the new architecture? (**select two**)
    * A. API Gateway + Lambda
    * B. SES + S3
    * C. EBS + RDS
    * D. ALB + ECS
    * E. CloudWatch + CloudFront
57. An organization with OLTP workloads have successfully moved to DynamoDB after having many issues with traditional database systems. However, a few months into production, DynamoDB tables are consistently recording high latency.<br/>As a Developer Associate, which of the following would you suggest to reduce the latency? (**Select two**)
    * A. Use eventually consistent reads in place of strongly consistent reads whenever possible
    * B. Reduce connection pooling, which keeps the connections alive even when user requests aren't present, thereby, blocking the services
    * C. Consider using Globales if your application is accessed by globally distributed users
    * D. Increase the request timeout settings, so the client gets enough time to complete the requests, thereby reducing retries on the system
    * E. Use DAX for business with heavy write-only workloads
58. You are working with a t2.small instance bastion host that has the AWS CLI installed to help manage all the AWS services installed on it. You would like to know the security group and the instance id of the current instance.<br/>Which of the following will help you fetch the needed information?
    * A. Query the metadata at http://169.254.169.254/latest/meta-data
    * B. Query the user data at http://169.254.169.254/latest/user-data
    * C. Query the user data at http://254.169.254/latest/meta-data
    * D. Create an IAM role & attach it to your EC2 instance that helps you perform a `describe` API call
59. An IT company has a HealthCare application with data security requirements such that the encryption key must be stored in a custom application running on-premises. The company wants to offload the data storage as well as the encryption process to Amazon S3 but continue to use the existing encryption keys.<br/>Which of the following S3 encryption options allows the company to leverage Amazon S3 for storing data with given constraints?
    * A. Server-Side Encryption with CMKs Stored in AWS SSE-KMS
    * B. Server-Side Enccryption with Amazon SSE-S3
    * C. Client-Side Encryption with data encryption is done on the lcient-side before sending it to Amazon S3
    * D. Server-Side Encryption with SSE-C
60. A Developer at a company is working on a CloudFormation template to set up resources. Resources will be defined using code and provisioned based on certain conditions.<br/>Which section of a CloudFormation template does not allow for conditions?
    * A. Parameters
    * B. Conditions
    * C. Outputs
    * D. Resources
61. You team maintains a public API Gateway that is accessed by clients from another domain. Usage has been consistent for the last few months but recently it has more than doubled. As a result, your costs have gone up and would like to prevent other unauthorized domains from accessing your API.<br/>Which of the following actions should you take?
    * A. Use Mapping Templates
    * B. Assign a SG to your API Gateway
    * C. Restrict access by using CORS
    * D. Use account level throttliing
62. You have a Java-based application running on EC2 instances loaded with AWS CodeDeploy agents. You are considering different options for deployment, one is the flexibility that allows for incremental deployment of your new application versions and replaces existing versions in the EC2 instances. The other option is a strategy in which an Auto Scaling group is used to perform a deployment.<br/>Which of the following options will allow you to deploy in this manner? (**Select two**)
    * A. In-place Deployment
    * B. Cattle Deployment
    * C. Blue/Green Deployment
    * D. Pilot Ligh Deployment
63. A junior developer working on ECS instances terminated a container instance in Amazon ECS as per instructions from the team lead. But the container instance continues to appear as a resource in the ECS cluster.<br/>As a Developer Associate, which of the following solutions would you recommend to fix this behavior?
    * A. A custom software on the container instance could have failed & resulted in the container hanging in an unhealthy state till restarted again
    * B. you terminated the container instance while it was is STOPPED state, that lead to this synchronization issues
    * C. You terminated the container instance while it was in RUNNING state, that lead to this synchronization issues
    * D. The container instance has been terminated with AWS CLI, whereas, for ECS instances, Amazon ECS CLI, should be used to avoid any synchronization issues
64. Question 64: Incorrect

A multi-national company maintains separate AWS accounts for different verticals in their organization. The project manager of a team wants to migrate the Elastic Beanstalk environment from Team A's AWS account into Team B's AWS account. As a Developer, you have been roped in to help him in this process.<br/>Which of the following will you suggest?
    * A. Create an export configuration from the EB console from Team A's account. This configuration has to be shared with the IAM Role of Team B's account. The import option of Team B's account will show the saved configuration, that can be used to create a new Beanstalk application
    * B. Create a saved configuration in Team A's account & configure it to Export. Now, log into Team B's account & choose the Import option. Here, you need to specify the name of the saved configuration & allow the system to create the new application. This takes a little time based on the Regions the two accounts belong to
    * C. It's not possible to migratite EB environment from one AWS account to the other
    * D. Create a saved configuration in Team A's account & download it to your local machine. Make the account specific parameter changes & upload to the S3 bucket in Team B's account. From EB console, create an application from 'Saved Configurations'
65. You are storing your video files in a separate S3 bucket than your main static website in an S3 bucket. When accessing the video URLs directly the users can view the videos on the browser, but they can't play the videos while visiting the main website.<br/>What is the root cause of this problem?
    * A. Enable CORS
    * B. Disable Server-Side Encryption
    * C. Amend the IAM policy
    * D. Change the bucket policy
* [Answers](https://i.imgur.com/DdVNFn1.png)
* Score: 34/75 = 52%
