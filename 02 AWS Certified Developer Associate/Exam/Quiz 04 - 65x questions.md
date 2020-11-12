# Quiz 04 - 65x questions

## Questions
1) An IT company is using AWS CloudFormation to manage its IT infrastructure. It has created a template to provision a stack with a VPC and a subnet. The output value of this subnet has to be used in another stack.
<br/>As a Developer Associate, which of the following options would you suggest to provide this information to another stack?
      * A. Use F::Transform
      * B. Use Fn::ImportValue
      * C. Use 'Expose' field in the Output section of the stack's template
      * D. Use 'Export' field in the Output section of the stack's template
2) An e-commerce company uses Amazon SQS queues to decouple their application architecture. The development team has observed message processing failures for an edge case scenario when a user places an order for a particular product ID, but the product ID is deleted, thereby causing the application code to fail.<br/>As a Developer Associate, which of the following solutions would you recommend to address such message failures?
      * A. Use a DLQ to handle message processing failures
      * B. Use short polling to handle message processing failures
      * C. Use long polling to handle message processing failures
      * D. Use a temporary queue to handle message processing failures
3) Your company stores confidential data on an Amazon S3 bucket. New security compliance guidelines require that files be stored with server-side encryption. The encryption used must be Advanced Encryption Standard (AES-256) and the company does not want to manage S3 encryption keys.<br/>Which of the following options should you use?
    * A. SSE-C
    * B. SSE-KMS
    * C. SSE-S3
    * D. Client Side Encryption
4) Your company manages MySQL databases on EC2 instances to have full control. Applications on other EC2 instances managed by an ASG make requests to these databases to get information that displays data on dashboards viewed on mobile phones, tablets, and web browsers.<br/>Your manager would like to scale your Auto Scaling group based on the number of requests per minute. How can you achieve this?
    * A. You create a CloudWatch custom metric & build an alarm to scale your ASG
    * B. Attach an ELB
    * C. Attach additional EFS
    * D. You enable detailed monitoring & use that to scale your ASG
5) A company developed an app-based service for citizens to book transportation rides in the local community. The platform is running on AWS EC2 instances and uses Amazon RDS for storing transportation data. A new feature has been requested where receipts would be emailed to customers with PDF attachments retrieved from Amazon S3.<br/>Which of the following options will provide EC2 instances with the right permissions to upload files to Amazon S3 and generate S3 Signed URL?
    * A. Run `aws configure` on the EC2 instance
    * B. CloudFormation
    * C. EC2 User Data
    * D. Create an IAM Role for EC2
6) An organization uses Alexa as its intelligent assistant to improve productivity throughout the organization. A group of developers manages custom Alexa Skills written in Node.Js to control conference-room equipment settings and start meetings using voice activation. The manager has requested developers that all functions code should be monitored for error rates with the possibility of creating alarms on top of them.<br/>Which of the following options should be chosen? (**select two**) 
    * A. SSM
    * B. CloudTrail
    * C. CloudWatch Metrics
    * D. X-Ray
    * E. CloudWatch Alarms
7) You work as a developer doing contract work for the government on AWS gov cloud. Your applications use Amazon SQS for its message queue service. Due to recent hacking attempts, security measures have become stricter and require you to store data in encrypted queues.<br/>Which of the following steps can you take to meet your requirements without making changes to the existing code?
    * A. Use the SSL endpoint
    * B. Use Client side encryption
    * C. Enable SQS KMS encryption
    * D. Use Secret Manager
8) Your organization is looking into making a change to all virtual machines in the cloud. They would like to take advantage of running a bootstrap script for their Windows Server 2012 Base AMI virtual machines when they first boot.<br/>Which of the following options will allow the organization to achieve this?
    * A. EC2 Meta Data
    * B. EC2 User Data
    * C. Custom AMI
    * D. Mount EFS network drives
9) A media company is building an application that needs to store video files in Amazon S3. Management requires that the files be encrypted before they are sent to Amazon S3 for storage. The encryption keys need to be managed by an in-house security team but the key itself is stored on AWS.<br/>Which solution should the company use to meet these requirements?
    * A. Use server-side encryption with a client-side master key
    * B. Use server-side encryption with customer-provider encryption key (SSE-C)
    * C. Use client-side encryption with an AWS KMS managed customer master key (CMK)
    * D. Use client-side encryption with Amazon S3 managed key
10) A senior cloud engineer designs and deploys online fraud detection solutions for credit card companies processing millions of transactions daily. The Elastic Beanstalk application sends files to Amazon S3 and then sends a message to an Amazon SQS queue containing the path of the uploaded file in S3. A solution architect recommended that since PUTS of existing objects in S3 deliver eventual consistency and we want to minimize the risk of consumers reading old data, it would be preferable to introduce a per-message lag so that consumers won't find a message in SQS until it has been in the queue for at least 10 seconds.<br/>Which SQS feature should the developer leverage?
    * A. Implement application-side delay
    * B. Enable LongPolling
    * C. Use DelaySeconds parameter
    * D. Use visibility timeout parameter
11) You are a system administrator whose company recently moved its production application to AWS and migrated data from MySQL to AWS DynamoDB. You are adding new tables to AWS DynamoDB and need to allow your application to query your data by the primary key and an alternate key. This option must be added when first creating tables otherwise changes cannot be made afterward.<br/>Which of the following actions should you take?
    * A. Create a GSI
    * B. Call Scan
    * C. Create a LSI
    * D. Migrate away from DynamoDB
12) A development team uses the AWS SDK for Java to maintain an application that stores data in AWS DynamoDB. The application makes use of `Scan` operations to return several items from a 25 GB table. There is no possibility of creating indexes to retrieve these items predictably. Developers are trying to get these specific rows from DynamoDB as fast as possible.<br/>Which of the following options can be used to improve the performance of the Scan operation?
    * A. Use a Query
    * B. Use a FilterExpression
    * C. Use a ProjectionExpression
    * D. Use parallel scans
13) You are a software engineer working for an IT company and are asked to contribute to a growing internal application that includes dashboards for data visualization. You are provisioning your AWS DynamoDB table and need to perform 10 strongly consistent reads per second of 4 KB in size each.<br/>How many RCUs are needed?
    * A. 5
    * B. 40
    * C. 10
    * D. 20
14) Your company manages hundreds of EC2 instances running on Linux OS. The instances are configured in several Availability Zones in the eu-west-3 region. Your manager has requested to collect system memory metrics on all EC2 instances using a script.<br/>Which of the following solutions will help you collect this data?
    * A. Use a cron job on the instances that pushes the EC2 RAM statistics as a Custom metric into CloudWatch
    * B. Extract RAM statistics from the standard CloudWatch metrics for EC2 instances
    * C. Extract RAM statistics using X-Ray
    * D. Extract RAM statistics using the instance metadata
15) A financial services company with over 10,000 employees has hired you as the new Senior Developer. Initially caching was enabled to reduce the number of calls made to all API endpoints and improve the latency of requests to the company’s API Gateway.<br/>For testing purposes, you would like to invalidate caching for the API clients to get the most recent responses. Which of the following should you do?
    * A. Using the Header Bypass-Cache=1
    * B. Use the Request parameter:?bypass_cache=1
    * C. Using the request parameter ?cache-control-max-age=0
    * D. Using the Header Cache-Control: max-age=0
16) Your company has been hired to build a resilient mobile voting app for an upcoming music award show that expects to have 5 to 20 million viewers. The mobile voting app will be marketed heavily months in advance so you are expected to handle millions of messages in the system. You are configuring Amazon SQS queues for your architecture that should receive messages from 20 KB to 200 KB.<br/>Is it possible to send these messages to SQS?
    * A. No, the max message size is 128KB
    * B. Yes, the max message size is 256KB
    * C. Yes, the max message is 512KB
    * D. No, the max message size is 64KB
17) The development team at a company wants to insert vendor records into an Amazon DynamoDB table as soon as the vendor uploads a new file into an Amazon S3 bucket.<br/>As a Developer Associate, which set of steps would you recommend to achieve this?
    * A. Develop a Lambda function that will poll the S3 bucket & then insert the records into DynamoDB
    * B. Write a cron job that will execute a Lambda function at a scheduled time & insert the records into DynamoDB
    * C. Create an S3 event to invoke a Lambda function that inserts records into DynamoDB
    * D. Set up an event with Amazon CloudWatch Events that will monitor the S3 bucket & then insert the records into DynamoDB
18) As a Full-stack Web Developer, you are involved with every aspect of a company’s platform from development with PHP and JavaScript to the configuration of NoSQL databases with Amazon DynamoDB. You are not concerned about your response receiving stale data from your database and need to perform 16 eventually consistent reads per second of 12 KB in size each.<br/>How many RCUs do you need?
    * A. 48
    * B. 12
    * C. 192
    * D. 24
19) You have a web application hosted on EC2 that makes GET and PUT requests for objects stored in Amazon S3 using the SDK for PHP. As the security team completed the final review of your application for vulnerabilities, they noticed that your application uses hardcoded IAM access key and secret access key to gain access to AWS services. They recommend you leverage a more secure setup, which should use temporary credentials if possible.<br/>Which of the following options can be used to address the given use-case?
    * A. Hardcode the credentials in the application code
    * B. Use the SSM parameter store
    * C. Use environment variables
    * D. Use an IAM Instance Role
20) DevOps engineers are developing an order processing system where notifications are sent to a department whenever an order is placed for a product. The system also pushes identical notifications of the new order to a processing module that would allow EC2 instances to handle the fulfillment of the order. In the case of processing errors, the messages should be allowed to be re-processed at a later stage and never lost.<br/>Which of the following solutions can be used to address this use-case?
    * A. SNS + Lambda
    * B. SQS + SES
    * C. SNS + SQS
    * D. SNS + Kinesis
21) You have moved your on-premise infrastructure to AWS and are in the process of configuring an AWS Elastic Beanstalk deployment environment for production, development, and testing. You have configured your production environment to use a rolling deployment to prevent your application from becoming unavailable to users. For the development and testing environment, you would like to deploy quickly and are not concerned about downtime.<br/>Which of the following deployment policies meet your needs?
    * A. All at once
    * B. Rolling with additional batches
    * C. Rolling 
    * D. Immutable
22) Your company leverages Amazon CloudFront to provide content via the internet to customers with low latency. Aside from latency, security is another concern and you are looking for help in enforcing end-to-end connections using HTTPS so that content is protected.<br/>Which of the following options is available for HTTPS in AWS CloudFront?
    * A. Neither between clients & CloudFront nor between CloudFront & backend
    * B. Between clients & CloudFront only
    * C. Between clients & CloudFront as well as between CloudFront & backend
    * D. Between Cloudfront & backend only
23) You are working on a project that has over 100 dependencies. Every time your AWS CodeBuild runs a build step it has to resolve Java dependencies from external Ivy repositories which take a long time. Your manager wants to speed this process up in AWS CodeBuild.<br/>Which of the following will help you do this with minimal effort?
    * A. Use Instance Store type of EC2 instances to facilitate internal dependency cache
    * B. Cache depencies on S3
    * C. Reduce the number of dependencies
    * D. Ship all the dependencies as partof the source code
24) An IT company has a web application running on Amazon EC2 instances that needs read-only access to an Amazon DynamoDB table.<br/>As a Developer Associate, what is the best-practice solution you would recommend to accomplish this task?
    * A. Run application code with AWS account root user credentials to ensure full access to all AWS services
    * B. Create an IAM role with an AmazonDynamoDBReadOnlyAccess policy & apply it to the EC2 instance profile
    * C. Create an IAM user with Administrator access & configure AWS credentials for this user on the given EC2 instance
    * D. Create a new IAM user with access keys. Attach an inline policy to the IAM user with read-only access to DynamoDB. Place the keys in the code. For security, redeploy the ocde whenever the keys rotate
25) Your development team uses the AWS SDK for Java on a web application that uploads files to several Amazon S3 buckets using the SSE-KMS encryption mechanism. Developers are reporting that they are receiving permission errors when trying to push their objects over HTTP. Which of the following headers should they include in their request?
    * A. 'x-amz-server-side-encryption': 'SSE-KMS'
    * B. 'x-amz-server-side-encryption': 'AES256'
    * C. 'x-amz-server-side-encryption': 'aws:kms'
    * D. 'x-amz-server-side-encryption': 'SSE-S3'
26) A communication platform serves millions of customers and deploys features in a production environment on AWS via CodeDeploy. You are reviewing scripts for the deployment process located in the AppSec file.<br/>Which of the following options lists the correct order of lifecycle events?
    * A. BeforeInstall => ValidateService => DownloadBundle => ApplicationStart
    * B. BeforeInstall => ApplicationStart => DownloadBundle => ValidateService
    * C. ValidateService => BeforeInstall => DownloadBundle => ApplicationStart
    * D. DownloadBundle => BeforeInstall => ApplicationStart => ValidateService
27) Your mobile application needs to perform API calls to DynamoDB. You do not want to store AWS secret and access keys onto the mobile devices and need all the calls to DynamoDB made with a different identity per mobile device.<br/>Which of the following services allows you to achieve this?
    * A. Cognito User Pools
    * B. Cognito Identity Pools
    * C. IAM
    * D. Cognito Sync
28) You are storing your video files in a separate S3 bucket than your main static website in an S3 bucket. When accessing the video URLs directly the users can view the videos on the browser, but they can't play the videos while visiting the main website.<br/>What is the root cause of this problem?
    * A. Amend the IAM policy
    * B. Enable CORS
    * C. Disable Server-Side Encryption
    * D. Change the bucket policy
29) A developer has pushed a Lambda function that pushes data into an RDS MySQL database with the following Python code:
````python
def handler(event, context):
    mysql = mysqlclient.connect()
    data = event['data']
    mysql.execute(f"INSERT INTO foo (bar) VALUES (${data});")
    mysql.close()
    return
````
On the first execution, the Lambda function takes 2 seconds to execute. On the second execution and all the subsequent ones, the Lambda function takes 1.9 seconds to execute.<br/>What can be done to improve the execution time of the Lambda function?
   * A. Increase the Lambda function RAM
   * B. Change the runtime to Node.js
   * C. Move the db connection out of the handler
   * D. Upgrade the MySQL instance type
30) A cybersecurity company is publishing critical log data to a log group in Amazon CloudWatch Logs, which was created 3 months ago. The company must encrypt the log data using an AWS KMS CMK, so any future data can be encrypted to meet the company’s security guidelines.<br/>How can the company address this use-case?
    * A. Use AWS CLI `describe-log-groups` command & specify the KMS key ARN
    * B. Enable the encrypt feature on the log group via the CloudWatch Logs console
    * C. Use the AWS CLI `create-log-group` command & specify the KMS key ARN
    * D. Use the AWS CLI `associate-kms-key` command & specify the KMS key ARN
31) As a site reliability engineer, you work on building and running large-scale, distributed, fault-tolerant systems in the cloud using automation. You have just replaced the company's Jenkins based CI/CD platform with AWS CodeBuild and would like to programmatically define your build steps.<br/>Which of the following options should you choose?
    * A. Define a `buildspec.yml` file in the root directory
    * B. Define a `buildspec.yml` file in the codebuild/ directory
    * C. Define an `appspec.yml` file in the root directory
    * D. Define an `appspec.yml` file in the codebuild/ directory
32) An analytics company is using Kinesis Data Streams (KDS) to process automobile health-status data from the taxis managed by a taxi ride-hailing service. Multiple consumer applications are using the incoming data streams and the engineers have noticed a performance lag for the data delivery speed between producers and consumers of the data streams.<br/>As a Developer Associate, which of the following options would you suggest for improving the performance for the given use-case?
    * A. Swap out Kinesis Data Streams with SQS Standard queues
    * B. Swap out Kinesis Data Streams with Kinesis Data Firehose
    * C. Use Enhanced Fanout feature of Kinesis Data Streams
    * D. Swap out Kinesis Data Streams with SQS FIFO queues
33) As a site reliability engineer, you are responsible for improving the company’s deployment by scaling and automating applications. As new application versions are ready for production you ensure that the application gets deployed to different sets of EC2 instances at different times allowing for a smooth transition.<br/>Using AWS CodeDeploy, which of the following options will allow you to do this?
    * A. CodeDeploy Agent
    * B. CodeDeploy Hooks
    * C. Define CodeDeploy Applications
    * D. CodeDeploy Deployment Groups
34) You have a Java-based application running on EC2 instances loaded with AWS CodeDeploy agents. You are considering different options for deployment, one is the flexibility that allows for incremental deployment of your new application versions and replaces existing versions in the EC2 instances. The other option is a strategy in which an Auto Scaling group is used to perform a deployment.<br/>Which of the following options will allow you to deploy in this manner? (**Select two**)
    * A. In-place Deployment
    * B. Cattle Deployment
    * C. Blue/green Deployment
    * D. Warm Standby Deployment
    * E. Pilot Light Deployment
35) A firm maintains a highly available application that receives HTTPS traffic from mobile devices and web browsers. The main Developer would like to set up the Load Balancer routing to route traffic from web servers to smart.com/api and from mobile devices to smart.com/mobile. A developer advises that the previous recommendation is not needed and that requests should be sent to api.smart.com and mobile.smart.com instead.<br/>Which of the following routing options were discussed in the given use-case? (**select two**)
    * A. Web browser version
    * B. Client IP
    * C. Cookie value
    * D. Path based
    * E. Host based
36) An organization recently began using AWS CodeCommit for its source control service. A compliance security team visiting the organization was auditing the software development process and noticed developers making many git push commands within their development machines. The compliance team requires that encryption be used for this activity.<br/>How can the organization ensure source code is encrypted in transit and at rest?
    * A. Use a git command line hook to encrypt the code client side
    * B. Repositories are automatically encrypted at rest
    * C. Use AWS Lambda as a hook to encrypt the pushed code 
    * D. Enable KMS encryption
37) You are designing a high-performance application that requires millions of connections. You have several EC2 instances running Apache2 web servers and the application will require capturing the user’s source IP address and source port without the use of X-Forwarded-For.<br/>Which of the following options will meet your needs?
    * A. NLB
    * B. CLB
    * C. ELB
    * D. ALB
38) A company has configured an Auto Scaling group with health checks. The configuration is set to the desired capacity value of 3 and maximum capacity value of 3. The EC2 instances of your Auto Scaling group are configured to scale when CPU utilization is at 60 percent and is now running at 80 percent utilization.<br/>Which of the following will take place?
    * A. The desired capacity will go up to 4 & the maximum capacity will stay at 3
    * B. The desired capacity will go up to 4 & the maximum capcity will also go up to 4
    * C. System will trigger CloudWatch alarms to AWS support
    * D. System will keep running as is
39) A development team has inherited a web application running in the us-east-1 region with three availability zones (us-east-1a, us-east1-b, and us-east-1c) whose incoming web traffic is routed by a load balancer. When one of the EC2 instances hosting the web application crashes, the team realizes that the load balancer continues to route traffic to that instance causing intermittent issues.<br/>Which of the following should the development team do to minimize this problem?
    * A. Enable SSL
    * B. Enable Health Checks
    * C. Enable Stickiness
    * D. Enable Multi AZ deployments
40) You have a popular web application that accesses data stored in an Amazon S3 bucket. Developers use the SDK to maintain the application and add new features. Security compliance requests that all new objects uploaded to S3 be encrypted using SSE-S3 at the time of upload. Which of the following headers must the developers add to their request?
    * A. 'x-amz-server-side-encryption': 'SSE-KMS'
    * B. 'x-amz-server-side-encryption': 'SSE-S3'
    * C. 'x-amz-server-side-encryption': 'AES256'
    * D. 'x-amz-server-side-encryption': 'aws:kms'
41) A firm uses AWS DynamoDB to store information about people’s favorite sports teams and allow the information to be searchable from their home page. There is a daily requirement that all 10 million records in the table should be deleted then re-loaded at 2:00 AM each night.<br/>Which option is an efficient way to delete with minimal costs?
    * A. Scan & call BatchDeleteItem
    * B. Call PurgeTable
    * C. Scan & call DeleteItem
    * D. Delete then re-create the table
42) As part of internal regulations, you must ensure that all communications to Amazon S3 are encrypted.<br/>For which of the following encryption mechanisms will a request get rejected if the connection is not using HTTPS?
    * A. Client Side Encryption
    * B. SSE-KMS
    * C. SSE-C
    * D. SSE-S3
43) Your company is in the process of building a DevOps culture and is moving all of its on-premise resources to the cloud using serverless architectures and automated deployments. You have created a CloudFormation template in YAML that uses an AWS Lambda function to pull HTML files from GitHub and place them into an Amazon S3 bucket that you specify.<br/>Which of the following AWS CLI commands can you use to upload AWS Lambda functions and AWS CloudFormation templates to AWS?
    * A. `cloudformation package` & `cloudformation upload`
    * B. `cloudformation zip` & `cloudformation upload`
    * C. `cloudformation zip` & `cloudformation deploy`
    * D. `cloudformation package` & `cloudformation deploy`
44) You are planning to build a fleet of EBS-optimized EC2 instances to handle the load of your new application. Due to security compliance, your organization wants any secret strings used in the application to be encrypted to prevent exposing values as clear text.<br/>The solution requires that decryption events be audited and API calls to be simple. How can this be achieved? (**select two**)
    * A. Store the secret as SecureString in SSM Parameter Store
    * B. Encrypt first with KMS then store in SSM Parameter store
    * C. Audit using SSM Audit Trail
    * D. Store the secret as PlainText in SSM Parameter Store
    * E. Audit using CloudTrail
45) A developer is migrating an on-premises application to AWS Cloud. The application currently processes user uploads and uploads them to a local directory on the server. All such file uploads must be saved and then made available to all instances in an Auto Scaling group.<br/>As a Developer Associate, which of the following options would you recommend for this use-case?
    * A. Use Amazon S3 & make code changes in the application so all uploads are put on S3
    * B. Use Instance Store type of EC2 instances & share the files via file synchronization software
    * C. Use Amazon EBS & configure the application AMI to use a snapshot of the same EBS instance while launching new instances
    * D. Use Amazon EBS as the storage volume & share the files via file synchronization software
46) A data analytics company with its IT infrastructure on the AWS Cloud wants to build and deploy its flagship application as soon as there are any changes to the source code.<br/>As a Developer Associate, which of the following options would you suggest to trigger the deployment? (**Select two**)
    * A. Keep the source code in an Amazon EBS volume & start AWS CodePipeline whenever there are updates to the source code
    * B. Keep the source code in an AWS CodeCommit repository & start AWS CodePipeline whenever a change is pushed to the CodeCommit repository
    * C. Keep the source code in Amazon EFS & start AWS CodePipeline whenever a file is updated
    * D. Keep the source code in an Amazon S3 bucket & start AWS CodePipeline whenever a file in the S3 bucket is updated
    * E. Keep the source code in an Amazon S3 bucket & set up AWS CodePipeline to recur at an interval of every 15 minutes
47) You are getting ready for an event to show off your Alexa skill written in JavaScript. As you are testing your voice activation commands you find that some intents are not invoking as they should and you are struggling to figure out what is happening. You included the following code `console.log(JSON.stringify(this.event))` in hopes of getting more details about the request to your Alexa skill.<br/>You would like the logs stored in an Amazon S3 bucket named `MyAlexaLog`. How do you achieve this?
    * A. Use CloudWatch integration feature with Glue
    * B. Use CloudWatch integration feature with S3
    * C. Use CloudWatch integration feature with Kinesis
    * D. Use CloudWatch inegration feature with Lambda
48) You have uploaded a zip file to AWS Lambda that contains code files written in Node.Js. When your function is executed you receive the following output, 'Error: Memory Size: 3008 MB Max Memory Used'.<br/>Which of the following explains the problem?
    * A. The uncompressed zip file exceeds AWS Lambda limits
    * B. Yur zip file is corrupt
    * C. Your Lambda function ran out of RAM
    * D. You have uploaded a zip file larger than 50 MB to AWS Lambda
49) You have been hired at a company that needs an experienced developer to help with a CI/CD workflow on AWS. You configure the company’s workflow to run an AWS CodePipeline pipeline whenever the application’s source code changes in a repository hosted in AWS Code Commit and compiles source code with AWS Code Build. You are configuring ProjectArtifacts in your build stage.<br/>Which of the following should you do?
    * A. Configure AWS CodeBuild to store output artifacts on EC2 servers
    * B. Give AWS CodeCommit permissions to upload the build output to your Amazon S3 bucket
    * C. Contact AWS Support to allow AWS CodePipeline to manage build outputs
    * D. Give AWS codeBuild permissions to upload the build output to your Amazon S3 bucket
50) An e-commerce company has implemented AWS CodeDeploy as part of its AWS cloud CI/CD strategy. The company has configured automatic rollbacks while deploying a new version of its flagship application to Amazon EC2.<br/>What occurs if the deployment of the new version fails?
    * A. AWS CodePipeline promotes the most recent working deployment with a SUCCEEDED status to production
    * B. The last known working deployment is automatically restored using the snapshot stored in Amazon S3
    * C. CodeDeploy switches the Route 53 alias records back to the known good green deployment & terminates the failed blue deployment
    * D. A new deployment of the last known working version of the application is deployed with a new deployment ID
51) You manage a group of developers that are experienced with the AWS SDK for Java. You have given them a requirement to build a state machine workflow where each state executes an AWS Lambda function written in Java. Data payloads of 1KB in size will be passed between states and should allow for two retry attempts if the state fails.<br/>Which of the following options will assist your developers with this requirement?
    * A. AWS ECS
    * B. AWS Step Functions
    * C. Amazon Simple Workflow Service
    * D. CloudWatch Rules
52) You have a popular three-tier web application that is used by users throughout the globe receiving thousands of incoming requests daily. You have AWS Route 53 policies to automatically distribute weighted traffic to the API resources located at URL api.global.com.<br/>What is an alternative way of distributing traffic to a web application?
    * A. Auto Scaling
    * B. ELB
    * C. S3
    * D. CloudFront
53) Your application sends messages to an Amazon SQS queue frequently, which are then polled by another application that specifies which message to retrieve.<br/>Which of the following options describe the maximum number of messages that can be retrieved at one time?
    * A. 10
    * B. 5
    * C. 20
    * D. 100
54) You are assigned as the new project lead for a web application that processes orders for customers. You want to integrate event-driven processing anytime data is modified or deleted and use a serverless approach using AWS Lambda for processing stream events.<br/>Which of the following databases should you choose from?
    * A. ElastiCache
    * B. RDS
    * C. DynamoDB
    * D. Kinesis
55) A .NET developer team works with many ASP.NET web applications that use EC2 instances to host them on IIS. The deployment process needs to be configured so that multiple versions of the application can run in AWS Elastic Beanstalk. One version would be used for development, testing, and another version for load testing.<br/>Which of the following methods do you recommend?
    * A. Create an ALB to route based on hostname so you can pass on parameters to the development EB envrironment. Create a file in .ebextensions/ to know how to handle the traffic coming from the ALB
    * B. You can't have multiple development environmentss in EB, just one development & one production environment
    * C. Define a dev environment with a single instance & a 'load test' environment that has settings close to production environment
    * D. Use only one Beanstalk environment & perform configuration changes using an Ansible script
56) Your AWS CodeDeploy deployment to T2 instances succeed. The new application revision makes API calls to Amazon S3 however the application is not working as expected due to authorization exceptions and you were assigned to troubleshoot the issue.<br/>Which of the following should you do?
    * A. Fix the IAM permissions for the CodeDeploy service role
    * B. Enable CodeDeploy Proxy
    * C. Fix the IAM permissions for the EC2 instance role
    * D. Make the S3 bucket public
57) You are revising options that would be best for monitoring a few EC2 instances you currently manage. Amazon CloudWatch has metrics available to monitor your EC2 instances for CPU load, I/O, and network I/O. Your budget does not allow for spending on monitoring so using the default monitoring available is your preferred choice.<br/>With default monitoring, at what interval will these metrics be collected?
    * A. 2 minutes
    * B. 1 minute
    * C. 10 minutes
    * D. 5 minutes
58) You have an Amazon Kinesis Data Stream with 10 shards, and from the metrics, you are well below the throughput utilization of 10 MB per second to send data. You send 3 MB per second of data and yet you are receiving ProvisionedThroughputExceededException errors frequently.<br/>What is the likely cause of this?
    * A. You have too many shards
    * B. The partition key that you have selected isn't distributed enough
    * C. The data retention period is too long
    * D. Metrics are slow to update
59) Your company has a load balancer in a VPC configured to be internet facing. The public DNS name assigned to the load balancer is `myDns-1234567890.us-east-1.elb.amazonaws.com`. When your client applications first load they capture the load balancer DNS name and then resolve the IP address for the load balancer so that they can directly reference the underlying IP.<br/>It is observed that the client applications work well but unexpectedly stop working after a while. What is the reason for this?
    * A. Your SGs are not stable
    * B. You need to disable multi-AZ deployments
    * C. You need to enable stickiness
    * D. The LB is higly available & its public IP may change. The DNS name is constant
60) An IT company uses a blue/green deployment policy to provision new Amazon EC2 instances in an Auto Scaling group behind a new Application Load Balancer for each new application version. The current set up requires the users to log in after every new deployment.<br/>As a Developer Associate, what advice would you give to the company for resolving this issue?
    * A. Use multicast to replicate session information
    * B. Use rolling updates instead of a blue/green deployment
    * C. Use ElastiCache to maintain user sessions
    * D. Enable sticky sessions in the ALB
61) After reviewing your monthly AWS bill you notice that the cost of using Amazon SQS has gone up substantially after creating new queues; however, you know that your queue clients do not have a lot of traffic and are receiving empty responses.<br/>Which of the following actions should you take?
    * A. Use LongPolling
    * B. Use a FIFO queue
    * C. Increase the VisibilityTimeout
    * D. Decrease DelaySeconds
62) You are working for a technology startup building web and mobile applications. You would like to pull Docker images from the ECR repository called demo so you can start running local tests against the latest application version.<br/>Which of the following commands must you run to pull existing Docker images from ECR? (**Select two**)
    * A. `$(aws ecr get-login --no-include-email`
    * B. `dokcer build -t 1234567890.dkr.ecr.eu-west-1.amazonaws.com/demo:latest`
    * C. `dokcer pull 1234567890.dkr.ecr.eu-west-1.amazonaws.com/demo:latest`
    * D. `aws docker push 1234567890.dkr.ecr.eu-west-1.amazonaws.com/demo:latest`
    * E. `docker login -u $AWS_ACCESS_KEY_IP -p $AWS_SECRET_ACCESS_key1
63) You're a developer maintaining a web application written in .NET. The application makes references to public objects in a public S3 accessible bucket using a public URL. While doing a code review your colleague advises that the approach is not a best practice because some of the objects contain private data. After the administrator makes the S3 bucket private you can no longer access the S3 objects but you would like to create an application that will enable people to access some objects as needed with a time policy constraint.<br/>Which of the following options will give access to the objects?
    * A. Using IAM policy
    * B. Using pre-signed URL
    * C. Using Routing Policy
    * D. Using bucket policy
64) You are a manager for a tech company that has just hired a team of developers to work on the company's AWS infrastructure. All the developers are reporting to you that when using the AWS CLI to execute commands it fails with the following exception: You are not authorized to perform this operation. Encoded authorization failure message: 6h34GtpmGjJJUm946eDVBfzWQJk6z5GePbbGDs9Z2T8xZj9EZtEduSnTbmrR7pMqpJrVYJCew2m8YBZQf4HRWEtrpncANrZMsnzk.<br/>Which of the following actions will help developers decode the message?
    * A. AWS IAM decode-authorization-message
    * B. Use KMS decode-authorization-message
    * C. AWS Cognito Decoder
    * D. AWS STS decode-authorization-message
65) A voting system hosted on-premise was recently migrated to AWS to lower cost, gain scalability, and to better serve thousands of concurrent users. When one of the AWS resource state changes, it generates an event and will need to trigger AWS Lambda. The AWS resource whose state changes and AWS Lambda does not have direct integration.<br/>Which of the following methods can be used to trigger AWS Lambda?
    * A. AWS Lambda Custom Sources
    * B. Open a support ticket with AWS
    * C. CloudWatch Events Rules with AWS Lambda
    * D. Cron jobs to trigger AWS Lambda to check the state of your service
* [Answers](https://i.imgur.com/XdeSuFs.png)
* Score:
    * [12-11-2020 AM] 52/65 = 80%
