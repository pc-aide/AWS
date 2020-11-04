# Quiz 03 - 65x questions

## Questions
1) An application runs on an EC2 instance and processes orders on a nightly basis. This EC2 instance needs to access the orders that are stored in S3.<br/>How would you recommend the EC2 instance access the orders securely?
      * A. Create an IAM programmatic user & store the access key & secret access key on the EC2 `~/.aws/credentials` file
      * B. Use an IAM role
      * C. Create an S3 bucket policy that authorises public access
      * D. Use EC2 User Data
2) Your company uses an Application Load Balancer to route incoming end-user traffic to applications hosted on Amazon EC2 instances. The applications capture incoming request information and store it in the Amazon RDS running on Microsoft SQL Server DB engines.<br/>As part of new compliance rules, you need to capture the client's IP address. How will you achieve this?
      * A. Use the header X-Forwarded-From
      * B. You can get the Client IP address from server access logs
      * C. You can get the Client IP address from ELB logs
      * D. Use the header X-Forwarded-For
3) You are a system administrator whose company recently moved its production application to AWS and migrated data from MySQL to AWS DynamoDB. You are adding new tables to AWS DynamoDB and need to allow your application to query your data by the primary key and an alternate key. This option must be added when first creating tables otherwise changes cannot be made afterward.<br/>Which of the following actions should you take?
      * A. Create a LSI
      * B. Migrate away from DynamoDB
      * C. Call Scan
      * D. Create a GSI
4) AWS CloudFormation helps model and provision all the cloud infrastructure resources needed for your business.<br/>Which of the following services rely on CloudFormation to provision resources (**Select two**)?
      * A. AWS Lambda
      * B. AWS CodeBuild
      * C. AWS Autoscaling
      * D. AWS EB
      * E. AWS SAM
5) As a developer, you are looking at creating a custom configuration for Amazon EC2 instances running in an Auto Scaling group. The solution should allow the group to auto-scale based on the metric of 'average RAM usage' for your Amazon EC2 instances.<br/>Which option provides the best solution?
      * A. Migrate your application to AWS Lambda
      * B. Enable detailed monitoring for EC2 & ASG to get the RAM usage data & create a CloudWatch Alarm on top of it
      * C. Create a custom alarm for your ASG & make your instances trigger the alarm using PutAlarmData API
      * D. Create a custom metric in CloudWatch & make your instances 
6) A cybersecurity company is running a serverless backend with several compute-heavy workflows running on Lambda functions. The development team has noticed a performance lag after analyzing the performance metrics for the Lambda functions.<br/>As a Developer Associate, which of the following options would you suggest as the BEST solution to address the compute-heavy workloads?
      * A. Use reserved concurrency to account for the compute-heavy workflows
      * B. Use provisioned concurrency to account for the compute-heavy workflows
      * C. Invoke the Lambda functions asynchronously to process the compute-heavy worflows
      * D. Increase the amount of memory avaialble to  the Lambda functions
7) You have been asked by your Team Lead to enable detailed monitoring of the Amazon EC2 instances your team uses. As a Developer working on AWS CLI, which of the below command will you run?
      * A. AWS ec2 monitor-instances --instance-id i-1234567890abcdef0
      * B. aws ec2 run-instances --image-id ami-0909236 --monitoring Enabled=tru
      * C. aws ec2 monitor-instances --instance-ids i-1234567890abcdef0
      * D. aws ec2 run-instances --image-id ami-09092360 --monitoring State=enabled
8) An AWS CodePipeline was configured to be triggered by Amazon CloudWatch Events. Recently the pipeline failed and upon investigation, the Team Lead noticed that the source was changed from AWS CodeCommit to Amazon S3. The Team Lead has requested you to find the user who had made the changes.<br/>Which service will help you solve this?
      * A. Amazon CloudWatch
      * B. AWS CloudTrail
      * C. Amazon Inspector
      * D. AWS X-Ray
9) A media company uses Amazon SQS queue to manage their transactions. With changing business needs, the payload size of the messages is increasing. The Team Lead of the project is worried about the 256 KB message size limit that SQS has.<br/>What can be done to make the queue accept messages of a larger size?
      * A. Get a service limit increase from AWS
      * B. Use the SQS Extended Client
      * C. Use gzip compression
      * D. Use the MultiPart API
10) You have an Auto Scaling group configured to a minimum capacity of 1 and a maximum capacity of 5, designed to launch EC2 instances across 3 Availability Zones. During a low utilization period, an entire Availability Zone went down and your application experienced downtime.<br/>What can you do to ensure that your application remains highly available?
      * A. Increase the minimum instance capacity of the ASG to 2
      * B. Configure ASG fast failover
      * C. Enable RDS Multi-AZ
      * D. Change the scaling metric of auto-scaling policy to network bytes
11) The development team at a social media company is considering using Amazon ElastiCache to boost the performance of their existing databases.<br/>As a Developer Associate, which of the following use-cases would you recommend as the BEST fit for ElastiCache? (**Select two**)
      * A. Use ElastCache to improve performance of compute-intensive workloads
      * B. Use ElastiCache to improve performance of ETL workloads
      * C. Use ElastiCache to improve latency & thoughput for read-heavy appliacation workloads
      * D. Use ElastiCache to improve latency & throughput for write-heavy appliaction workloads
      * E. Use ElastiCache to run highly complex JOIN queries
12) Recently, you started an online learning platform using AWS Lambda and AWS Gateway API. Your first version was successful, and you began developing new features for the second version. You would like to gradually introduce the second version by routing only 10% of the incoming traffic to the new Lambda version.<br/>Which solution should you opt for?
      * A. Deploy your Lambda in a VPC
      * B. Use Tags to distinguish the different versions
      * C. Use environment variables
      * D. Use AWS Lambda aliases
13) A company uses Amazon RDS as its database. For improved user experience, it has been decided that a highly reliable fully-managed caching layer has to be configured in front of RDS.<br/>Which of the following is the right choice, keeping in mind that cache content regeneration is a costly activity?
      * A. Install Redis on an Amazon EC2 instance
      * B. Implement Amazon ElastiCache Redis in Cluster Mode
      * C. Implement Amazon ElastiCache Memcached
      * D. Migrate the db to Amazon Redshift
14) Your web application reads and writes data to your DynamoDB table. The table is provisioned with 400 WCU’s shared across 4 partitions. One of the partitions receives 250 WCU/second while others receive much less. You receive the error 'ProvisionedThroughputExceededException'.<br/>What is the likely cause of this error?
      * A. You have a hot partition
      * B. WCU's are applied across to all your DynamoDB tables & this needs reconfiguration
      * C. Configured IAM policy is wrong
      * D. CloudWatch monitoring is lagging
15) Amazon S3 achieves high availability by replicating data across multiple servers within AWS data centers. This implies, information about the changes must be replicated across Amazon S3, which can take some time. One gets to observe certain behavior of S3 because of this lag.<br/>Which of the following is an INCORRECT statement about Amazon S3 data consistency model?
      * A. A process deletes an existing object & immediately tries to read it. Until the deletion is fully propagated, Amazon S3 might return the deleted data
      * B. A process writes a new object to Amazon S3 & immediately lists keys within its bucket. Until the change is fully propagated, the object might not appear in the list
      * C. A process deletes an existing object & immediately lists keys within its bucket. Until the deletion is fully propagated, Amazon S3 might list the deleted object
      * D. Amazon S3 supports object locking for concurrent updates
16) Two policies are attached to an IAM user. The first policy states that the user has explicitly been denied all access to EC2 instances. The second policy states that the user has been allowed permission for EC2:Describe action.<br/>When the user tries to use 'Describe' action on an EC2 instance using the CLI, what will be the output?
      * A. The IAM user stands in an invalid state, because of conflicting policies
      * B. The user will get access because it has an explicit allow
      * C. The user will be denied access because one of the policies has an explicit deny on it
      * D. The order of the policy matters. If policy 1 is before 2, then the user is denied access. If policy 2 is before 1, then the user is allowed access
17) Your team-mate has configured an Amazon S3 event notification for an S3 bucket that holds sensitive audit data of a firm. As the Team Lead, you are receiving the SNS notifications for every event in this bucket. After validating the event data, you realized that few events are missing.<br/>What could be the reason for this behavior and how to avoid this in the future?
      * A. Versioning is enabled on the S3 bucket & event notifications are getting fired for only one version
      * B. If two write are made to a single non-versioned object at the same time, it is possible that only a single event notification will be sent
      * C. Someone could have created a new notification configuration & that has overridden your existing configuration
      * D. Your notification action is writing to the same bucket that triggers the notification
18) Your company hosts a static website on Amazon S3 written in HTML5. The website targets aviation enthusiasts and it has grown a worldwide audience with hundreds of thousands of visitors accessing the website now on a monthly basis. While users in the United States have a great user experience, users from other parts of the world are experiencing slow responses and lag.<br/>Which service can mitigate this issue?
      * A. Use Amazon ElastiCache for Redis
      * B. Use Amazon S3 Caching
      * C. Use Amazon CloudFront
      * D. Use Amazon S3 Transfer Acceleration
19) As a Senior Developer, you manage 10 Amazon EC2 instances that make read-heavy database requests to the Amazon RDS for PostgreSQL. You need to make this architecture resilient for disaster recovery.<br/>Which of the following features will help you prepare for database disaster recovery? (**Select two**)
      * A. Use cross-Region Read Replicas
      * B. Enable the automated backup feature of Amazon RDS in a multi-AZ deployment that creates backups in a single AWS Region
      * C. Use db cloning feature of the RDS DB cluster
      * D. Use RDS Provisoned IOPS (SSD) Storage in place of General Purpose (SSD) storage
      * E. Enable the automated backup feature of Amazon RDS in multi-AZ deployment that creates backups across multiple Regions
20) A junior developer working on ECS instances terminated a container instance in Amazon ECS as per instructions from the team lead. But the container instance continues to appear as a resource in the ECS cluster.<br/>As a Developer Associate, which of the following solutions would you recommend to fix this behavior?
      * A. A custom software on the container instance could have failed & resulted in the countainer hanging in an unhealthy state till restarted again
      * B. You terminated the container instance while it was in STOPPED state, that lead to this synchronization issues
      * C. The container instance has been terminated with AWS CLI, whereas, for ECS instances, Amazon ECS CLI should be used to avoid any synchronization issue
      * D. You terminated the container instance while it was in RUNNING state, that lead to this synchronization issues
21) Your company is planning to move away from reserving EC2 instances and would like to adopt a more agile form of serverless architecture.<br/>Which of the folloiwng is the simplest and the least effort way of deploying the Docker containers on this serverless architecture?
      * A. AWS Elastic Beanstalk
      * B. Amazon ECS on EC2
      * C. Amazon EKS on Fargate
      * D. Amazon ECS on Fargate
22) You have a three-tier web application consisting of a web layer using AngularJS, an application layer using an AWS API Gateway and a data layer in an Amazon RDS database. Your web application allows visitors to look up popular movies from the past. The company is looking at reducing the number of calls made to endpoint and improve latency to the API.<br/>What can you do to improve performance?
      * A. Enable API Gateway Caching
      * B. Use Amazon Kinesis Data Streams to stream incoming data & reduce the burden on Gateway APIs
      * C. Use Mapping Templates
      * D. Use Stage Variables
23) You are working for a shipping company that is automating the creation of ECS clusters with an Auto Scaling Group using an AWS CloudFormation template that accepts cluster name as its parameters. Initially, you launch the template with input value 'MainCluster', which deployed five instances across two availability zones. The second time, you launch the template with an input value 'SecondCluster'. However, the instances created in the second run were also launched in 'MainCluster' even after specifying a different cluster name.<br/>What is the root cause of this issue?
      * A. The ECS agent Docker image must be re-built to connect to the other clusters
      * B. The SGs on the EC2 instance are pointing to the wrong ECS cluster
      * C. The EC2 instance is missing IAM permissions to join the other clusters
      * D. The cluster name Parameter has not been updated in the file /etc/ecs/ecs.config during bootstrap
24) An IT company has migrated to a serverless application stack on the AWS Cloud with the compute layer being implemented via Lambda functions. The engineering managers would like to actively troubleshoot any failures in the Lambda functions.<br/>As a Developer Associate, which of the following solutions would you suggest for this use-case?
      * A. Use CodeCommit to identity & notify any failures in the Lambda code
      * B. Use CloudWatch Events to identity & notify any failures in the Lambda code
      * C. Use CodeDeploy to identity & notify any failures in the Lambda code
      * D. The developers should insert logging statements in the Lambda function code which are then available via CloudWatch logs
25) Your company has a three-year contract with a healthcare provider. The contract states that monthly database backups must be retained for the duration of the contract for compliance purposes. Currently, the limit on backup retention for automated backups, on Amazon RDS, does not meet your requirements.<br/>Which of the following solutions can help you meet your requirements?
      * A. Enable RDS Multi-AZ
      * B. Create a cron event in CloudWatch, which triggers in AWS Lambda function that triggers the db snapshot
      * C. Enable RDS Read replicas
      * D. Enable RDS automatic backups
26) As part of their on-boarding, the employees at an IT company need to upload their profile photos in a private S3 bucket. The company wants to build an in-house web application hosted on an EC2 instance that should display the profile photos in a secure way when the employees mark their attendance.<br/>As a Developer Associate, which of the following solutions would you suggest to address this use-case?
      * A. Save the S3 key for each user's profile photo in a DynamoDB table & use a lambda function to dynamically generate a pre-signed URL. Reference this URL for display via the web application
      * B. Keep each user's profile image encoded in base64 format in an RDS table & reference it from the application for display
      * C. Keep each user's profile image encoded in base64 format in a DynamoDB table & reference it from the application for display
      * D. Make the S3 bucket public so that the application can reference the image URL for display
27) A company has a workload that requires 14k consistent IOPS for data that must be durable and secure. The compliance standards of the company state that the data should be secure at every stage of its lifecycle on all of the EBS volumes they use.<br/>Which of the following statements are true regarding data security on EBS?
      * A. EBS volumes support in-flight encryption but does not support encryption at rest
      * B. EBS volumes don't support in-flight encryption but do support encryption at rest using KMS
      * C. EBS volumes support both in-flight encryption & encryption at rest using KMS
      * D. EBS volumes don't support any encryption
28) A new member of your team is working on creating DLQ for AWS Lambda functions.<br/>As a Developer Associate, can you help him identify the use cases, wherein AWS Lambda will add a message into a DLQ after being processed? (**Select two**)
      * A. The Lambda function invocation is synchronous
      * B. The Lambda function invocation failed once but succeeded thereafter
      * C. The event fails all processing attempts
      * D. The event has been processed successfully
      * E. The Lambda function invocation is asynchronous
29) You team maintains a public API Gateway that is accessed by clients from another domain. Usage has been consistent for the last few months but recently it has more than doubled. As a result, your costs have gone up and would like to prevent other unauthorized domains from accessing your API.<br/>Which of the following actions should you take?
      * A. Assign a SG to your API Gateway
      * B. Restrict access by using CORS
      * C. Use Account-level throttling
      * D. Use Mapping Templates
30) A company uses microservices-based infrastructure to process the API calls from clients, perform request filtering and cache requests using the AWS API Gateway. Users report receiving 501 error code and you have been contacted to find out what is failing.<br/>Which service will you choose to help you troubleshoot?
      * A. Use X-Ray service
      * B. Use API Gateway service
      * C. Use CloudWatch service
      * D. Use CloudTrail service
31) You company runs business logic on smaller software components that perform various functions. Some functions process information in a few seconds while others seem to take a long time to complete. Your manager asked you to decouple components that take a long time to ensure software applications stay responsive under load. You decide to configure Amazon Simple Queue Service (SQS) to work with your Elastic Beanstalk configuration.<br/>Which of the following Elastic Beanstalk environment should you choose to meet this requirement?
      * A. Single Instance Worker node
      * B. LB, Autoscaling environment
      * C. Single Instance with EIP
      * D. Dedicated worker environment
32) Your team lead has requested code review of your code for Lambda functions. Your code is written in Python and makes use of the Amazon S3 to upload logs to an S3 bucket. After the review, your team lead has recommended reuse of execution context to improve the Lambda performance.<br/>Which of the following actions will help you implement the recommendation?
      * A. Move the Amazon S3 client initialization, out of your function handler
      * B. Use environment variables to pass operational parameters
      * C. Assign more RAM the function
      * D. Enable X-Ray integration
33) A recruit has created an Amazon S3 bucket. He needs assistance in getting the security principles right for this bucket.<br/>Which of the following is NOT a security practice for access control to S3 buckets?
      * A. Use of SGs
      * B. Use of Bucket Policies
      * C. Use of IAM Roles
      * D. Use ACLs
34) A Company uses a large set of EBS volumes for their fleet of Amazon EC2 instances. As an AWS Certified Developer Associate, your help has been requested to understand the security features of the EBS volumes. The company does not want to build or maintain their own encryption key management infrastructure.<br/>Can you help them understand what works for Amazon EBS encryption? (**Select two**)
      * A. You can encrypt an existing unencrypted volume or snapshot by using AWS KMS AWS SDKs
      * B. Encryption by default is a Region-specific setting. If you enable it for a Region, you can't disable it for individual volumes or snapshots in that Region
      * C. A volume restored from an encrypted snapshot, or a copy of an encrypted snapshot is always encrypted
      * D. Encryption by default is an AZ specific setting. If you enable it for an AZ, you can't disable it for individual volumes or snapshots in that AZ
      * E. A snapshot of an encrypted volume can be encrypted or unencrypted
35) An IT company has its serverless stack integrated with AWS X-Ray. The developer at the company has noticed a high volume of data going into X-Ray and the AWS monthly usage charges have skyrocketed as a result. The developer has requested changes to mitigate the issue.<br/>As a Developer Associate, which of the following solutions would you recommend to obtain tracing trends while reducing costs with minimal disruption?
      * A. Custom configuration for the X-Ray agents
      * B. Implement a network sampling rule
      * C. Use Filter Expressions in the X-Ray console
      * D. Enable X-Ray sampling
36) A HealthCare mobile app uses proprietary Machine Learning algorithms to provide early diagnosis using patient health metrics. To protect this sensitive data, the development team wants to transition to a scalable user management system with log-in/sign-up functionality that also supports MFA<br/>Which of the following options can be used to implement a solution with the LEAST amount of development effort? (**Select two**)
      * A. Use Amazon Cognito to enable MFA when users log-in
      * B. Use Lambda functions & DynamoDB to create a custom solution for user management
      * C. Use Amaon Cognito fo user-management & facilitating the log-in/sign-up process
      * D. Use Amazon SNS to send MfA code via SMS to mobile app users
      * E. Use Lambda functions & RDS to create a custom solution for user managment
37) A high-frequency stock trading firm is migrating their messaging queues from self-managed message-oriented middleware systems to Amazon SQS. The development team at the company wants to minimize the costs of using SQS.<br/>As a Developer Associate, which of the following options would you recommend to address the given use-case?
      * A. Use SQS short polling to retrieve messages from your Amazon SQS queues
      * B. Use SQS visibility timeout to retrieve messages from your Amazon SQS queues
      * C. Use SQS long polling to retrieve messages from your Amazon SQS queues 
      * D. use SQS message timer to retrieve messages from your Amazon SQS queues
38) A leading financial services company offers data aggregation services for Wall Street trading firms. The company bills its clients based on per unit of clickstream data provided to the clients. As the company operates in a regulated industry, it needs to have the same ordered clickstream data available for auditing within a window of 7 days.<br/>As a Developer Associate, which of the following AWS services do you think provides the ability to run the billing process and auditing process on the given clickstream data in the same order?
      * A. AWS Kinesis Data Analytics
      * B. AWS SQS
      * C. AWS Kinesis Data Streams
      * D. AWS Knesis Data Firehose
39) You are creating a mobile application that needs access to the AWS API Gateway. Users will need to register first before they can access your API and you would like the user management to be fully managed.<br/>Which authentication option should you use for your API Gateway layer?
      * A. Use Cognito User Pools
      * B. Use Lambda Authorizer
      * C. Use IAM permissions with sigv4
      * D. Use API Gateway User Pools
40) A multi-national company runs its technology operations on AWS Cloud. As part of their storage solution, they use a large number of EBS volumes, with AWS Config and CloudTrail activated. A manager has tried to find the user name that created an EBS volume by searching CloudTrail events logs but wasn't successful.<br/>As a Developer Associate, which of the following would you recommend as the correct solution?
      * A. AWS CloudTrail event logs for 'CreateVolume' aren't available for EBS volumes created during an Amazon EC2 launch
      * B. AWS CloudTrail event logs for 'ManageVolume' aren't available for EBS volumes created during an Amazon EC2 launch
      * C. EBS volume status checks are disabled
      * D. Amazon EBS CloudWatch metrics are disabled
41) You have a workflow process that pulls code from AWS CodeCommit and deploys to EC2 instances associated with tag group ProdBuilders. You would like to configure the instances to archive no more than two application revisions to conserve disk space.<br/>Which of the following will allow you to implement this?
      * A. Have LB in front of your instances
      * B. Integrate with AWS CodePipeline
      * C. AWS CloudWatch Log Agent
      * D. CodeDeploy Agent
42) An organization is moving its on-premises resources to the cloud. Source code will be moved to AWS CodeCommit and AWS CodeBuild will be used for compiling the source code using Apache Maven as a build tool. The organization wants the build environment should allow for scaling and running builds in parallel.<br/>Which of the following options should the organization choose for their requirement?
      * A. Choose a high-performance instance type for your CodeBuild instances
      * B. CodeBuild scales automatically, the organization does not have to do anything for scaling or for parallel builds
      * C. Run CodeBuild in an ASG
      * D. Enable CodeBuild Auto Scaling
43) A developer from your team has configured the load balancer to route traffic equally between instances or across Availability Zones. However, ELB routes more traffic to one instance or AZ than the others.<br/>Why is this happening and how can it be fixed? (**Select two**)
      * A. The could be short-lived TCP connections between clients & instances
      * B. Instances of a specific type aren't equally distributed across AZs
      * C. Sticky sessions are enabled for the LB
      * D. For ALB, cross-zone LB is disabled by default
      * E. After you disable an AZ, the targets in that AZ remian registered with the LB, thereby random bursts of traffic
44) A company’s e-commerce website is expecting hundreds of thousands of visitors on Black Friday. The marketing department is concerned that high volumes of orders might stress SQS leading to message failures. The company has approached you for the steps to be taken as a precautionary measure against the high volumes.<br/>What step will you suggest as a Developer Associate?
      * A. Pre-configure the SQS queue to increase the capacity when messages hit a certain threshold
      * B. Amazon SQS is highly scalable & does not need any intervention to handle the expected high volumes
      * C. Convert the queue into FIFO ordered queue, since messages to the down system will be processed faster once they are ordered
      * D. Enable auto-scaling in the SQS queue
45) A telecommunications company that provides internet service for mobile device users maintains over 100 c4.large instances in the us-east-1 region. The EC2 instances run complex algorithms. The manager would like to track CPU utilization of the EC2 instances as frequently as every 10 seconds.<br/>Which of the following represents the BEST solution for the given use-case?
      * A. Enable EC2 detailed monitoring
      * B. Symply get it from the CloudWatch Metrics
      * C. Open a support ticket with AWS
      * D. Create a high-resolution custom metric & push the data using a script triggered every 10 seconds
46) A digital marketing company has its website hosted on an Amazon S3 bucket A. The development team notices that the static JavaScript files, that are hosted on another S3 bucket B, are not loading correctly on the website.<br/>Which of the following solutions can be used to address this issue?
      * A. Configure CORS on the bucket A that is hosting the website to allow any origin to respond to requests
      * B. Configure CORS on the bucket B that is hosting the JavaScript files to allow Bucket A origin to make the requests
      * C. Enable versioning on both th buckets to facilitate correct functioning of the website
      * D. Update bucket policies on both bucket A & bucket B to allow successful loading of the JavaScript files on the website
47) A media company stores all of their static data assets on Amazon S3. They have configured S3 notifications for different stages of the object life cycle. But, the notifications are not getting delivered.<br/>Which of the following could be the most possible configuration error?
      * A. S3 destination might have been an Amazon SNS topic. Topics are no more suported for S3 event notification destinations
      * B. An Amazon FIFO SQS queue might have been configured as the destination. Only standard SQS queues are supported for Amazon S3 event notification destination
      * C. An AWS Lambda function might have been configured that ends up writing to the same bucket that triggers the notification
      * D. An Amazon Standard SQS queue might have been configured as the destination. Only FIFO SQS queues are supported for Amazon S3 event notification destination
48) You have migrated an on-premise SQL Server database to an Amazon RDS database attached to a VPC inside a private subnet. Also, the related Java application, hosted on-premise, has been moved to an Amazon Lambda function.<br/>Which of the following should you implement to connect AWS Lambda function to its RDS instance?
      * A. Configure Lambda to connect to the public subnet that will give internet access & use SG to access RDS inside the private subnet
      * B. Use Lambda layers to connect ot the internet & RDS separately
      * C. Configure Lambda to connect to VPC with private subnet & SG needed to access RDS
      * D. Use Environment variables to pass in the RDS connection string
49) You have deployed a traditional 3-tier web application architecture with a Classic Load Balancer, an Auto Scaling group, and an Amazon RDS database. Users are reporting that they have to re-authenticate into the website often.<br/>What should you do to make the application tier stateless and outsource the session information?
      * A. Enable LB stickiness
      * B. Add an ElastiCache Cluster
      * C. Enable RDS read replicas
      * D. Use EIP
50) An e-commerce company has an order processing workflow with several tasks to be done in parallel as well as decision steps to be evaluated for successful processing of the order. All the tasks are implemented via Lambda functions.<br/>Which of the following is the BEST solution to meet these business requirements?
      * A. Use AWS Step Functions activities to orchestrate the workflow
      * B. AWS Glue to orchestrate the workflow
      * C. Use AWS Batch ot orchestrate the workflow
      * D. Use AWS Step Function state machines to orchestrate the workflow
51) An organization with OLTP workloads have successfully moved to DynamoDB after having many issues with traditional database systems. However, a few months into production, DynamoDB tables are consistently recording high latency.<br/>As a Developer Associate, which of the following would you suggest to reduce the latency? (**Select two**)
      * A. Use DAX for business with heavy write-only workloads
      * B. Increase the request timeout settings, so the client gets enough time to complete the requests, thereby reducing retries on the system
      * C. Use entually consistent reads in place of strongly consistent reads whenever possible
      * D. Consider using Global tables if your application is accessed by globally distrubted users
      * E. Reduce connection pooling, which keeps the connections alive even when user requests are not present, thereby, blocking the services
52) As a Developer, you are working on a mobile application that utilizes Amazon SQS for sending messages to downstream systems for further processing. One of the requirements is that the messages should be stored in the queue for a period of 12 days.<br/>How will you configure this requirement?
      * A. Enable Long Polling for the SQS queue
      * B. Use a FIFO SQS queue
      * C. Change the queue message retention setting
      * D. The maximum retention period of SQS messages is 7 days, therefore retention period of 12 days is not possible
53) You are a developer working with the AWS CLI to create Lambda functions that contain environment variables. Your functions will require over 50 environment variables consisting of sensitive information of database table names.<br/>What is the total set size/number of environment variables you can create for AWS Lambda?
      * A. The total sie of all environment variables shouldn't exceed 4kB. The maximum number of variables that can be created is 35
      * B. The total size of all environment variables shouldn't exceed 8KB. There is no limit on the number of variables
      * C. The total size of all environment variables souldn't exceed 4KB. There is no limit on the number of variables
      * D. The total size of all environment variables souldn't exceed 8KB. The maximum number of variables that can be created is 50
54) A mobile gaming company is experiencing heavy read traffic to its Amazon RDS database that retrieves player’s scores and stats. The company is using RDS database instance type db.m5.12xlarge, which is not cost-effective for their budget. They would like to implement a strategy to deal with the high volume of read traffic, reduce latency, and also downsize the instance size to cut costs.<br/>As a Developer, which of the following solutions do you recommend?
      * A. Switch application code to AWS Lambda for better performance
      * B. Setup ElastiCache in front of RDS
      * C. Setup RDS Read Replicas
      * D. Move to Amazon Redshift
55) Your organization has developers that merge code changes regularly to an AWS CodeCommit repository. Your pipeline has AWS CodeCommit as the source and you would like to configure a rule that reacts to changes in CodeCommit.<br/>Which of the following options do you choose for this type of integration?
      * A. Use Lambda Event Rules
      * B. Use CloudTrail Event rules with Amazon SES
      * C. Use CloudWatch Event Rules
      * D. Use Lambda function with Amazon SNS
56) Your application is deployed automatically using AWS Elastic Beanstalk. Your YAML configuration files are stored in the folder .ebextensions and new files are added or updated often. The DevOps team does not want to re-deploy the application every time there are configuration changes, instead, they would rather manage configuration externally, securely, and have it load dynamically into the application at runtime.<br/>What option allows you to do this?
      * A. Use Environment variables
      * B. Use Stage Variables
      * C. Use SSM Parameter Store
      * D. Use S3
57) A company has their entire stack integrated with AWS X-Ray. A manager at the company noticed the skyrocketing AWS monthly usage charges for the X-Ray service. He tracked the abnormal bills to the high volume of input data going into X-Ray. As a Developer, you have been given the responsibility to fix this issue as quickly as possible, with minimal disruptions.<br/>Which of the below is the optimal choice for this issue?
      * A. Send only the required data from client-side
      * B. Custom configuration of the X-Ray agents
      * C. Enable X-Ray Sampling
      * D. Enable X-Ray Deep linking to send only the most useful data to X-Ray
58) A startup manages its Cloud resources with Elastic Beanstalk. The environment consists of few Amazon EC2 instances, an ASG, and an ELB. Even after the Load Balancer marked an EC2 instance as unhealthy, the ASG has not replaced it with a healthy instance.<br/>As a Developer, suggest the necessary configurations to automate the replacement of unhealthy instance.
      * A. The health check type of your instance's ASG, must be changed from EC2 to ELB by using a configuration file
      * B. The ping path field of the LB is configured incorrectly
      * C. Health check parameters were configured for checking the instance health alone. The instance failed because of applicatiol failure which was not configured as a parameter for health check status
      * D. ASG doesn't automatically replcae the unhealthy instance marked by the LB. They have ot be manually replcaed from AWS Console
59) A financial services company wants to ensure that the customer data is always kept encrypted on Amazon S3 but wants a fully managed solution to create, rotate and remove the encryption keys.<br/>As a Developer Associate, which of the following would you recommend to address the given use-case?
      * A. SSE with CMKs Stored in AWS SSE-KMS
      * B. SSE with Secret Manager
      * C. SSE-C
      * D. SSE-S3
60) A multi-national company maintains separate AWS accounts for different verticals in their organization. The project manager of a team wants to migrate the Elastic Beanstalk environment from Team A's AWS account into Team B's AWS account. As a Developer, you have been roped in to help him in this process.<br/>Which of the following will you suggest?
      * A. Create an export configuration from the EB console from Team A's account. This configuration has to be shared with the IAM Role of Team B's account. The import option of Team's account will hsow the saved configuration, that can be used to create a new Beanstalk application
      * B. Create a saved configuration in Team A's account & configure it to Export. Now, log into Team B's account & choose the miport option. Here, you need to specify the name of the saved configuration & allow the system to create the new application. This takes a little on the Regions the two accounts belong to
      * C. It is not possible to migrate EB environment from one AWS account to the other
      * D. Create a saved configuration in Team A's account & download it to your local machine. Make the account-specific parameter changes & upload to the S3 bucket in Team B's account. From EB console, create an application from 'Saved Configurations'
61) As part of employee skills upgrade, the developers of your team have been delegated few responsibilities of DevOps engineers. Developers now have full control over modeling the entire software delivery process, from coding to deployment. As the team lead, you are now responsible for any manual approvals needed in the process.<br/>Which of the following approaches supports the given workflow?
      * A. Create deeply integrated AWS CodePipelines for each environment
      * B. Create multiple CodePipelines for each environment & link them using AWS Lambda
      * C. Use CodePipeline with Amazon VPC
      * D. Create one CodePipeline for your entire flow & add a manual approval step
62) You are running a cloud file storage website with an Internet-facing Application Load Balancer, which routes requests from users over the internet to 10 registered Amazon EC2 instances. Users are complaining that your website always asks them to re-authenticate when they switch pages. You are puzzled because this behavior is not seen in your local machine or dev environment.<br/>What could be the reason?
      * A. ALB is in slow-start mode, which gives ALB a little more time to read & write session data
      * B. The EC2 instance are logging out the users because the instances never have access to the client IPs because of the LB
      * C. The LB does not have TLS enabled
      * D. The LB does not have stickiness enabled
63) A multi-national enterprise uses AWS Organizations to manage its users across different divisions. Even though CloudTrail is enabled on the member accounts, managers have noticed that access issues to CloudTrail logs across different divisions and AWS Regions is becoming a bottleneck in troubleshooting issues. They have decided to use the organization trail to keep things simple.<br/>What are the important points to remember when configuring an organization trail? (**Select two**)
      * A. By default, CloudTrail tacks only bucket-level actions. To track object-level actions, you need to enable Amazon S3 data events
      * B. Member accounts will be able to see the Organization trail, but can't modify or delete it
      * C. By default, CloudTrail event log files are not encrypted
      * D. There is nothing called Organization tRail. The master account can, however, enable CloudTrail logging, to keep track of all activities across AWS accounts
      * E. Member accounts don't have access to organization trail, neither do they have access to the Amazon S3 bucket that logs the files
64) A large firm stores its static data assets on Amazon S3 buckets. Each service line of the firm has its own AWS account. For a business use case, the Finance department needs to give access to their S3 bucket's data to the Human Resources department.<br/>Which of the below options is NOT feasible for cross-account access of S3 bucket objects?
      * A. Use Resource-based ACL & IAM policies for programmatic-only access to S3 bucket objects
      * B. Use Cross-account IAM role for programmatic & console access to S3 bucket objects
      * C. Use Resource-based & AWS IAM policies for programmatic-only access to S3 bucket objects
      * D. Use IAM roles & resource-based policies delegate access aross accounts within different partitions via programmatic access only
65) Your web application architecture consists of multiple Amazon EC2 instances running behind an Elastic Load Balancer with an Auto Scaling group having the desired capacity of 5 EC2 instances. You would like to integrate AWS CodeDeploy for automating application deployment. The deployment should re-route traffic from your application's original environment to the new environment.<br/>Which of the following options will meet your deployment criteria?
      * A. Opt for In-place deployment
      * B. Opt for Rolling deployment
      * C. Opt for Blue/Green deployment
      * D. Opt for Immutable deployment
* [Answer](https://i.imgur.com/niyyoGy.png)
* Score:
    * [03-11-2020 AM] 33/65 = 50%
