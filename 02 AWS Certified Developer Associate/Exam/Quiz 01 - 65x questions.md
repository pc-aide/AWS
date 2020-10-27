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
   * A. SWF
28.
* [Answer]()
29.
* [Answer]()
30.
* [Answer]()
31.
* [Answer]()
32.
* [Answer]()
33.
* [Answer]()
34.
* [Answer]()
35.
* [Answer]()
36.
* [Answer]()
37.
* [Answer]()
38.
* [Answer]()
39.
* [Answer]()
40.
* [Answer]()
41.
* [Answer]()
42.
* [Answer]()
43.
* [Answer]()
44.
* [Answer]()
45.
* [Answer]()
46.
* [Answer]()
47.
* [Answer]()
48.
* [Answer]()
49.
* [Answer]()
50.
* [Answer]()
51.
* [Answer]()
52.
* [Answer]()
53.
* [Answer]()
54.
* [Answer]()
55.
* [Answer]()
56.
* [Answer]()
57.
* [Answer]()
58.
* [Answer]()
59.
* [Answer]()
* [Answer]()
60.
* [Answer]()
61.
* [Answer]()
62.
* [Answer]()
63.
* [Answer]()
64.
* [Answer]()
65.
* [Answer]()
* Score: 34/75 = 52%
