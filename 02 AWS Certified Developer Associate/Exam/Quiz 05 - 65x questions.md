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
28)
29)
30)
31)
32)
33)
34)
35)
36)
37)
38)
39)
40)
41)
42)
43)
44)
45)
46)
47)
48)
49)
50)
51)
52)
53)
54)
55)
56)
57)
58)
59)
60)
61)
62)
63)
64)
65)
* [Answer]()
* Score:
    * [12-11-2020 PM] 48/65 = 73%
