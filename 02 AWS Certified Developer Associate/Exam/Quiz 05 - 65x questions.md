# Quiz 05 - 65x questions

## Questions
1) You are a DynamoDB developer for an aerospace company that requires you to write 6 objects per second of 4.5KB in size each.<br/>What write capacity unit is needed for your project?
    * A. 24
    * B. 30
    * C. 15
    * D. 46
2) An IT company uses AWS CloudFormation templates to provision their AWS infrastructure for Amazon EC2, Amazon VPC, and Amazon S3 resources. Using cross-stack referencing, a developer creates a stack called `NetworkStack` which will export the `subnetId` that can be used when creating EC2 instances in another stack.<br/>To use the exported value in another stack, which of the following functions must be used?
    * A. `!Ref`
    * B. `!ImportValue`
    * C. `!Sub`
    * D. `!GetAtt`
3) Your Lambda function must use the Node.js drivers to connect to your RDS PostgreSQL database in your VPC.<br/>How do you bundle your Lambda function to add the dependencies?
    * A. Zip the function as-is with with a package.json file so that AWS Lambda can resolve the dependencies for you
    * B. Upload the ocde through the AWS console & upload the dependencies as a zip
    * C. Put the function & the dependencies in one folder & zip them together
    * D. Zip the function & the dependencies separately & upload them in AWS Lambda as two parts
4) A media company wants to migrate a video editing service to Amazon EC2 while following security best practices. The videos are sourced and read from a non-public S3 bucket.<br/>As a Developer Associate, which of the following solutions would you recommend for the given use-case?
    * A. Set up an IAM user with read-only permissions for the S3 bucket. Configure the IAM user credentials in the user data of the EC2 instance
    * B. Set up an IAM user iwth read-only permissions for the S3 bucket. Configure AWS credentials for this user via AWS CLI on the EC2 instance
    * C. Set up an EC2 service role with read-only permissions for the S3 bucket & attach the role to the EC2 instance profile
    * D. Set up an S3 service role with read-only permissions for the S3 bucket & attach the role to the EC2 instance profile
5) You are implementing a banking application in which you need to update the Exchanges DynamoDB table and the AccountBalance DynamoDB table at the same time or not at all.<br/>Which DynamoDB feature should you use?
    * A. DynamoDB Indexes
    * B. DynamoDB Transactions
    * C. DynamoDB TTL
    * D. DynamoDB Streams
6) A developer created an online shopping application that runs on EC2 instances behind load balancers. The same web application version is hosted on several EC2 instances and the instances run in an Auto Scaling group. The application uses STS to request credentials but after an hour your application stops working.<br/>What is the most likely cause of this issue?
    * A. Your IAM policy wrong
    * B. Your application needs to renew the credentials after 1 hour when they expire
    * C. A lambda function revokes your access every hour
    * D. The IAM service is experiencing downtime once an hour
7) Your company has developers worldwide with access to the company's Amazon S3 buckets. The objects in the buckets are encrypted at the server-side but need more flexibility with access control, auditing, rotation, and deletion of keys. You would also like to limit who can use the key.<br/>Which encryption mechanism best fits your needs?
    * A. SSE-C
    * B. Client Side Encryption
    * C. SSE-KMS
    * D. SSE-S3
8) A financial services company has developed a REST API which is deployed in an Auto Scaling Group behind an Application Load Balancer. The API stores the data payload in DynamoDB and the static content is served through S3. Upon analyzing the usage pattern, it's found that 80% of the read requests are shared across all users.<br/>As a Developer Associate, how can you improve the application performance while reducing the cost?
    * A. Enable ElastiCache Redis for DynamoDB & ElastiCache Memcached for S3
    * B. Enable ElastiCache Redis for DynamoDB & CloudFront for S3
    * C. Enable DAX for DynamoDB & CloudFront fro S3
    * D. Enable DAX for DynamoDB & ElastiCache Memcached for S3
9) Your company is new to cloud computing and would like to host a static HTML5 website on the cloud and be able to access it via domain www.mycompany.com. You have created a bucket in Amazon Simple Storage Service (S3), enabled website hosting, and set the index.html as the default page. Finally, you create an Alias record in Amazon Route 53 that points to the S3 website endpoint of your S3 bucket.<br/>When you test the domain www.mycompany.com you get the following error: 'HTTP response code 403 (Access Denied)'. What can you do to resolve this error?
    * A. Create an IAM role
    * B. Enable CORS
    * C. Create a bucket policy
    * D. Enable Encryption
10) A security company is requiring all developers to perform server-side encryption with customer-provided encryption keys when performing operations in AWS S3. Developers should write software with C# using the AWS SDK and implement the requirement in the PUT, GET, Head, and Copy operations.<br/>Which of the following encryption methods meets this requirement?
    * A. SSE-S3
    * B. SSE-C
    * C. Client-Side Encryption
    * D. SSE-KMS
11) A development team has a mix of applications hosted on-premises as well as on EC2 instances. The on-premises application controls all applications deployed on the EC2 instances. In case of any errors, the team wants to leverage Amazon CloudWatch to monitor and troubleshoot the on-premises application.<br/>As a Developer Associate, which of the following solutions would you suggest to address this use-case?
    * A. Upload log file from the on-premise server to an EC2 instance which further forwards the logs to CloudWatch
    * B. Upload log file from the on-premise server to S3 & let CloudWatch process the files from S3
    * C. Configure CloudWatch Logs to directly read the logs from the on-premises server
    * D. Configure the CloudWatch agent on the on-premise server by using IAM credentials with permissions for CloudWatch
12) You are looking to invoke an AWS Lambda function every hour (similar to a cron job) in a serverless way.<br/>Which event source should you use for your AWS Lambda function?
    * A. SQS
    * B. CloudWatch Events
    * C. Kinesis
    * D. Amazon S3
13) You are running a video website and provide users with S3 pre-signed URLs allowing your users to securely upload their video content onto your buckets. The average file size uploaded to your buckets is 500MB and you would like your users to efficiently send the content.<br/>What would you recommend doing in the client SDK?
    * A. Zip the video file before sending
    * B. Upload as one part
    * C. Use SSE-S3 encryption
    * D. Do a multi-part upload
14) You are working for a small organization that does not have a database administrator and the organization needs to install a database on the cloud quickly to support an accounting application used by thousands of users. The application will act as a backend and will perform CRUD operations as well as inner joins.<br/>Which database is best suited for this scenario?
    * A. DynamoDb
    * B. Redshift
    * C. RDS
    * D. ElastiCache
15) You are working with a t2.small instance bastion host that has the AWS CLI installed to help manage all the AWS services installed on it. You would like to know the security group and the instance id of the current instance.<br/>Which of the following will help you fetch the needed information?
    * A. Query the user data at http://254.169.254.169/latest/meta-data
    * B. Create an IAM role an attach it to your EC2 instance that helps you perform a 'describe' API call
    * C. Query the user data at http://169.254.169.254/latest/user-data
    * D. Query the metadata at http://169.254.169.254/latest/meta-data
16) Your team lead has finished creating a CodeBuild project in the management console and a build spec has been defined for the project. After the build is run, CodeBuild fails to pull a Docker image into the build environment.<br/>What is the most likely cause?
    * A. The Docker iamge is too big
    * B. The Docker image is missing some tags
    * C. Missing IAM permissions for the CodeBuild Service
    * D. CodeBuild can't work with custom Docker images
17) You are responsible for an application that runs on multiple Amazon EC2 instances. In front of the instances is an Internet-facing load balancer that takes requests from clients over the internet and distributes them to the EC2 instances. A health check is configured to ping the index.html page found in the root directory for the health status. When accessing the website via the internet visitors of the website receive timeout errors.<br/>What should be checked first to resolve the issue?
    * A. SGs
    * B. The application is down
    * C. The ALB is warming up
    * D. IAM Roles
18) One of your Kinesis Stream is experiencing increased traffic due to a sale day. Therefore your Kinesis Administrator has split shards and thus you went from having 6 shards to having 10 shards in your Kinesis Stream. Your consuming application is running a KCL-based application on EC2 instances.<br/>What is the maximum number of EC2 instances that can be deployed to process the shards?
    * A. 1
    * B. 20
    * C. 6
    * D. 10
19) You are using AWS SQS FIFO queues to get the ordering of messages on a per `user_id` basis.<br/>As a developer, which message parameter should you set the value of `user_id` to guarantee the ordering?
    * A. MessageDeduplicationId
    * B. MessageGroupId
    * C. MessageHash
    * D. MessageOrderId
20) Your client has tasked you with finding a service that would enable you to get cross-account tracing and visualization.<br/>Which service do you recommend?
    * A. VPC Flow Logs
    * B. CloudWatch Events
    * C. AWS X-Ray
    * D. CloudTrail
21) Your company likes to operate multiple AWS accounts so that teams have their environments. Services deployed across these accounts interact with one another, and now there's a requirement to implement X-Ray traces across all your applications deployed on EC2 instances and AWS accounts.<br/>As such, you would like to have a unified account to view all the traces. What should you in your X-Ray daemon set up to make this work? (**Select two**)
    * A. Create a user in the target unified account & generate access & secret keys
    * B. Configure the X-Ray daemon to use an IAM instance role
    * C. Enable Cross Acount collection in the X-Ray console
    * D. Configure the X-Ray daemon to use access & secret keys
    * E. Create a role in the target unified account & allow roles in each sub-account to assume the role
22) As part of your video processing application, you are looking to perform a set of repetitive and scheduled tasks asynchronously. Your application is deployed on Elastic Beanstalk.<br/>Which Elastic Beanstalk environment should you set up for performing the repetitive tasks?
    * A. Setup a Worker environment & a `.ebextensions` file
    * B. Setup a Web Server environment & a `cron.yaml` file
    * C. Setup a Worker environment & a `cron.yaml` file
    * D. Setup a Web Server environment & a `ebextensions` file
23) You would like to paginate the results of an S3 List to show 100 results per page to your users and minimize the number of API calls that you will use.<br/>Which CLI options should you use? (**Select two**)
    * A. --starting-token
    * B. --page-size
    * C. --limit
    * D. --max-items
    * E. --next-token
24) You would like to retrieve a subset of your dataset stored in S3 with the CSV format. You would like to retrieve a month of data and only 3 columns out of the 10.<br/>You need to minimize compute and network costs for this, what should you use?
    * A. S3 Inventory
    * B. S3 Select
    * C. S3 Analytics
    * D. S3 Access Logs
25) Your organization has set up a full CI/CD pipeline leveraging CodePipeline and the deployment is done on Elastic Beanstalk. This pipeline has worked for over a year now but you are approaching the limits of Elastic Beanstalk in terms of how many versions can be stored in the service.<br/>How can you remove older versions that are not used by Elastic Beanstalk so that new versions can be created for your applications?
    * A. Setup an `ebextensions` file
    * B. Define a Lambda function
    * C. Use Worker Environments
    * D. Use a Lifecycle Policy
26) Your client wants to deploy a service on EC2 instances, and as EC2 instances are added into an ASG, each EC2 instance should be running 3 different Docker Containers simultaneously.<br/>What Elastic Beanstalk platform should they choose?
    * A. Docker multi-container platform
    * B. Third-party platform
    * C. Custom platform
    * D. Docker single-container platform
27) You are running a public DNS service on an EC2 instance where the DNS name is pointing to the IP address of the instance. You wish to upgrade your DNS service but would like to do it without any downtime.<br/>Which of the following options will help you accomplish this?
    * A. EIP
    * B. Create a LB & an ASG
    * C. Prove a static private IP
    * D. Use Route 53
28) Your e-commerce company needs to improve its software delivery process and is moving away from the waterfall methodology. You decided that every application should be built using the best CI/CD practices and every application should be packaged and deployed as a Docker container. The Docker images should be stored in ECR and pushed with AWS CodePipeline and AWS CodeBuild.<br/>When you attempt to do this, the last step fails with an authorization issue. What is the most likely issue?
    * A. The ECR repository is stale, you must delete & re-create it
    * B. CodeBuild can't talk to ECR because of SG issues
    * C. The ECS instances are misconfigured & must contain additional data in /etc/ecs/ecs.config
    * D. The IAM permissions are wrong for the CodeBuild service
29) You are a developer working on AWS Lambda functions that are triggered by Amazon API Gateway and would like to perform testing on a low volume of traffic for new API versions.<br/>Which of the following features will accomplish this task?
    * A. Custom Authorizers
    * B. Stage Variables 
    * C. Mapping Templates
    * D. Canary Deployment
30) You have been collecting AWS X-Ray traces across multiple applications and you would now like to index your XRay traces to search and filter through them efficiently.<br/>What should you use in your instrumentation?
    * A. Segments
    * B. Metadata
    * C. Annotations
    * D. Sampling
31) An EC2 instance has an IAM instance role attached to it, providing it read and write access to the S3 bucket 'my_bucket'. You have tested the IAM instance role and both reads and writes are working. You then remove the IAM role from the EC2 instance and test both read and write again. Writes stopped working but reads are still working.<br/>What is the likely cause of this behavior?
    * A. The EC2 instance is using cached temporary IAM credentials
    * B. Removing an instance role from an EC2 instance can take a few minutes before being active
    * C. The S3 bucket policy authorize reads
    * D. When a read is done on a bucket, there's a grace period of 5 minutes to do the same read again
32) A popular mobile app retrieves data from an AWS DynamoDB table that was provisioned with RCU’s that are evenly shared across four partitions. One of those partitions is receiving more traffic than the other partitions, causing hot partition issues.<br/>What technology will allow you to reduce the read traffic on your AWS DynamoDB table with minimal effort?
    * A. More partitions
    * B. ElastiCache
    * C. DynamoDB Streams
    * D. DynamoDB DAX
33) You need to load SSL certificates onto your Load Balancers and also have EC2 instances dynamically retrieve them when needed for service to service two-way TLS communication.<br/>What service should you use to centrally manage these SSL certificates?
    * A. S3
    * B. IAM
    * C. KMS
    * D. ACM
34) Which of the following CLI options will allow you to retrieve a subset of the attributes coming from a DynamoDB scan?
    * A. --projection-expression
    * B. --page-size
    * C. --filter-expression
    * D. --max-items
35) Your company is shifting towards ECS to deploy applications. The process should be automated using the AWS CLI to create a service where at least ten instances of a task definition are kept running under the default cluster.<br/>Which of the following commands should be executed?
    * A. `aws ecs create-service --service-name ecs-simple-service --task-definition ecs-demo --desired-count 10`
    * B. `aws ecs run-task --cluster default --task-definition ecs-demo`
    * C. `aws ecr create-service --service-name ecs-simple-service --task-definition ecs-demo --desired-count 10`
    * D. `docker -compose create ecs-simple-service`
36) You would like to run the X-Ray daemon for your Docker containers deployed using AWS Fargate.<br/>What do you need to do to ensure the setup will work? (**Select two**)
    * A. Deploy the X-Ray daemon agent as a sidecar container
    * B. Deploy the X-Ray daemon agent as a daemon set on ECS
    * C. Provide the correct IAM task role to the X-Ray container
    * D. Provide the correct IAM instance role to the EC2 instance
    * E. Deploy the X-Ray daemon agent as a process on your EC2 instance
37) You have created a DynamoDB table to support your application and provisioned RCU and WCU to it so that your application has been running for over a year now without any throttling issues. Your application now requires a second type of query over your table and as such, you have decided to create an LSI and a GSI on a new table to support that use case. One month after having implemented such indexes, it seems your table is experiencing throttling.<br/>Upon looking at the table's metrics, it seems the RCU and WCU provisioned are still sufficient. What's happening?
    * A. Adding both an LSI & a GSI to a table is not recommended by AWS best practices as this is a known cause for creating throttles
    * B. Metrics are lagging in your CloudWatch dashboard & you should see the RCU & WCU peaking for the main table in a few minutes
    * C. The GSI is throttling so you need to provision more RCU & WCU to the GSI
    * D. The LSI is throttling so you need to provision more RCU & WCU to the LSI
38) You have created a test environment in Elastic Beanstalk and as part of that environment, you have created an RDS database.<br/>How can you make sure the database can be explored after the environment is destroyed?
    * A. Change the EB environment variables
    * B. Convert the EB environment to a worker environment
    * C. Make a snapshot of the db before it gets deleted
    * D. Make a selective delete in EB
39) A media analytics company has built a streaming application on Lambda using SAM.<br/>As a Developer Associate, which of the following would you identify as the correct order of execution to successfully deploy the application?
    * A. Develop the SAM template locally => deploy the template to S3 => use your application in the cloud
    * B. Develop the SAM template locally => upload the template to CodeCommit => deploy your application to CodeDeploy
    * C. Develop the SAM template locally => upload the template to Lambda => deploy your application to the cloud
    * D. Develop the SAM template locally => upload the template to S3 => deploy your application to the cloud
40) Your company wants to move away from manually managing Lambda in the AWS console and wants to upload and update them using AWS CloudFormation.<br/>How do you declare an AWS Lambda function in CloudFormation? (**Select two**)
    * A. Upload all the code as a zip to S3 & refer the object in `AWS::Lambda::Function` block
    * B. Write the AWS Lambda code inline in CloudFormation in the `AWS::Lambda::Function` block & reference the dependencies as a zip file stored in S3
    * C. Upload the code to CodeCommit & refer to the CodeCommit Repository in `AWS::Lambda::Function` block
    * D. Upload all the code as a folder to S3 & refer the folder in `AWS::Lambda::Function` block
    * E. Write the AWS Lambda code inline in CloudFormation in the `AWS::Lambda::Function` block as long as there are no third-party
41) You are storing bids information on your betting application and you would like to automatically expire DynamoDB table data after one week.<br/>What should you use?
    * A. Use DynamoDB Streams
    * B. Use a Lambda function
    * C. Use DAX
    * D. Use TTL
42) Your development team has created a popular mobile app written for Android. The team is looking for a technology that can send messages to mobile devices using a mobile app.<br/>Mobile app users will register and be given permissions to access AWS resources. Which technology would you recommend for subscribing users to messages?
    * A. SES
    * B. Kinesis
    * C. SQS
    * D. SNS
43) You are running a web application where users can author blogs and share them with their followers. Most of the workflow is read based, but when a blog is updated, you would like to ensure that the latest data is served to the users (no stale data). The Developer has already suggested using ElastiCache to cope with the read load but has asked you to implement a caching strategy that complies with the requirements of the site.<br/>Which strategy would you recommend?
    * A. Use DAX
    * B. Use a Write Through strategy
    * C. Use a Lazy Loading strategy with TTL
    * D. Use a Lazy Loading strategy without TTL
44) A development team has created AWS CloudFormation templates that are reusable by taking advantage of input parameters to name resources based on client names.<br/>You would like to save your templates on the cloud, which storage option should you choose?
    * A. S3
    * B. EBS
    * C. ECR
    * D. EFS
45) Your organization has a single Amazon S3 bucket that contains folders labeled with customer names. Several administrators have IAM access to the S3 bucket and versioning is enabled to easily recover from unintended user actions.<br/>Which of the following statements about versioning is NOT true based on this scenario?
    * A. Versioning can be enabled only for a specific folder
    * B. Any file that was unversioned before enabling versioning will have the 'null' version
    * C. Deleting a file is a recoverable operation
    * D. Overwriting a file increases its versions
46) Your Lambda function processes files for your customers and as part of that process, it creates a lot of intermediary files it needs to store on its disk and then discard.<br/>What is the best way to store temporary files for your Lambda functions that will be discarded when the function stops running?
    * A. Use the local directory /tmp
    * B. Create a tmp/ direcotry in the source zip file & use it
    * C. Use the local directory /opt
    * D. Use an S3 bucket
47) You would like to deploy a Lambda function globally so that requests are filtered at the AWS edge locations.<br/>Which Lambda deployment mode do you need?
    * A. Deploy Lambda in S3
    * B. Deploy Lambda in a Global VPC
    * C. Use a Global DynamoDB table as a Lambda source
    * D. Use a Lambda@Edge
48) You've just deployed an AWS Lambda function. The lambda function will be invoked via the API Gateway. The API Gateway will need to control access to it.<br/>Which of the following mechanisms is not supported for API Gateway?
    * A. STS
    * B. Cognito User Pools
    * C. IAM permissions with sigv4
    * D. Lambda Authorizer
49) Your team has just signed up an year-long contract with a client maintaining a three-tier web application, that needs to be moved to AWS Cloud. The application has steady traffic throughout the day and needs to be on a reliable system with no down-time or access issues. The solution needs to be cost-optimal for this startup.<br/>Which of the following options should you choose?
    * A. Amazon EC2 On Demand Instances
    * B. On-premise EC2 instance
    * C. Amazon EC2 Spot Instances
    * D. Amazon EC2 Reserved Instances
50) Applications running on EC2 instances process messages from an SQS queue but sometimes they experience errors due to messages not being processed.<br/>To isolate the messages, which option will help with further debugging?
    * A. Reduce the VisibilityTimeout
    * B. Implement a DLQ
    * C. Increase the VisibilityTimeout
    * D. Use DeleteMessage
51) Which environment variable can be used by AWS X-Ray SDK to ensure that the daemon is correctly discovered on ECS?
    * A. AWS_XRAY_TRACING_NAME
    * B. AWS_XRAY_DAEMON_ADDRESS
    * C. AWS_XRAY_DEBUG_MODE
    * D. AWS_XRAY_CONTEXT_MISSING
52) You would like your Elastic Beanstalk environment to expose an HTTPS endpoint and an HTTP endpoint. The HTTPS endpoint should be used to get in-flight encryption between your clients and your web servers, while the HTTP endpoint should only be used to redirect traffic to HTTPS and support URLs starting with http://.
What must be done to configure this setup? (**Select three**)
    * A. Configure your EC2 instances to redirect HTTP traffic to HTTPS
    * B. Open up port 80 & port 443
    * C. Assign an SSL certificate to the LB
    * D. Only open up port 443
    * E. Only open up port 80
    * F. Configure your EC2 instances to redirect HTTPS to HTTP
53) Your web application front end consists of 5 EC2 instances behind an Application Load Balancer. You have configured your web application to capture the IP address of the client making requests. When viewing the data captured you notice that every IP address being captured is the same, which also happens to be the IP address of the Application Load Balancer.<br/>What should you do to identify the true IP address of the client?
    * A. Look into the X-Forwarded-For header in the backend
    * B. Modify the front-end of the website so that the users send their IP in the requests
    * C. Look into the X-Forwarded-Proto header in the backend
    * D. Look into the client's cookie
54) You are creating a web application in which users can follow each other. Some users will be more popular than others and thus their data will be requested very often. Currently, the user data sits in RDS and it has been recommended by your Developer to use ElastiCache as a caching layer to improve the read performance. The whole dataset of users cannot sit in ElastiCache without incurring tremendous costs and therefore you would like to cache only the most often requested users profiles there. As your website is high traffic, it is accepted to have stale data for users for a while, as long as the stale data is less than a minute old.<br/>What caching strategy do you recommend implementing?
    * A. Use a Lazy Loading strategy without TTL
    * B. Use Write Through strategy with TTL
    * C. Use Write Through strategy without TTL
    * D. Use a Lazy Loading strategy with TTL
55) You would like to have a one-stop dashboard for all the CI/CD needs of one of your projects. You don't need heavy control of the individual configuration of each component in your CI/CD, but need to be able to get a holistic view of your projects.<br/>Which service do you recommend?
    * A. CodeStar
    * B. CodePipeline
    * C. CodeBuild
    * D. CodeDeploy
56) A data analytics company ingests a large number of messages and stores them in an RDS database using Lambda. Because of the increased payload size, it is taking more than 15 minutes to process each message.<br/>As a Developer Associate, which of the following options would you recommend to process each message in the MOST scalable way?
    * A. Provision EC2 instances in an ASG to poll the messages from an SQS queue
    * B. Contact AWS Support to increase the Lambda timeout to 60 minutes
    * C. Use DynamoDB instead of RDS as db
    * D. Provision an EC2 instance to poll the messages from an SQS queue
57) When your company first created an AWS account, you began with a single sign-in principal called a root user account that had complete access to all AWS services and resources.<br/>What should you do to adhere to best practices for using the root user account?
    * A. It should be accessible using the access key id & secret access key
    * B. It should be accessible by one admin only after enabling Multi-factor authentication
    * C. It should be accessible by 3 to 6 members of the IT team
    * D. It should be accessible by no one, throw away the passwords after creating the account
58) You are a cloud security engineer working for a popular cyber-forensics company that offers vulnerability scanning solutions to government contractors. The scanning solutions are integrated with AWS resources to monitor EC2 and S3 API calls which then display results to users on an analytical dashboard.<br/>Which of the following AWS services makes this possible?
    * A. CloudTrail
    * B. S3 Access Logs
    * C. IAM 
    * D. VPC Flow Logs
59) You are using AWS SQS FIFO queues to get the ordering of messages on a per user_id basis. On top of this, you would like to make sure that duplicate messages should not be sent to SQS as this would cause application failure.<br/>As a developer, which message parameter should you set for deduplicating messages?
    * A. ContentBasedDeduplication
    * B. MessageGroupId
    * C. ReceiveRequestAttemptId
    * D. MessageDeduplicaitonId
60) You are deploying Lambda functions that operate on your S3 buckets to read files and extract key metadata. The Lambda functions are managed using SAM.<br/>Which Policy should you insert in your serverless model template to give buckets read access?
    * A. SQSPollerPolicy
    * B. S3ReadPolicy
    * C. LambdaInvokePolicy
    * D. S3CrudPolicy
61) You were assigned to a project that requires the use of the AWS CLI to build a project with AWS CodeBuild. Your project's root directory includes the buildspec.yml file to run build commands and would like your build artifacts to be automatically encrypted at the end.<br/>How should you configure CodeBuild to accomplish this?
    * A. Specify a KMS key to use
    * B. Use In Flight encryption (SSL)
    * C. Use an AWS Lambda Hook
    * D. Use AWS Encryption SDK
62) The development team at an e-commerce company is preparing for the upcoming Thanksgiving sale. The product manager wants the development team to implement appropriate caching strategy on Amazon ElastiCache to withstand traffic spikes on the website during the sale. A key requirement is to facilitate consistent updates to the product prices and product description, so that the cache never goes out of sync with the backend.<br/>As a Developer Associate, which of the following solutions would you recommend for the given use-case?
    * A. Use a caching strategy to write to the cache directly & sync the backend at a later time
    * B. Use a caching strategy to update the cache & the backend at the same time
    * C. Use a caching strategy to write to the backend first & wait for the cache to expire via TTL
    * D. Use a caching strategy to write to the backend first & then invalidate the cache
63) Your AWS account is now growing to 200 users and you would like to provide each of these users a personal space in the S3 bucket 'my_company_space' with the prefix `/home/<username>`, where they have read/write access.<br/>How can you do this efficiently?
    * A. Create one customer-managed policy with policy variables & attach to a group of all users
    * B. Create one customer-managed policy per user & attach them to the relevant users
    * C. Create inline policies for each user as they are onboarded
    * D. Create an S3 bucket policy & change it as users are added & removed
64) You would like your Elastic Beanstalk environment to expose an HTTPS endpoint instead of an HTTP endpoint to get in-flight encryption between your clients and your web servers.<br/>What must be done to set up HTTPS on Beanstalk?
    * A. Create an .ebextentions file to configure the LB
    * B. Configure Health Checks
    * C. Open up the port 80 for the SG
    * D. Use a separate CloudFormation template to load the SSL certificate into the Lb
65) An IT company leverages CodePipeline to automate its release pipelines. The development team wants to write a Lambda function that will send notifications for state changes within the pipeline.<br/>As a Developer Associate, which steps would you suggest to associate the Lambda function with the event source?
    * A. Set up an Amazon CloudWatch Events rule that uses CodePipeline as an event source with the target as the Lambda function
    * B. Use the Lambda console to configure a trigger that invokes the Lambda function with CodePipeline as the event source
    * C. Set up an Amazon CloudWatch alarm that monitors status changes in CodePipeline & triggers the Lambda function
    * D. Use the CodePipeline console to set up a trigger for the Lambda function
* [Answers](https://i.imgur.com/f1dae10.png)
* Score:
    * [12-11-2020 PM] 48/65 = 73%
