# 136x questions

## URL
* [CertQueeen Free Exam Dumps to Test Online](https://freedumps.certqueen.com/dva-c01-aws-certified-developer-associate-exam-dumps/)

## Questions
1) A company is using Amazon API Gateway to manage its public-facing API. The CISO requires that the APIs be used by test account users only.
What is the MOST secure way to restrict API access to users of this particular AWS account?
    * A. Client-side SSL certificates for authentication
    * B. API Gateway resource policies
    * C. Cross-origin resource sharing (CORS)
    * D. Usage plans
2) A Developer is migrating existing applications to AWS. These applications use MongoDB as their primary data store, and they will be deployed to Amazon EC2 instances. Management requires that the Developer minimize changes to applications while using AWS services.
Which solution should the Developer use to host MongoDB in AWS?
    * A. Install MongoDB on the same instance where the application is running.
    * B. Deploy Amazon DocumentDB in MongoDB compatibility mode.
    * C. Use Amazon API Gateway to translate API calls from MongoDB to Amazon DynamoDB
    * D. Replicate the existing MongoDB workload to Amazon DynamoDB
3) A company requires that AWS Lambda functions written by Developers log errors so System Administrators can more effectively troubleshoot issues.
What should the Developers implement to meet this need?
    * A. Publish errors to a dedicated Amazon SQS queue.
    * B. Create an Amazon CloudWatch Events event trigger based on certain Lambda events.
    * C. Report errors through logging statements in Lambda function code.
    * D. Set up an Amazon SNS topic that sends logging statements upon failure
4) A Developer needs to deploy an application running on AWS Fargate using Amazon ECS. The application has environment variables that must be passed to a container for the application to initialize.
How should the environment variables be passed to the container?
    * A. Define an array that includes the environment variables under the environment parameter within the service definition.
    * B. Define an array that includes the environment variables under the environment parameter within the task definition.
    * C. Define an array that includes the environment variables under the entryPoint parameter within the task definition.
    * D. Define an array that includes the environment variables under the entryPoint parameter within the service definition.
5) A company's fleet of Amazon EC2 instances receives data from millions of users through an API. The servers batch the data, add an object for each user, and upload the objects to an S3 bucket to ensure high access rates. The object attributes are Customer ID, Server ID, TS-Server (TimeStamp and Server ID), the size of the object, and a timestamp. A Developer wants to find all the objects for a given user collected during a specified time range.
After creating an S3 object created event, how can the Developer achieve this requirement?
    * A. Execute an AWS Lambda function in response to the S3 object creation events that creates an Amazon DynamoDB record for every object with the Customer ID as the partition key and the Server ID as the sort key. Retrieve all the records using the Customer ID and Server ID attributes.
    * B. Execute an AWS Lambda function in response to the S3 object creation events that creates an Amazon Redshift record for every object with the Customer ID as the partition key and TS-Server as the sort key. Retrieve all the records using the Customer ID and TS-Server attributes.
    * C. Execute an AWS Lambda function in response to the S3 object creation events that creates an Amazon DynamoDB record for every object with the Customer ID as the partition key and TS-Server as the sort key. Retrieve all the records using the Customer ID and TS-Server attributes.
    * D. Execute an AWS Lambda function in response to the S3 object creation events that creates an Amazon Redshift record for every object with the Customer ID as the partition key and the Server ID as the sort key. Retrieve all the records using the Customer ID and Server ID attributes.
6) A company is managing a NoSQL database on-premises to host a critical component of an application, which is starting to have scaling issues.
The company wants to migrate the application to Amazon DynamoDB with the following considerations:
  * - Optimize frequent queries
  * - Reduce read latencies
  * - Plan for frequent queries on certain key attributes of the table
 Which solution would help achieve these objectives?
    * A. Create global secondary indexes on keys that are frequently queried. Add the necessary attributes into the indexes.
    * B. Create local secondary indexes on keys that are frequently queried. DynamoDB will fetch needed attributes from the table.
    * C. Create DynamoDB global tables to speed up query responses. Use a scan to fetch data from the table.
    * D. Create an AWS Auto Scaling policy for the DynamoDB table.
7) A developer is writing an application that will process data delivered into an Amazon S3 bucket. The data is delivered approximately 10 times a day, and the developer expects the data will be processed in less than 1 minute, on average.
How can the developer deploy and invoke the application with the lowest cost and lowest latency?
    * A. Deploy the application as an AWS Lambda function and invoke it with an Amazon CloudWatch alarm triggered by an S3 object upload.
    * B. Deploy the application as an AWS Lambda function and invoke it with an S3 event notification.
    * C. Deploy the application as an AWS Lambda function and invoke it with an Amazon CloudWatch scheduled event.
    * D. Deploy the application onto an Amazon EC2 instance and have it poll the S3 bucket for new objects.
8) A developer converted an existing program to an AWS Lambda function in the console. The program runs properly on a local laptop, but shows an “Unable to import module” error when tested in the Lambda console.
Which of the following can fix the error?
    * A. Install the missing module and specify the current directory as the target. Create a ZIP file to include all files under the current directory, and upload the ZIP file.
    * B. Install the missing module in a lib directory. Create a ZIP file to include all files under the lib directory, and upload the ZIP file as dependency file.
    * C. In the Lambda code, invoke a Linux command to install the missing modules under the /usr/lib directory.
    * D. In the Lambda console, create a LB_LIBRARY_PATH environment and specify the value for the system library plan.
9) A front-end web application is using Amazon Cognito user pools to handle the user authentication flow. A developer is integrating Amazon DynamoDB into the application using the AWS SDK for JavaScript.
How would the developer securely call the API without exposing the access or secret keys?
  * A. Configure Amazon Cognito identity pools and exchange the JSON Web Token (JWT) for temporary credentials.
  * B. Run the web application in an Amazon EC2 instance with the instance profile configured.
  * C. Hardcore the credentials, use Amazon S3 to host the web application, and enable server-side encryption.
  * D. Use Amazon Cognito user pool JSON Web Tokens (JWITs) to access the DynamoDB APIs.
10)  A developer needs to manage AWS infrastructure as code and must be able to deploy multiple identical copies of the infrastructure, stage changes, and revert to previous versions.
Which approach addresses these requirements?
  * A. Use cost allocation reports and AWS OpsWorks to deploy and manage the infrastructure.
  * B. Use Amazon CloudWatch metrics and alerts along with resource tagging to deploy and manage the infrastructure.
  * C. Use AWS Elastic Beanstalk and AWS CodeCommit to deploy and manage the infrastructure.
  * D. Use AWS CloudFormation and AWS CodeCommit to deploy and manage the infrastructure.
11)  What is required to trace Lambda-based applications with AWS X-Ray?
  * A. Send logs from the Lambda application to an S3 bucket; trigger a Lambda function from the bucket to send data to AWS X-Ray.
  * B. Trigger a Lambda function from the application logs in Amazon CloudWatch to submit tracing data to AWS X-Ray.
  * C. Use an IAM execution role to give the Lambda function permissions and enable tracing.
  * D. Update and add AWS X-Ray daemon code to relevant parts of the Lambda function to set up the trace.
12) A development team is building a new application that will run on Amazon EC2 and use Amazon DynamoDB as a storage layer. The developers all have assigned IAM user accounts in the same IAM group. The developers currently can launch EC2 instances, and they need to be able to launch EC2 instances with an instance role allowing access to Amazon DynamoDB.
Which AWS IAM changes are needed when creating an instance role to provide this functionality?
  * A. Create an IAM permission policy attached to the role that allows access to DynamoDB
  * B. Add a trust policy to the role that allows DynamoDB to assume the role. Attach a permissions policy to the development group in AWS IAM that allows developers to use the iam:GetRole and iam:PassRole permissions for the role.
  * C. Create an IAM permissions policy attached to the role that allows access to DynamoDB
  * D. Add a trust policy to the role that allows Amazon EC2 to assume the role. Attach a permissions policy to the development group in AWS IAM that allows developers to use the iam:PassRole permission for the role.
  * E. Create an IAM permission policy attached to the role that allows access to Amazon EC2. Add a trust policy to the role that allows DynamoDB to assume the role. Attach a permissions policy to the development group in AWS IAM that allows developers to use the iam:PassRole permission for the role.
  * F. Create an IAM permissions policy attached to the role that allows access to DynamoDB
  * G. Add a trust policy to the role that allows Amazon EC2 to assume the role. Attach a permissions policy to the development group in AWS IAM that allows developers to use the iam:GetRole permission for the role.
13)  A developer is migrating code to an AWS Lambda function that will an Amazon Aurora MySQL database.
What is the MOST secure way to authenticate the function to the database?
  * A. Store the database credentials as encrypted parameters in AWS Systems Manager Parameters Store. Obtain the credentials from Systems Manager when the Lambda function needs to connect to the database.
  * B. Store the database credentials in AWS Secrets Manager. Let Secrets Manager handle the rotation of the credentials, as required.
  * C. Store the database credentials in an Amazon S3 bucket that has a restrictive bucket policy for the Lambda role when accessing the credentials. Use AWS KMS to encrypt the data.
  * D. Create a policy with rds-db:connect access to the database and attach it to the role assigned to the Lambda function.
14) A development team uses AWS Elastic Beanstalk for application deployment. The team has configured the application version lifecycle policy to limit the number of application versions to 25.
However, even with the lifecycle policy, the source bundle is deleted from the Amazon S3 source bucket.
What should a developer do in the Elastic Beanstalk application version lifecycle settings to retain the source code in the S3 bucket?
  * A. Change the Set the application versions limit by total count setting to zero.
  * B. Disable the Lifecycle policy setting.
  * C. Change the Set the application version limit by age setting to zero.
  * D. Set Retention to Retain source bundle in S3.
15) A developer has built a market application that stores pricing data in Amazon DynamoDB with Amazon ElastiCache in front. The prices of items in the market change frequently. Sellers have begun complaining that, after they update the price of an item, the price does not actually change in the product listing.
What could be causing this issue?
  * A. The cache is not being invalidated when the price of the item is changed
  * B. The price of the item is being retrieved using a write-through ElastiCache cluster
  * C. The DynamoDB table was provisioned with insufficient read capacity
  * D. The DynamoDB table was provisioned with insufficient write capacity
16)  A developer is provided with an HTTPS clone URL for an AWS CodeCommit repository.
What needs to be configured before cloning this repository?
  * A. Use AWS KMS to set up public and private keys for use with AWS CodeCommit.
  * B. Set up the Git credential helper to use an AWS credential profile, and enable the helper to send the path to the repositories.
  * C. Use AWS Certificate Manager to provision public and private SSL/TLS certificates.
  * D. Generate encryption keys using AWS CloudHSM, then export the key for use with AWS CodeCommit.
17)  A developer is building an application using an Amazon API Gateway REST API backend by an AWS Lambda function that interacts with an Amazon DynamoDB table. During testing, the developer observes high latency when making requests to the API.
How can the developer evaluate the end-to-end latency and identify performance bottlenecks?
  * A. Enable AWS CloudTrail logging and use the logs to map each latency and bottleneck.
  * B. Enable and configure AWS X-Ray tracing on API Gateway and the Lambda function. Use X-Ray to trace and analyze user requests.
  * C. Enable Amazon CloudWatch Logs for the Lambda function. Enable execution logs for API Gateway to view and analyze user request logs.
  * D. Enable VPC Flow Logs to capture and analyze network traffic within the VP
18) A developer is writing an AWS Lambda function. The developer wants to log key events that occur during the Lambda function and include a unique identifier to associate the events with a specific function invocation.
Which of the following will help the developer accomplish this objective?
  * A. Obtain the request identifier from the Lambda context object. Architect the application to write logs to the console.
  * B. Obtain the request identifier from the Lambda event object. Architect the application to write logs to a file.
  * C. Obtain the request identifier from the Lambda event object. Architect the application to write logs to the console.
  * D. Obtain the request identifier from the Lambda context object. Architect the application to write logs to a file.
19) An IAM role is attached to an Amazon EC2 instance that explicitly denies access to all Amazon S3 API actions. The EC2 instance credentials file specifies the IAM access key and secret access key, which allow full administrative access.
Given that multiple modes of IAM access are present for this EC2 instance, which of the following is correct?
  * A. The EC2 instance will only be able to list the S3 buckets.
  * B. The EC2 instance will only be able to list the contents of one S3 bucket at a time.
  * C. The EC2 instance will be able to perform all actions on any S3 bucket.
  * D. The EC2 instance will not be able to perform any S3 action on any S3 bucket.
20) Two containerized microservices are hosted on Amazon EC2 ECS. The first microservice reads an Amazon RDS Aurora database instance, and the second microservice reads an Amazon DynamoDB table.
How can each microservice be granted the minimum privileges?
  * A. Set ECS_ENABLE_TASK_IAM_ROLE to false on EC2 instance boot in ECS agent configuration file. Run the first microservice with an IAM role for ECS tasks with read-only access for the Aurora database. Run the second microservice with an IAM role for ECS tasks with read-only access to DynamoDB
  * B. Set ECS_ENABLE_TASK_IAM_ROLE to false on EC2 instance boot in the ECS agent configuration file. Grant the instance profile role read-only access to the Aurora database and DynamoDB
  * C. Set ECS_ENABLE_TASK_IAM_ROLE to true on EC2 instance boot in the ECS agent configuration file. Run the first microservice with an IAM role for ECS tasks with read-only access for the Aurora database. Run the second microservice with an IAM role for ECS tasks with read-only access to DynamoDB
  * D. Set ECS_ENABLE_TASK_IAM_ROLE to true on EC2 instance boot in the ECS agent configuration file. Grant the instance profile role read-only access to the Aurora database and DynamoDB
21) A developer has written an AWS Lambda function using Java as the runtime environment. The developer wants to isolate a performance bottleneck in the code.
Which steps should be taken to reveal the bottleneck?
  * A. Use the Amazon CloudWatch API to write timestamps to a custom CloudWatch metric. Use the CloudWatch console to analyze the resulting data.
  * B. Use the AWS X-Ray API to write trace data into X-Ray from strategic places within the code. Use the Amazon CloudWatch console to analyze the resulting data.
  * C. Use the AWS X-Ray API to write trace data into X-Ray from strategic places within the code. Use the X-Ray console to analyze the resulting data.
  * D. Use the Amazon CloudWatch API to write timestamps to a custom CloudWatch metric. Use the AWS X-Ray console to analyze the resulting data.
22)
23)
24)
25)
26)
27)
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
* [Answers]()
* Score:
