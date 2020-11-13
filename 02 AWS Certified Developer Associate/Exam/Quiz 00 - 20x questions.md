# Quiz 00 - 20x questions

## Questions
1. A developer is writing a component that will read customer orders from an Amazon SQS queue & process them. The developer wants to reduce empty response to the ReceiveMessage call & obtain a customer order message as soon as it is it available.<br/>What should the developer od when writing code to retireve messages fro the queue?
    * A. Use SQS Short Polling
    * B. Extend the visibility timeout
    * C. Use SQS Long Polling
    * D. Increase the maximum of messages to return
2. Each time a developer publishes a new version of an AWS Lambda function, all the dependent event source mappings need to be updated with the reference to the new version's ARN. These updates are time consuming & error-prone<br/>Which combination of actions should the developer take to avoind performing these updates when publishing a new Lambda version? (**Select TWO**)
    * A. Update event source mappings with ARN on the Lambda layer
    * B. Point a Lambda alias to a new version of the Lambda function
    * C. Create a Lambda alias for every published version of the Lambda function
    * D. Point the Lambda alias to a new Lambda function alias
    * E. Update the event source mappings with the Lambda alias ARN
3. A developer wants to monitor the execution of an AWS Lambda function using Amazon CloudWatch Logs. To accomplish this, the developer adds a number of print statements to the function code that write the logging information to the stdout stream. after executiong the function, the developer does not see any log data being generated, even after several minutes<br/>Why does the log data NOT appear in the CloudWatch Logs?
    * A. The log data is not written to the stderr stream
    * B. Lambda function loggin is not automatically enabled
    * C. The execution role for the Lambda function did not grant permissions to write log data to CloudWatch Logs
    * D. The Lambda function outputs the logs to an Amazon S3 bucket
4. A company is developing an image processing application. When an image is uploaded to an Amazon S3 bucket, a number of independent & separate services should be triggered to process the image. Each service must process every image, but may not be available to do so immediately<br/>Which application design satisfies these requirements?
    * A. Configure an S3 event notification that publishes to an Amazon SWS queue. Each service pulls the message from the same queue
    * B. Configure an S3 event notification that publishes to an Amazon SNS topic. Each service subscribes to the same topic.
    * C. Configure an S3 event notification that publishes to an Amazon SQS queue. Subscribe a separate Amazon SNS topic for each service to the SQS queue
    * D. Configure an S3 event notification that publishes to an Amazon SNS topic. Subscribe a separate Amazon SQS queue for each service to the SNS topic
5. A company wants to start using AWS log monitoring services to monitor an application that runs on premises. Currently, the application runs on an recent version of ubuntu Server & outputs the logs to a local file.<br/>Which steps should a developer perform to accoumplish this goal? (**Select TWO**)
    * A. Update the application code with calls to the agent API for log collection
    * B. Install the Amazon ECS container agent on the server
    * C. Install the Amazon CloudWatch agent on the server
    * D. Configure the logn-term AWS credentials on the server to enable log collection by the agent
    * E. Attach an IAM role to the server to neable log collection by the agent
6. A company is migrating a web service that accepts requests using HTTP (port 80) to the AWS Cloud. The company wants to use an AWS Lambda function to process HTTP requests.<br/>Which application design would satisfy these requirements?
    * A. Create an Amazon API Gateway API & configure proxy integration with the Lambda function
    * B. Create an Amazon API Gateway API & configure non-proxy integration with the Lambda function
    * C. Configure the Lambda function as a target in the ALB target group
    * D. Make the Lambda function listen to inbound network connections on port 80
7. An application running on Amazon EC2 instances needs credentials to make an API call to Amazon DynamoDB.<br/>What is the recommended secure way to provide credentials to perform the call?
    * A. Store AWS access key in the credentials file on the instance
    * B. Write AWS access keys into the environment variables in the user data script
    * C. Assign an IAM role with the correct permissions to the EC2 instance
    * D. Add the name of an IAM policy the correct permissions to the config file on the instance
8. A company is developing a Python application that submits data to an Amazon DynamoDB table. The company requires client-side encryption of specific data items & end-to-end protection for the encrypted data in transit & at rest<br/>Which combination of steps will meet the requirement for encryption of specific data items? (**Select TWO**)
    * A. Generate symmetric encryption keys with AWS KMS
    * B. Generate asymmetric encryption keys with AWS KMS
    * C. Use generated key with the DynamoDB Encryption Client
    * D. Use generated keys to configure DynamoDB table encryption using AWS-managed CMKs
    * E. Use generated keys to configure DynamoDB table encryption using AWS-owned customer CMKs
9. A developer plans to implement a mobile app to provide personalized services to the app users. The application code makes calls to Amazon S3 & Amazon SQS.<br/>Which options can the developer use to authenticate the app users? (**Select TWO**)
    * A. Authenticate to the Amazon Cognito identity pool directly
    * B. Authenticate to AWS IAM directly
    * C. Authenticate to the Amazon Cognito user pool directly
    * D. Federate authentication using Login with Amazon to AWS Security Token
    * E. Federate authentication using Login with Amazon to the Amazon Congito user pool
10. A developer uses AWS CodeDeploy to deploy a Python application to a fleet of Amazon EC2 instances running behind an ALB. The instances run in an EC2 ASG across multi-AZs.<br/>What should the developer include in the CodeDeploy deployment package?
    * A. A launch template for the EC2 ASG
    * B. An AWS CodeDeployAppSpec file
    * C. An EC2 role that grants the application access to AWS service
    * D. An IAM policy that grants the application access to AWS services
11. A developer wants to implement Amazon EC2 Auto Scaling for a web application, but is concerned that user sessions will be lost during scale-in events.<br/>How can the developer store the session state & share it across the EC2 instances?
    * A. Write the session to an Amazon Kinesis data stream. Configure the application to poll the stream
    * B. Publish the sessions to an Amazon SNS topic. Subscribe each instance in the group to the topic
    * C. Store the sessions in an Amazon ElastiCache for Memcached cluster. Configure the application to use the Memcached API
    * D. Write the sessions to an Amazon EBS volume. Mount the volume to each instance in the group
12. A developer has writen severall custom applications that read & write to the same Amazon DynamoDB table. Each time the data in the table is modified, the change needs to be sent to an external API.<br/>Which combiantion of steps will meet these requirements? (**Select TWO**)
    * A. Enable DynamoDB Streams on the table
    * B. Create a trigger in the DynamoDB table to publish the change to an Amazon Kiniesis data stream
    * C. Configure an AWS Lambda function to poll the stream & call the external API
    * D. Configure an event in Amazon EventBridge that publishes the change to an Amazon Managed Streaming for Apache Kafka (Amazon MSK) data stream
    * E. Deliver the stream to an Amazon SNS topic & subscribe the API to the topic
13. A company is developing a REST API  with Amazon API  Gateway. Access to the API should be limited to users in the existing Amazon Cognito user pool.<br/>Which combination of steps should be performed to secure the API? (**Select TWO**)
    * A. Create an AWS Lambda authorizer for the API
    * B. Create an Amazon Cognito authorizer for the API
    * C. Configure the authorizer for the API resource
    * D. Configure the authorizer on the API mehtods
    * E. Configure the authorizer for the API stage
14. A company is considering migrating the CRUD functionality of an existing Java web application to AWS Lambda.<br/>Which minimal code refactoring is necessary for the CRUD operations to be eecuted in the Lambda function?
    * A. Import an AWS X-Ray package
    * B. Rewrite the application ocde in Python
    * C. Implement a Lambda handler function
    * D. Add a reference to the Lambda execution role
15. A company needs to implement a number of order processing workflows. Each workflow is implemented using AWS Lambda functions for each task.<br/>Which combination of steps should the developer follow to implement these workflows? (**Select TWO**)
    * A. Define an AWS Step Function task for each Lambda function
    * B. Define an AWS Step Functions task for each workflow
    * C. Write code that pools the AWS Step Functions execution to coordinate each workflow
    * D. Define an AWS Step Functions state machine for each workflow
    * E. Define an AWS Step Function state machine for each Lambda function
16. A developer is integrating a legacy web application running on a fleet of Amazon EC2 instances with an Amazon DynamoDB table. The research shows there is currently no AWS SDK avaialble for the programming language the web application is implemented with<br/>Which combination of steps should the developer perform to make an API call to Amazon DynamoDB from the instances? (**Select TWO**)
    * A. Make an HTTPS POST request to the DynamoDB API endpoint for the Region. Include an XML document in the request body onctaining the request attributes
    * B. Make a HTTPS POST request to the DynamoDB API endpoint for the Region. Include a JSON document in the request body containing the request attributes
    * C. Sign the requests using AWS access keys & sigv4
    * D. Use an EC2 SSH key to calculate sigv4 of the request
    * E. Provide the singature value through the HTTP x-api-key header
17. A company plans to automate the build stage of its CI/CD pipeline. The company wants to specify the combination of the OS, the programming language runtime, & the tools used to run a build.<br/>What configuration option should a developer use to meet these requirements?
    * A. Specify an AMI i nthe appspec.yml file
    * B. Specify a Docker image in the buildspec.yml file
    * C. Specify an AMI in the uild environment
    * D. Specify a Docker image in the build environment 
18. A company wants to store sensitive user data in Amazon S3 & encrypt this data at rest. The company must manage the encryption keys themselves & use Amazon S3 to perform the encryption.<br/>How can a developer meet these requirements?
    * A. Enable default encryption for the S3 bucket using a customer-provided keys option
    * B. Provide a private encryption key when uploading an object to the S3 bucket
    * C. Provide a public encryption key when uploading an object to the S3bucket 
    * D. Provide a symmetric encryption key when uploading an object to the S3 bucket
19. A developer needs to prepare a deployment package for a Java implementation of an AWS Lambda function.<br/>What should go into the deployment package? (**Select TWO**)
    * A. Compiled application code
    * B. Java runtime environment
    * C. References to the event sources
    * D. Lambda execution role 
    * E. Application dependencies
20. A company noticies performance degradation in one of its production web application. The distributed application is built using a microservices architecture, & the company suspects that one of the microservices is causing the problem.<br/>Which tool should be used to identify the service that is contributing to higher application latency?
    * A. AWS X-Ray service map
    * B. AWS CloudTrail event history
    * C. Amazon CloudWatch Events
    * D. AWS Trusted Advisor performance report
* [MyAnswers]()
    * [Explication]()
* Score: 
