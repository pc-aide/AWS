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
22) A developer added a new feature to an application running on an Amazon EC2 instance that uses Amazon SQS. After deployment, the developer noticed a significant increase in Amazon SQS costs. When monitoring the Amazon SQS metrics on Amazon CloudWatch, the developer found that on average one message per minute is posted on this queue.
What can be done to reduce Amazon SQS costs for this application?
   * A.  Increase the Amazon SQS queue polling timeout.
   * B. Scale down the Amazon SQS queue to the appropriate size for low traffic demand.
   * C. Configure push delivery via Amazon SNS instead of polling the Amazon SQS queue.
   * D. Use an Amazon SQS first-in, first-out (FIFO) queue instead of a standard queue.
23) A developer is using Amazon DynamoDB to store application data. The developer wants to further improve application performance by reducing response times for read and write operations.
Which DynamoDB feature should be used to meet these requirements?
   * A. Amazon DynamoDB Streams
   * B. Amazon DynamoDB Accelerator
   * C. Amazon DynamoDB global tables
   * D. Amazon DynamoDB transactions
24) A developer is creating a script to automate the deployment process for a serverless application. The developer wants to use an existing AWS Serverless Application Model (AWS SAM) template for the application.
What should the developer use for the project? (**Choose two**.)
   * A. Call aws cloudformation package to create the deployment package. Call aws cloudformation deploy to deploy the package afterward.
   * B. Call sam package to create the deployment package. Call sam deploy to deploy the package afterward.
   * C. Call aws s3 cp to upload the AWS SAM template to Amazon S3. Call aws lambda update-function-code to create the application.
   * D. Create a ZIP package locally and call aws serverlessrepo create-application to create the application.
   * E. Create a ZIP package and upload it to Amazon S3. Call aws cloudformation create-stack to create the application.
25) A development team is designing a mobile app that requires multi-factor authentication.
Which steps should be taken to achieve this? (**Choose two**.)
   * A. Use Amazon Cognito to create a user pool and create users in the user pool.
   * B. Send multi-factor authentication text codes to users with the Amazon SNS Publish API call in the app code.
   * C. Enable multi-factor authentication for the Amazon Cognito user pool.
   * D. Use AWS IAM to create IAM users.
   * E. Enable multi-factor authentication for the users created in AWS IA
26) A gaming application stores scores for players in an Amazon DynamoDB table that has four attributes: user_id, user_name, user_score, and user_rank. The users are allowed to update their names only. A user is authenticated by web identity federation.
Which set of conditions should be added in the policy attached to the role for the dynamodb: PutItem API call?
    * A.   
````json
"Condition": {
  "ForAllValues:StringEquals": {
    "dynamodb:LeadingKeys": [
      "${www.amazon.com:user_id}"
    ],
    "dynamodb:Attributes": [
      "user_name"
    ]
  }
}
````
   * B. 
````json
"Condition": {
  "ForAllValues:StringEquals": {
    "dynamodb:LeadingKeys": [
      "${www.amazon.com:user_name}"
    ],
    "dynamodb:Attributes": [
      "user_id"
    ]
  }
}
````
  * C. 
````json
"Condition": {
  "ForAllValues:StringEquals": {
    "dynamodb:LeadingKeys": [
      "${www.amazon.com:user_id}"
    ],
    "dynamodb:Attributes": [
      "user_name", "user_ide"
    ]
  }
}
````
  * D.
````json
"condition": {
  "ForAllValues:StringEquals": {
    "dynamodb:LeadingKeys": [
      "${www.amazon.com:user_name}"
    ],
    "dynamodb:Attributes": [
      "user_name", "user_ide"
    ]
  }
}
````
27) A developer is using AWS CodeDeploy to deploy an application running on Amazon EC2. The developer wants to change the file permissions for a specific deployment file.
Which lifecycle event should a developer use to meet this requirement?
  * A. AfterInstall
  * B. DownloadBundle
  * C. BeforeInstall
  * D. ValidateService
28) Given the following AWS CloudFormation template:
````yaml
Description: Creates a new Amazon S3 bucket for shared content. use 
a random bucket name to avoid conflicts.
Resources:
  ContentBucket:
    Type: AWS::S3::Bucket
  Outputs:
    ContentBucketName:
      Value: !Ref ContentBucket
````
What is the MOST efficient way to reference the new Amazon S3 bucket from another AWS CloudFormation template?
  * A. Add an Export declaration to the Outputs section of the original template and use ImportValue in other templates.
  * B. Add Exported: true to the Contentbucket in the original template and use ImportResource in other templates.
  * C. Create a custom AWS CloudFormation resource that gets the bucket name from the ContentBucket resource of the first stack.
  * D. Use Fn::Include to include the existing template in other templates and use the ContentBucket resource directly.
29) A company is developing a report executed by AWS Step Functions. Amazon CloudWatch shows errors in the Step Functions task state machine. To troubleshoot each task, the state input needs to be included along with the error message in the state output.
Which coding practice can preserve both the original input and the error for the state?
  * A. Use ResultPath in a Catch statement to include the error with the original input.
  * B. Use InputPath in a Catch statement and set the value to null.
  * C. Use ErrorEquals in a Retry statement to include the error with the original input.
  * D. Use OutputPath in a Retry statement and set the value to $.
30) A developer receives the following error message when trying to launch or terminate an Amazon EC2 instance using a boto3 script.
````xml
boto.exception.BotoServerError:BotoServerError: 503 Service Unavailable
<?xml version="1.0" encoding="UTF-8"?>
<Response><Errors><Error><Code>RequestLimitExceeded</Code>
<Message>Request limit execeeded.</Message></Error></Errors>
<RequestID>bfddec84-53b3-4701-b728-dceefb696ced</RequestID
</Response>
````
What should the developer do to correct this error message?
  * A. Assign an IAM role to the EC2 instance to allow necessary API calls on behalf of the client.
  * B. Implement an exponential backoff algorithm for optimizing the number of API requests made to Amazon EC2.
  * C. Increase the overall network bandwidth to handle higher API request rates.
  * D. Upgrade to the latest AWS CLI version so that boto3 can handle higher request rates.
31) A developer is updating an application deployed on AWS Elastic Beanstalk. The new version is incompatible with the old version. To successfully deploy the update, a full cutover to the new, updated version must be performed on all instances at one time, with the ability to roll back changes in case of a deployment failure in the new version.
How can this be performed with the LEAST amount of downtime?
  * A. Use the Elastic Beanstalk All at once deployment policy to update all instances simultaneously.
  * B. Perform an Elastic Beanstalk Rolling with additional batch deployment.
  * C. Deploy the new version in a new Elastic Beanstalk environment and swap environment URLs.
  * D. Perform an Elastic Beanstalk Rolling deployment.
32) A developer is writing a web application that must share secure documents with end users. The documents are stored in a private Amazon S3 bucket. The application must allow only authenticated users to download specific documents when requested, and only for a duration of 15 minutes.
How can the developer meet these requirements?
  * A. Copy the documents to a separate S3 bucket that has a lifecycle policy for deletion after 15 minutes.
  * B. Create a presigned S3 URL using the AWS SDK with an expiration time of 15 minutes.
  * C. Use server-side encryption with AWS KMS managed keys (SSE-KMS) and download the documents using HTTP
  * D. Modify the S3 bucket policy to only allow specific users to download the documents. Revert the change after 15 minutes.
33) A developer wants to send multi-value headers to an AWS Lambda function that is registered as a target with an Application Load Balancer (ALB).
What should the developer do to achieve this?
  * A. Place the Lambda function and target group in the same account.
  * B. Send the request body to the Lambda function with a size less than 1 M
  * C. Include the Base64 encoding status, status code, status description, and headers in the Lambda function.
  * D. Enable the multi-value headers on the ALB
34) An ecommerce startup is preparing for an annual sales event. As the traffic to the company’s application increases, the development team wants to be notified when the Amazon EC2 instance’s CPU utilization exceeds 80%.
Which solution will meet this requirement?
  * A. Create a custom Amazon CloudWatch alarm that sends a notification to an Amazon SNS topic when the CPU utilization exceeds 80%.
  * B. Create a custom AWS Cloud Trail alarm that sends a notification to an Amazon SNS topic when the CPU utilization exceeds 80%.
  * C. Create a cron job on the EC2 instance that executes the --describe-instance-information command on the host instance every 15 minutes and sends the results to an Amazon SNS topic.
  * D. Create an AWS Lambda function that queries the AWS CloudTrail logs for the CPU Utilization metric every 15 minutes and sends a notification to an Amazon SNS topic when the CPU utilization exceeds 80%.
35) An application running on Amazon EC2 opens connections to an Amazon RDS SQL Server database. The developer does not want to store the user name and password for the database in the code. The developer would also like to automatically rotate the credentials.
What is the MOST secure way to store and access the database credentials?
  * A. Create an IAM role that has permissions to access the database. Attach the role to the EC2 instance.
  * B. Use AWS Secrets Manager to store the credentials. Retrieve the credentials from Secrets Manager as needed.
  * C. Store the credentials in an encrypted text file in an Amazon S3 bucket. Configure the EC2 instance’s user data to download the credentials from Amazon S3 as the instance boots.
  * D. Store the user name and password credentials directly in the source code. No further action is needed because the source code is stored in a private repository.
36) A global company has an application running on Amazon EC2 instances that serves image files from Amazon S3. User requests from the browser are causing high traffic, which results in degraded performance.
Which optimization solution should a developer implement to increase application performance?
   * A. Create multiple prefixes in the S3 bucket to increase the request rate.
   * B. Create an Amazon ElastiCache cluster to cache and serve frequently accessed items.
   * C. Use Amazon CloudFront to serve the content of images stored in Amazon S3.
   * D. Submit a ticket to AWS Support to request a rate limit increase for the S3 bucket.
37) An application needs to encrypt data that is written to Amazon S3 where the keys are managed in an on-premises data center, and the encryption is handled by S3.
Which type of encryption should be used?
   * A. Use server-side encryption with Amazon S3-managed keys
   * B. Use server-side encryption with AWS KMS-managed keys
   * C. Use client-side encryption with customer master keys
   * D. Use server-side encryption with customer-provided keys
38)  A development team is working on a mobile app that allows users to upload pictures to Amazon S3. The team expects the app will be used by hundreds of thousands of users during a single event simultaneously. Once the pictures are uploaded, the backend service will scan and parse the pictures for inappropriate content.
Which approach is the MOST resilient way to achieve this goal, which also smooths out temporary volume spikes for the backend service?
   * A. Develop an AWS Lambda function to check the upload folder in the S3 bucket. If new uploaded pictures are detected, the Lambda function will scan and parse them.
   * B. Once a picture is uploaded to Amazon S3, publish the event to an Amazon SQS queue. Use the queue as an event source to trigger an AWS Lambda function. In the Lambda function, scan and parse the picture.
   * C. When the user uploads a picture, invoke an API hosted in Amazon API Gateway. The API will invoke an AWS Lambda function to scan and parse the picture.
   * D. Create a state machine in AWS Step Functions to check the upload folder in the S3 bucket. If a new picture is detected, invoke an AWS Lambda function to scan and parse it.
39) A development team wants to run their container workloads on Amazon ECS. Each application container needs to share data with another container to collect logs and metrics.
What should the developer team do to meet these requirements?
   * A. Create two pod specifications. Make one to include the application container and the other to include the other container. Link the two pods together.
   * B. Create two task definitions. Make one to include the application container and the other to include the other container. Mount a shared volume between the two tasks.
   * C. Create one task definition. Specify both containers in the definition. Mount a shared volume between those two containers.
   * D. Create a single pod specification. Include both containers in the specification. Mount a persistent volume to both containers.
40)  A company has 25,000 employees and is growing. The company is creating an application that will be accessible to its employees only. A developer is using Amazon S3 to store images and Amazon RDS to store application data. The company requires that all employee information remain in the legacy Security Assertion Markup Language (SAML) employee directory only and is not interested in mirroring any employee information on AWS.
How can the developer provide authorized access for the employees who will be using this application so each employee can access their own application data only?
   * A. Use Amazon VPC and keep all resources inside the VPC, and use a VPC link for the S3 bucket with the bucket policy.
   * B. Use Amazon Cognito user pools, federate with the SAML provider, and use user pool groups with an IAM policy.
   * C. Use an Amazon Cognito identity pool, federate with the SAML provider, and use an IAM condition key with a value for the cognito-identity.amazonaws.com:sub variable to grant access to the employees.
   * D. Create a unique IAM role for each employee and have each employee assume the role to access the application so they can access their personal data only.
41) A company has developed a new serverless application using AWS Lambda functions that will be deployed using the AWS Serverless Application Model (AWS SAM) CLI.
Which step should the developer complete prior to deploying the application?
   * A. Compress the application to a .zip file and upload it into AWS Lambda
   * B. Test the new AWS Lambda function by first tracing it in AWS X-Ray
   * C. Bundle the serverless application using a SAM package
   * D. Create the application environment using the eb create my-env command
42) A company stores all personally identifiable information (PII) in an Amazon DynamoDB table named PII in Account A. An application running on Amazon EC2 instances in Account B requires access to the PII table. An administrator in Account A created an IAM role named AccessPII with privileges to access the PII table, and made Account B a trusted entity.
Which combination of additional steps should developers take to access the table? (**Choose two**.)
   * A. Ask an administrator in Account B to allow the EC2 IAM role permission to assume the AccessPII role.
   * B. Ask an administrator in Account B to allow the EC2 IAM role permission to assume the AccessPII role with predefined service control policies.
   * C. Ask an administrator in Account A to allow the EC2 IAM role permission to assume the AccessPII role with predefined service control policies.
   * D. Include the AssumeRole API in the application code logic to obtain credentials to access the PII table.
   * E. Include the GetSessionToken API in the application code logic to obtain credentials to access the PII table.
43)  A developer is creating an AWS Lambda function that generates a new file each time it runs. Each new file must be checked into an AWS CodeCommit repository hosted in the same AWS account.
How should the developer accomplish this?
   * A. When the Lambda function starts, use the Git CLI to clone the repository. Check the new file into the cloned repository and push the change.
   * B. After the new file is created in Lambda, use cURL to invoke the CodeCommit AP
   * C. Send the file to the repository.
   * D. Use an AWS SDK to instantiate a CodeCommit client. Invoke the put_file method to add the file to the repository.
   * E. Upload the new to an Amazon S3 bucket. Create an AWS Step Function to accept S3 events. In the Step Function, add the new file to the repository.
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
