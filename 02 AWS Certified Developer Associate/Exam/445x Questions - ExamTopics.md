# 445x Questions - ExamTopics

## URL
* https://www.examtopics.com/exams/amazon/aws-certified-developer-associate/view/

## Questions
1) A Developer created a dashboard for an application using Amazon API Gateway, Amazon S3, AWS Lambda, and Amazon RDS. The Developer needs an authentication mechanism allowing a user to sign in and view the dashboard. It must be accessible from mobile applications, desktops, and tablets, and must remember user preferences across platforms.
Which AWS service should the Developer use to support this authentication scenario?
    * A. AWS KMS
    * B. AWS Cognito
    * C. AWS Directoy Service
    * D. Amazon IAM 
* [Answer](https://i.imgur.com/201CZwe.png)
2) A Developer has created an S3 bucket s3://mycoolapp and has enabled server across logging that points to the folder s3://mycoolapp/logs. The
Developer moved 100 KB of CSS documents to the folder s3://mycoolapp/css, and then stopped work. When the developer came back a few days later, the bucket was 50 GB.
What is the MOST likely cause of this situation?
    * A. The CSS files were not compressed and S3 versioning was enabled. 
    * B. S3 replication was enabled on the bucket. 
    * C. Logging into the same bucket caused exponential log growth. 
    * D. An S3 lifecycle policy has moved the entire CSS file to S3 Infrequent Access. 
* [Answer](https://i.imgur.com/hrsWAqy.png) - error
3) A Developer is creating an Auto Scaling group whose instances need to publish a custom metric to Amazon CloudWatch.
Which method would be the MOST secure way to authenticate a CloudWatch PUT request?
    * A.  Create an IAM user with PutMetricData permission and put the user credentials in a private repository; have applications pull the credentials as needed. 
    * B. Create an IAM user with PutMetricData permission, and modify the Auto Scaling launch configuration to inject the user credentials into the instance user data. 
    * C. Modify the CloudWatch metric policies to allow the PutMetricData permission to instances from the Auto Scaling group.
    * D. Create an IAM role with PutMetricData permission and modify the Auto Scaling launching configuration to launch instances using that role. 
* [Answer](https://i.imgur.com/yfdaQAM.png)
4) A Developer is working on an application that tracks hundreds of millions of product reviews in an Amazon DynamoDB table. The records include the data elements shown in the table:

| Name       | Type   | Description                |
|------------|--------|----------------------------|
| reviewID   | Number | 16 digit UUID              |
| starRating | Number | Integer 1-5 of user rating |
| comment    | String | User comment string        |
| productID  | Number | Product ID being reviewed  |

Which field, when used as the partition key, would result in the MOST consistent performance using DynamoDB?
   * A. starRating
   * B. reviewID
   * C. comment
   * D. productID
* [Answer](https://i.imgur.com/qqIVocr.png)
5) A Developer has written a serverless application using multiple AWS services. The business logic is written as a Lambda function which has dependencies on third-party libraries. The Lambda function endpoints will be exposed using Amazon API Gateway. The Lambda function will write the information to Amazon
DynamoDB. The Developer is ready to deploy the application but must have the ability to rollback. How can this deployment be automated, based on these requirements?
    * A.  Deploy using Amazon Lambda API operations to create the Lambda function by providing a deployment package. 
    * B. Use an AWS CloudFormation template and use CloudFormation syntax to define the Lambda function resource in the template
    * C. Use syntax conforming to the Serverless Application Model in the AWS CloudFormation template to define the Lambda function resource.
    * D. Create a bash script which uses AWS CLI to package and deploy the application. 
* [Answer](https://i.imgur.com/PxphA0C.png) - error
6) What are the steps to using the AWS CLI to launch a templatized serverless application?
    * A.  Use AWS CloudFormation get-template then CloudFormation execute-change-set. 
    * B.  Use AWS CloudFormation validate-template then CloudFormation create-change-set. 
    * C. Use AWS CloudFormation package then CloudFormation deploy.
    * D. Use AWS CloudFormation create-stack then CloudFormation update-stack
* [Answer](https://i.imgur.com/OdGyzvM.png)
7) A Developer is creating a web application that requires authentication, but also needs to support guest access to provide users limited access without having to authenticate. What service can provide support for the application to allow guest access?
    * A. IAM temporary credentials using AWS STS.
    * B. Amazon Directory Service
    * C. Amazon Cognito with unauthenticated access enabled
    * D. IAM with SAML integration 
* [Answer](https://i.imgur.com/zSLW5g2.png) error
8) An application takes 40 seconds to process instructions received in an Amazon SQS message.
Assuming the SQS queue is configured with the default VisibilityTimeout value, what is the BEST way, upon receiving a message, to ensure that no other instances can retrieve a message that has already been processed or is currently being processed?
    * A. Use the ChangeMessageVisibility API to increase the VisibilityTimeout, then use the DeleteMessage API to delete the message.
    * B. Use the DeleteMessage API call to delete the message from the queue, then call DeleteQueue API to remove the queue.
    * C. Use the ChangeMessageVisibility API to decrease the timeout value, then use the DeleteMessage API to delete the message.
    * D. Use the DeleteMessageVisibility API to cancel the VisibilityTimeout, then use the DeleteMessage API to delete the message.
* [Answer](https://i.imgur.com/Gzp6SUi.png) 
9) A Developer has implemented a Lambda function that needs to add new customers to an RDS database that is expected to run hundreds of times per hour. The
Lambda function is configured to use 512MB of RAM and is based on the following pseudo code:
````python
def lambda_handler(event, context):

db = database.connect()
db.statement(`INSERT INTO Customer (CustomerName) VALUES
 (context.name)`)
 db.close
````
After testing the Lambda function, the Developer notices that the Lambda execution time is much longer than expected. What should the Developer do to improve performance?
    * A. Increase the amount of RAM allocated to the Lambda function, which will increase the number of threads the Lambda can use.
    * B. Increase the size of the RDS database to allow for an increased number of database connections each hour.
    * C. Move the database connection and close statement out of the handler. Place the connection in the global space.
    * D. Replace RDS wit Amazon DynamoDB to implement control over the number of writes per second.
* [Answer](https://i.imgur.com/IGFsdgf.png) error
10) A current architecture uses many Lambda functions invoking one another as a large state machine. The coordination of this state machine is legacy custom code that breaks easily.
Which AWS Service can help refactor and manage the state machine?
    * A. AWS Data Pipeline
    * B. AWS SNS with AWS SQS
    * C. Amazon Elastic MapReduce
    * D. AWS Step Functions 
* [Answer](https://i.imgur.com/0nmSYby.png)
11) A Developer is asked to implement a caching layer in front of Amazon RDS. Cached content is expensive to regenerate in case of service failure. Which implementation below would work while maintaining maximum uptime?
    * A. Implement Amazon ElastiCache Redis in Cluster Mode
    * B. Install Redis on an Amazon EC2 instance.
    * C. Implement Amazon ElastiCache Memcached.
    * D. Migrate the database to Amazon Redshift.
* [Answer](https://i.imgur.com/RetF06O.png)
12) A large e-commerce site is being designed to deliver static objects from Amazon S3. The Amazon S3 bucket will server more than 300 GET requests per second.
What should be done to optimize performance? (**Select TWO**.)
    * A. Integrate Amazon CloudFront with Amazon S3.
    * B. Enable Amazon S3 cross-region replication.
    * C. Delete expired Amazon S3 server log files.
    * D. Configure Amazon S3 lifecycle rules.
    * E. Randomize Amazon S3 key name prefixes.
* [Answer](https://i.imgur.com/UDVzjiu.png) error
13) A company is building a stock trading application that requires sub-millisecond latency in processing trading requests. Amazon DynamoDB is used to store all the trading data that is used to process each request. After load testing the application, the development team found that due to data retrieval times, the latency requirement is not satisfied. Because of sudden high spikes in the number of requests, DynamoDB read capacity has to be significantly over-provisioned to avoid throttling.
What steps should be taken to meet latency requirements and reduce the cost of running the application?
    * A. Add Global Secondary Indexes for trading data.
    * B. Store trading data in Amazon S3 and use Transfer Acceleration.
    * C. Add retries with exponential back-off for DynamoDB queries
    * D. Use DynamoDB Accelerator to cache trading data. 
* [Answer](https://i.imgur.com/PoYBIvZ.png) error
14) A Developer needs temporary access to resources in a second account.
What is the MOST secure way to achieve this?
    * A. Use the Amazon Cognito user pools to get short-lived credentials for the second account.
    * B. Create a dedicated IAM access key for the second account, and send it by mail.
    * C. Create a cross-account access role, and use sts:AssumeRole API to get short-lived credentials.
    * D. Establish trust, and add an SSH key for the second account to the IAM user.
* [Answer](https://i.imgur.com/x9NKhAX.png) 
15) An application reads data from an Amazon DynamoDB table. Several times a day, for a period of 15 seconds, the application receives multiple errors.
ProvisionedThroughputExceeded -
How should this exception be handled?
    * A. Create a new global secondary index for the table to help with the additional requests.
    * B. Retry the failed read requests with exponential backoff.
    * C. Immediately retry the failed read requests.
    * D. Use the DynamoDB "UpdateItem" API to increase the provisioned throughput capacity of the table.
* [Answer](https://i.imgur.com/KEXgdYV.png) error
16) A Developer has created a large Lambda function, and deployment is failing with the following error:
ClientError: An error occurred (InvalidParameterValueException) when calling the CreateFunction operation: Unzipped size must be smaller than XXXXXXXXX bytes', where XXXXXXXXX is the current Lambda limit
What can the Developer do to fix this problem?
    * A. Submit a limit increase request to AWS Support to increase the function to the size needed.
    * B. Use a compression algorithm that is more efficient than ZIP.
    * C. Break the function into multiple smaller Lambda functions.
    * D. ZIP the ZIP file twice to compress it further.
* [Answer](https://i.imgur.com/dollour.png) error
17) Given the source code for an AWS Lambda function in the local store.py containing a handler function called get_store and the following AWS
CloudFormation template:
````yaml
Transform: AWS::Serverless-2016-10-31
Resource:
  StoreFunc:
    Type: AWS::Serverless::Function
    Properties:
      Handler: store.get_store
      Runtime: python3.6
````
What should be done to prepare the template so that it can be deployed using the AWS CLI command aws cloudformation deploy?
    * A. Use aws cloudformation compile to base64 encode and embed the source file into a modified CloudFormation template.
    * B. Use aws cloudformation package to upload the source code to an Amazon S3 bucket and produce a modified CloudFormation template.
    * C. Use aws lambda zip to package the source file together with the CloudFormation template and deploy the resulting zip archive.
    * D. Use aws serverless create-package to embed the source file directly into the existing CloudFormation template.
* [Answer](https://i.imgur.com/W5rxPdE.png) error
18) An application stores images in an S3 bucket. Amazon S3 event notifications are used to trigger a Lambda function that resizes the images. Processing each image takes less than a second.
How will AWS Lambda handle the additional traffic?
    * A. Lambda will scale out to execute the requests concurrently.
    * B. Lambda will handle the requests sequentially in the order received.
    * C. Lambda will process multiple images in a single execution.
    * D. Lambda will add more compute to each execution to reduce processing time. 
* [Answer](https://i.imgur.com/ghbZtFc.png)
19) A company wants to implement a continuous integration for its workloads on AWS. The company wants to trigger unit test in its pipeline for commits-on its code repository, and wants to be notified of failure events in the pipeline.
How can these requirements be met?
    * A. Store the source code in AWS CodeCommit. Create a CodePipeline to automate unit testing. Use Amazon SNS to trigger notifications of failure events.
    * B. Store the source code in GitHub. Create a CodePipeline to automate unit testing. Use Amazon SES to trigger notifications of failure events.
    * C. Store the source code on GitHub. Create a CodePipeline to automate unit testing. Use Amazon CloudWatch to trigger notifications of failure events.
    * D. Store the source code in AWS CodeCommit. Create a CodePipeline to automate unit testing. Use Amazon CloudWatch to trigger notification of failure events.
* [Answer](https://i.imgur.com/NhQflCf.png)
20) A serverless application uses an API Gateway and AWS Lambda.
Where should the Lambda function store its session information across function calls?
    * A. In an Amazon DynamoDB table
    * B. In an Amazon SQS queue
    * C. In the local filesystem
    * D. In an SQLite session table using ""DSQLITE_ENABLE_SESSION 
* [Answer](https://i.imgur.com/qjki8Ch.png)
21) A Developer has created a software package to be deployed on multiple EC2 instances using IAM roles.
What actions could be performed to verify IAM access to get records from Amazon Kinesis Streams? (**Select TWO**.)
    * A. Use the AWS CLI to retrieve the IAM group.
    * B. Query Amazon EC2 metadata for in-line IAM policies.
    * C. Request a token from AWS STS, and perform a describe action.
    * D. Perform a get action using the ""-dry-run argument.
    * E. Validate the IAM role policy with the IAM policy simulator.
* [Answer](https://i.imgur.com/h6YKiip.png)
22) When writing a Lambda function, what is the benefit of instantiating AWS clients outside the scope of the handler?
    * A. Legibility and stylistic convention
    * B. Taking advantage of connection re-use
    * C. Better error handling
    * D. Creating a new instance per invocation
* [Answer](https://i.imgur.com/OZ7AjEl.png)
23) An application on AWS is using third-party APIs. The Developer needs to monitor API errors in the code, and wants to receive notifications if failures go above a set threshold value.
How can the Developer achieve these requirements?
    * A. Publish a custom metric on Amazon CloudWatch and use Amazon SES for notification.
    * B. Use an Amazon CloudWatch API-error metric and use Amazon SNS for notification.
    * C. Use an Amazon CloudWatch API-error metric and use Amazon SES for notification.
    * D. Publish a custom metric on Amazon CloudWatch and use Amazon SNS for notification.
* [Answer](https://i.imgur.com/xxLszxw.png) error
24) A Developer has an application that can upload tens of thousands of objects per second to Amazon S3 in parallel within a single AWS account. As part of new requirements, data stored in S3 must use server side encryption with AWS SSE-KMS. After creating this change, performance of the application is slower.
Which of the following is MOST likely the cause of the application latency?
    * A. Amazon S3 throttles the rate at which uploaded objects can be encrypted using Customer Master Keys.
    * B. The AWS KMS API calls limit is less than needed to achieve the desired performance.
    * C. The client encryption of the objects is using a poor algorithm.
    * D. KMS requires that an alias be used to create an independent display name that can be mapped to a CMK.
* [Answer](https://i.imgur.com/BKJWcBx.png) error
25) A company wants to migrate its web application to AWS and leverage Auto Scaling to handle pear workloads. The Solutions Architect determined that the best metric for an Auto Scaling event is the number of concurrent users.
Based on this information, what should the Developer use to autoscale based on concurrent users?
    * A. An Amazon SNS topic to be triggered when a concurrent user threshold is met
    * B. An Amazon Cloudwatch Networkin metric
    * C. Amazon CloudFront to leverage AWS Edge Locations
    * D. A Custom Amazon CloudWatch metric for concurrent users. 
* [Answer](https://i.imgur.com/QIUhvN9.png)
26) A company is migrating its on-premises database to Amazon RDS for MySQL. The company has read-heavy workloads, and wants to make sure it re-factors its code to achieve optimum read performance for its queries.
How can this objective be met?
    * A. Add database retries to effectively use RDS with vertical scaling
    * B. Use RDS with multi-AZ deployment
    * C. Add a connection string to use an RDS read replica for read queries
    * D. Add a connection string to use a read replica on an EC2 instance. 
* [Answer](https://i.imgur.com/jljGqJK.png)
27) A Developer is receiving HTTP 400: ThrottlingException errors intermittently when calling the Amazon CloudWatch API. When a call fails, no data is retrieved.
What best practice should first be applied to address this issue?
    * A. Contact AWS Support for a limit increase.
    * B. Use the AWS CLI to get the metrics
    * C. Analyze the applications and remove the API call
    * D. Retry the call with exponential backoff
* [Answer](https://i.imgur.com/QjneEzE.png) error
28) A Developer is testing a Docker-based application that uses the AWS SDK to interact with Amazon DynamoDB. In the local development environment, the application has used IAM access keys. The application is now ready for deployment onto an ECS cluster.
How should the application authenticate with AWS services in production?
    * A. Configure an ECS task IAM role for the application to use
    * B. Refactor the application to call AWS STS AssumeRole based on an instance role
    * C. Configure AWS access key/secret access key environment variables with new credentials
    * D. Configure the credentials file with a new access key/secret access key
* [Answer](https://i.imgur.com/ZSbhfR3.png)
29) A Developer created a Lambda function for a web application backend. When testing the Lambda function from the AWS Lambda console, the Developer can see that the function is being executed, but there is no log data being generated in Amazon CloudWatch Logs, even after several minutes.
What could cause this situation?
    * A. The Lambda function does not have any explicit log statements for the log data to send it to CloudWatch Logs.
    * B. The Lambda function is missing CloudWatch Logs as a source trigger to send log data.
    * C. The execution role for the Lambda function is missing permissions to write log data to the CloudWatch Logs.
    * D. The Lambda function is missing a target CloudWatch Log group.
* [Answer](https://i.imgur.com/g8I8zzl.png)
30) An application has hundreds of users. Each user may use multiple devices to access the application. The Developer wants to assign unique identifiers to these users regardless of the device they use.<br/>Which of the following methods should be used to obtain unique identifiers?
    * A. Create a user table in Amazon DynamoDB as key-value pairs of users and their devices. Use these keys as unique identifiers.
    * B. Use IAM-generated access key IDs for the users as the unique identifier, but do not store secret keys.
    * C. Implement developer-authenticated identities by using Amazon Cognito, and get credentials for these identities.
    * D. Assign IAM users and roles to the users. Use the unique IAM resource ID as the unique identifier.
* [Answer](https://i.imgur.com/7MrIXnK.png) error
31) An application is designed to use Amazon SQS to manage messages from many independent senders. Each sender's messages must be processed in the order they are received.<br/>Which SQS feature should be implemented by the Developer?
    * A. Configure each sender with a unique MessageGroupId
    * B. Enable MessageDeduplicationIds on the SQS queue
    * C. Configure each message with unique MessageGroupIds.
    * D. Enable ContentBasedDeduplication on the SQS queue
* [Answer](https://i.imgur.com/ITo0t5T.png) error
32) A deployment package uses the AWS CLI to copy files into any S3 bucket in the account, using access keys stored in environment variables. The package is running on EC2 instances, and the instances have been modified to run with an assumed IAM role and a more restrictive policy that allows access to only one bucket. After the change, the Developer logs into the host and still has the ability to write into all of the S3 buckets in that account.<br/>What is the MOST likely cause of this situation?
    * A. An IAM inline policy is being used on the IAM role
    * B. An IAM managed policy is being used on the IAM role
    * C. The AWS CLI is corrupt and needs to be reinstalled
    * D. The AWS credential provider looks for instance profile credentials last
* [Answer](https://i.imgur.com/Q4ZeUd3.png)
33) A Developer is writing transactions into a DynamoDB table called "SystemUpdates" that has 5 write capacity units.<br/>Which option has the highest read throughput?
    * A. Eventually consistent reads of 5 read capacity units reading items that are 4 KB in size
    * B. Strongly consistent reads of 5 read capacity units reading items that are 4 KB in size
    * C. Eventually consistent reads of 15 read capacity units reading items that are 1 KB in size
    * D. Strongly consistent reads of 15 read capacity units reading items that are 1 KB in size
* [Answer](https://i.imgur.com/vr2N0t3.png)
34) Where should an Elastic Beanstalk configuration file named healthcheckur1.config be placed in the application source bundle?
    * A. In the root of the application
    * B. In the bin folder
    * C. In healthcheckur1.config.ebextension under root
    * D. In the .ebextensions folder
* [Answer](https://i.imgur.com/vZrkBGn.png)
35) During non-peak hours, a Developer wants to minimize the execution time of a full Amazon DynamoDB table scan without affecting normal workloads. The workloads average half of the strongly consistent read capacity units during non-peak hours.<br/>How would the Developer optimize this scan?
    * A. Use parallel scans while limiting the rate
    * B. Use sequential scans
    * C. Increase read capacity units during the scan operation
    * D. Change consistency to eventually consistent during the scan operation 
* [Answer](https://i.imgur.com/SewYUsx.png)
36) A Developer is creating a Lambda function and will be using external libraries that are not included in the standard Lambda libraries.<br/>What action would minimize the Lambda compute time consumed?
    * A. Install the dependencies and external libraries at the beginning of the Lambda function.
    * B. Create a Lambda deployment package that includes the external libraries.
    * C. Copy the external libraries to Amazon S3, and reference the external libraries to the S3 location.
    * D. Install the external libraries in Lambda to be available to all Lambda functions.
* [Answer](https://i.imgur.com/qXxvvGI.png) error
37) A Developer is writing a Linux-based application to run on AWS Elastic Beanstalk. Application requirements state that the application must maintain full capacity during updates while minimizing cost.<br/>Which type of Elastic Beanstalk deployment policy should the Developer specify for the environment?
    * A. Immutable
    * B. Rolling
    * C. All at Once
    * D. Rolling with additional batch
* [Answer](https://i.imgur.com/hranJZP.png)
38) An application under development is required to store hundreds of video files. The data must be encrypted within the application prior to storage, with a unique key for each video file.<br/>How should the Developer code the application?
    * A. Use the KMS Encrypt API to encrypt the data. Store the encrypted data key and data.
    * B. Use a cryptography library to generate an encryption key for the application. Use the encryption key to encrypt the data. Store the encrypted data.
    * C. Use the KMS GenerateDataKey API to get a data key. Encrypt the data with the data key. Store the encrypted data key and data.
    * D. Upload the data to an S3 bucket using server side-encryption with an AWS KMS key.
* [Answer](https://i.imgur.com/D37MU8f.png) error
39) A Developer is creating an application that needs to locate the public IPv4 address of the Amazon EC2 instance on which it runs. How can the application locate this information?
    * A. Get the instance metadata by retrieving http://169.254.169.254/latest/metadata/.
    * B. Get the instance user data by retrieving http://169.254.169.254/latest/userdata/.
    * C. Get the application to run IFCONFIG to get the public IP address.
    * D. Get the application to run IPCONFIG to get the public IP address.
* [Answer](https://i.imgur.com/fh335E3.png)
40) The Lambda function below is being called through an API using Amazon API Gateway. The average execution time for the Lambda function is about 1 second.The pseudocode for the Lambda function is as shown in the exhibit.
````python
include "3rd party encryption module"
include "match module"
lambda_handler(event, context)
  rds_host = "rds-instance-endpoint"
  name = db_username
  password = db_password
  db_name = db_name
# Connect to the RDS Database
Conn = RDSConnection(rds_host, user=name, passwd=password,
db=db_name, connect_timeout=5)
#Perform some Processing reading data from the RDS database
#Code Block
#Code Block
#Code Block
````
What two actions can be taken to improve the performance of this Lambda function without increasing the cost of the solution? (**Select two**.)
   * A. Package only the modules the Lambda function requires
   * B. Use Amazon DynamoDB instead of Amazon RDS
   * C. Move the initialization of the variable Amazon RDS connection outside of the handler function
   * D. Implement custom database connection pooling with the Lambda function
   * E. Implement local caching of Amazon RDS data so Lambda can re-use the cache
* [Answer](https://i.imgur.com/QyyeuCI.png) error
41) An application will ingest data at a very high throughput from many sources and must store the data in an Amazon S3 bucket. Which service would BEST accomplish this task?
    * A. Amazon Kinesis Firehose
    * B. Amazon S3 Acceleration Transfer
    * C. Amazon SQS
    * D. Amazon SNS
* [Answer](https://i.imgur.com/lNAQog3.png) error
42) A Developer has setup an Amazon Kinesis Stream with 4 shards to ingest a maximum of 2500 records per second. A Lambda function has been configured to process these records.<br/>In which order will these records be processed?
    * A. Lambda will receive each record in the reverse order it was placed into the stream following a LIFO method
    * B. Lambda will receive each record in the exact order it was placed into the stream following a FIFO method.
    * C. Lambda will receive each record in the exact order it was placed into the shard following a FIFO method. There is no guarantee of order across shards.
    * D. The Developer can select FIFO, LIFO, random, or request specific record using the getRecords API.
* [Answer](https://i.imgur.com/EN0F9J7.png) error
43) A static website is hosted in an Amazon S3 bucket. Several HTML pages on the site use JavaScript to download images from another Amazon S3 bucket. These images are not displayed when users browse the site.<br/>What is the possible cause for the issue?
    * A. The referenced Amazon S3 bucket is in another region.
    * B. The images must be stored in the same Amazon S3 bucket.
    * C. Port 80 must be opened on the security group in which the Amazon S3 bucket is located.
    * D. Cross Origin Resource Sharing must be enabled on the Amazon S3 bucket.
* [Answer](https://i.imgur.com/tpXlQ9k.png)
44) Amazon S3 has the following structure: S3://BUCKET/FOLDERNAME/FILENAME.zip<br/>Which S3 best practice would optimize performance with thousands of PUT request each second to a single bucket?
    * A. Prefix folder names with user id; for example, s3://BUCKET/2013-FOLDERNAME/FILENAME.zip
    * B. Prefix file names with timestamps; for example, s3://BUCKET/FOLDERNAME/2013-26-05-15-00-00-FILENAME.zip
    * C. Prefix file names with random hex hashes; for example, s3://BUCKET/FOLDERNAME/23a6-FILENAME.zip
    * D. Prefix folder names with random hex hashes; for example, s3://BUCKET/23a6-FOLDERNAME/FILENAME.zip 
* [Answer](https://i.imgur.com/Cqpsl8P.png)
45) For a deployment using AWS CodeDeploy, what is the run order of the hooks for in-place deployments?
    * A. Before Install -> Application Stop -> Application Start -> After Install
    * B. Application Stop -> Before Install -> After Install -> Application Start
    * C. Before Install -> Application Stop -> Validate Service -> Application Start
    * D. Application Stop -> Before Install -> Validate Service -> Application Start
* [Answer](https://i.imgur.com/FwvvOBm.png) error
46) A Developer is developing an application that manages financial transactions. To improve security, MFA will be required as part of the login protocol.<br/>What services can the Developer use to meet these requirements?
    * A. Amazon DynamoDB to store MFA session data, and Amazon SNS to send MFA codes
    * B. Amazon Cognito with MFA
    * C. AWS Directory Service
    * D. AWS IAM with MFA enabled D
* [Answer](https://i.imgur.com/jSNF26R.png)
47) A game stores user game data in an Amazon DynamoDB table. Individual users should not have access to other users' game data. How can this be accomplished?
    * A. Encrypt the game data with individual user keys.
    * B. Restrict access to specific items based on certain primary key values.
    * C. Stage data in SQS queues to inject metadata before accessing DynamoDB.
    * D. Read records from DynamoDB and discard irrelevant data client-side.
* [Answer](https://i.imgur.com/uspe0UU.png) error
48) A company developed a set of APIs that are being served through the Amazon API Gateway. The API calls need to be authenticated based on OpenID identity providers such as Amazon or Facebook. The APIs should allow access based on a custom authorization model.<br/>Which is the simplest and MOST secure design to use to build an authentication and authorization model for the APIs?
    * A. Use Amazon Cognito user pools and a custom authorizer to authenticate and authorize users based on JSON Web Tokens.
    * B. Build a OpenID token broker with Amazon and Facebook. Users will authenticate with these identify providers and pass the JSON Web Token to the API to authenticate each API call.
    * C. Store user credentials in Amazon DynamoDB and have the application retrieve temporary credentials from AWS STS. Make API calls by passing user credentials to the APIs for authentication and authorization.
    * D. Use Amazon RDS to store user credentials and pass them to the APIs for authentications and authorization.
* [Answer](https://i.imgur.com/U2m6YMa.png)
49) A supplier is writing a new RESTful API for customers to query the status of orders. The customers requested the following API endpoint. http://www.supplierdomain.com/status/customerID<br/>Which of the following application designs meet the requirements? (**Select two**.)
    * A. Amazon SQS; Amazon SNS
    * B. Elastic Load Balancing; Amazon EC2
    * C. Amazon ElastiCache; Amazon Elacticsearch Service
    * D. Amazon API Gateway; AWS Lambda
    * E. Amazon S3; Amazon CloudFront
* [Answer](https://i.imgur.com/s1cksQS.png) error
50) A development team consists of 10 team members. Similar to a home directory for each team member the manager wants to grant access to user-specific folders in an Amazon S3 bucket. For the team member with the username "TeamMemberX", the snippet of the IAM policy looks like this:
````json
{"Sid": "AllowS3ActionToFolders","Effect": "Allow", "Action":
["s3:*"], "Resource":
["arn:aws:s3:::companyname/home/TeamMemberX/*] }
````
Instead of creating distinct policies for each team member, what approach can be used to make this policy snippet generic for all team members?
    * A. Use IAM policy condition
    * B. Use IAM policy principal
    * C. Use IAM policy variables
    * D. Use IAM policy resource
* [Answer](https://i.imgur.com/k2yTYqS.png)
51) A legacy service has an XML-based SOAP interface. The Developer wants to expose the functionality of the service to external clients with the Amazon API
Gateway. Which technique will accomplish this?
    * A. Create a RESTful API with the API Gateway; transform the incoming JSON into a valid XML message for the SOAP interface using mapping templates.
    * B. Create a RESTful API with the API Gateway; pass the incoming JSON to the SOAP interface through an Application Load Balancer.
    * C. Create a RESTful API with the API Gateway; pass the incoming XML to the SOAP interface through an Application Load Balancer.
    * D. Create a RESTful API with the API Gateway; transform the incoming XML into a valid message for the SOAP interface using mapping templates.
* [Answer](https://i.imgur.com/kJW68Kq.png) error
52) A company is using AWS CodeBuild to compile a website from source code stored in AWS CodeCommit. A recent change to the source code has resulted in the
CodeBuild project being unable to successfully compile the website.<br/>How should the Developer identify the cause of the failures?
    * A. Modify the buildspec.yml file to include steps to send the output of build commands to Amazon CloudWatch.
    * B. Use a custom Docker image that includes the AWS X-Ray agent in the AWS CodeBuild project configuration.
    * C. Check the build logs of the failed phase in the last build attempt in the AWS CodeBuild project build history.
    * D. Manually re-run the build process on a local machine so that the output can be visualized.
* [Answer](https://i.imgur.com/Ae0j4OL.png) error
53) A web application is using Amazon Kinesis Streams for clickstream data that may not be consumed for up to 12 hours.<br/>How can the Developer implement encryption at rest for data within the Kinesis Streams?
    * A. Enable SSL connections to Kinesis
    * B. Use Amazon Kinesis Consumer Library
    * C. Encrypt the data once it is at rest with a Lambda function
    * D. Enable server-side encryption in Kinesis Streams
* [Answer](https://i.imgur.com/6rPaCEo.png)
54) A Developer wants to use AWS X-Ray to trace a user request end-to-end throughput the software stack. The Developer made the necessary changes in the application tested it, and found that the application is able to send the traces to AWS X-Ray. However, when the application is deployed to an EC2 instance, the traces are not available.<br/>Which of the following could create this situation? (**Select two**.)
    * A. The traces are reaching X-Ray, but the Developer does not have access to view the records.
    * B. The X-Ray daemon is not installed on the EC2 instance.
    * C. The X-Ray endpoint specified in the application configuration is incorrect.
    * D. The instance role does not have "xray:BatchGetTraces" and "xray:GetTraceGraph" permissions.
    * E. The instance role does not have "xray:PutTraceSegments" and "xray:PutTelemetryRecords" permissions.
* [Answer](https://i.imgur.com/oJZUKWW.png)
55) A Developer executed a AWS CLI command and received the error shown below:
````text
A client error (UnauthorizedOperation) occured when calling the RunInstances operation:
Your are not authorized to perform this operation. Encoded authorization failure message:
fjsdoifhesoifgjsiadehfhworfwieojriewhjrhiri3hjrijweikrjkiewhtretkjjkhgfjjhfkjewrtjewjhreh
fhdsjhfsdjuhfuihuhuheufghsduhfu32yr3rhwherheufhejjhfdshfghdlghjghahgfhdugiernjgnrughreugh
fdjkshfjdhsjfhdshfjdshfiuwehfiuhwefhdsughfuysdgfhwejkrhuiwhefuidhsjfhdsjkhfdshfjjfhdsjfhj
````
What action should the Developer perform to make this error human-readable?
    * A. Make a call to AWS KMS to decode the message.
    * B. Use the AWS STS decode-authorization-message API to decode the message.
    * C. Use an open source decoding library to decode the message.
    * D. Use the AWS IAM decode-authorization-message API to decode this message.
* [Answer](https://i.imgur.com/mVcIH1c.png)
56) A company is using Amazon API Gateway to manage access to a set of microservices implemented as AWS Lambda functions. Following a bug report, the company makes a minor breaking change to one of the APIs.In order to avoid impacting existing clients when the new API is deployed, the company wants to allow clients six months to migrate from v1 to v2.<br/>Which approach should the Developer use to handle this change?
    * A. Update the underlying Lambda function and provide clients with the new Lambda invocation URL.
    * B. Use API Gateway to automatically propagate the change to clients, specifying 180 days in the phased deployment parameter.
    * C. Use API Gateway to deploy a new stage named v2 to the API and provide users with its URL.
    * D. Update the underlying Lambda function, create an Amazon CloudFront distribution with the updated Lambda function as its origin.
* [Answer](https://i.imgur.com/lEbALEX.png)
57) An application stops working with the following error: The specified bucket does not exist. Where is the BEST place to start the root cause analysis?
    * A. Check the Elastic Load Balancer logs for DeleteBucket requests.
    * B. Check the application logs in Amazon CloudWatch Logs for Amazon S3 DeleteBucket errors.
    * C. Check AWS X-Ray for Amazon S3 DeleteBucket alarms.
    * D. Check AWS CloudTrail for a DeleteBucket event.
* [Answer](https://i.imgur.com/dez2a94.png) error
58) An organization must store thousands of sensitive audio and video files in an Amazon S3 bucket. Organizational security policies require that all data written to this bucket be encrypted.<br/>How can compliance with this policy be ensured?
    * A. Use AWS Lambda to send notifications to the security team if unencrypted objects are pun in the bucket.
    * B. Configure an Amazon S3 bucket policy to prevent the upload of objects that do not contain the x-amz-server-side-encryption header.
    * C. Create an Amazon CloudWatch event rule to verify that all objects stored in the Amazon S3 bucket are encrypted.
    * D. Configure an Amazon S3 bucket policy to prevent the upload of objects that contain the x-amz-server-side-encryption header.
* [Answer](https://i.imgur.com/eAMqnIv.png)
59) An application overwrites an object in Amazon S3, and then immediately reads the same object. Why would the application sometimes retrieve the old version of the object?
    * A. S3 overwrite PUTS are eventually consistent, so the application may read the old object.
    * B. The application needs to add extra metadata to label the latest version when uploading to Amazon S3.
    * C. All S3 PUTS are eventually consistent, so the application may read the old object.
    * D. The application needs to explicitly specify latest version when retrieving the object.
* [Answer](https://i.imgur.com/nrX1M3A.png) error
60) The release process workflow of an application requires a manual approval before the code is deployed into the production environment.<br/>What is the BEST way to achieve this using AWS CodePipeline?
    * A. Use multiple pipelines to allow approval
    * B. Use an approval action in a stage
    * C. Disable the stage transition to allow manual approval
    * D. Disable a stage just prior the deployment stage
* [Answer](https://i.imgur.com/1k7fKhP.png) error
61) Where should the appspec.yml file be placed in order for AWS CodeDeploy to work?
    * A. In the root of the application source code directory structure
    * B. In the bin folder along with all the complied code
    * C. In an S3 bucket
    * D. In the same folder as the application configuration files
* [Answer](https://i.imgur.com/b4gWLKu.png)
62) An existing serverless application processes uploaded image files. The process currently uses a single Lambda function that takes an image file, performs the processing, and stores the file in Amazon S3. Users of the application now require thumbnail generation of the images. Users want to avoid any impact to the time it takes to perform the image uploads.<br/>How can thumbnail generation be added to the application, meeting user requirements while minimizing changes to existing code?
    * A. Change the existing Lambda function handling the uploads to create thumbnails at the time of upload. Have the function store both the image and thumbnail in Amazon S3.
    * B. Create a second Lambda function that handles thumbnail generation and storage. Change the existing Lambda function to invoke it asynchronously.
    * C. Create an S3 event notification with a Lambda function destination. Create a new Lambda function to generate and store thumbnails.
    * D. Create an S3 event notification to an SQS Queue. Create a scheduled Lambda function that processes the queue, and generates and stores thumbnails.
* [Answer](https://i.imgur.com/dJta7va.png)
63) A Developer must re-implement the business logic for an order fulfilment system. The business logic has to make requests to multiple vendors to decide where to purchase an item. The whole process can take up to a week to complete.<br/>What is the MOST efficient and SIMPLEST way to implement a system that meets these requirements?
    * A. Use AWS Step Functions to execute parallel Lambda functions, and join the results.
    * B. Create an AWS SQS for each vendor, poll the queue from a worker instance, and joint the results.
    * C. Use AWS Lambda to asynchronously call a Lambda function for each vendor, and join the results.
    * D. Use Amazon CloudWatch Events to orchestrate the Lambda functions.
* [Answer](https://i.imgur.com/O31NiYk.png) error
64) A customer wants to deploy its source code on an AWS Elastic Beanstalk environment. The customer needs to perform deployment with minimal outage and should only use existing instances to retain application access log.<br/>What deployment policy would satisfy these requirements?
    * A. Rolling
    * B. All at once
    * C. Rolling with an additional batch
    * D. Immutable
* [Answer](https://i.imgur.com/xRl4Kn3.png)
65) A Developer has been asked to build a real-time dashboard web application to visualize the key prefixes and storage size of objects in Amazon S3 buckets.
Amazon DynamoDB will be used to store the Amazon S3 metadata.<br/>What is the optimal and MOST cost-effective design to ensure that the real-time dashboard is kept up to date with the state of the objects in the Amazon S3 buckets?
    * A. Use an Amazon CloudWatch event backed by an AWS Lambda function. Issue an Amazon S3 API call to get a list of all Amazon S3 objects and persist the metadata within DynamoDB. Have the web application poll the DynamoDB table to reflect this change.
    * B. Use Amazon S3 Event Notification backed by a Lambda function to persist the metadata into DynamoDB. Have the web application poll the DynamoDB table to reflect this change.
    * C. Run a cron job within an Amazon EC2 instance to list all objects within Amazon S3 and persist the metadata into DynamoDB. Have the web application poll the DynamoDB table to reflect this change.
    * D. Create a new Amazon EMR cluster to get all the metadata about Amazon S3 objects; persist the metadata into DynamoDB. Have the web application poll the DynamoDB table to reflect this change. 
* [Answer](https://i.imgur.com/YaQKo62.png) error
66) A Developer must repeatedly and consistently deploy a serverless RESTful API on AWS.
Which techniques will work? (**Choose two**.)
    * A. Define a Swagger file. Use AWS Elastic Beanstalk to deploy the Swagger file.
    * B. Define a Swagger file. Use AWS CodeDeploy to deploy the Swagger file.
    * C. Deploy a SAM template with an inline Swagger definition.
    * D. Define a Swagger file. Deploy a SAM template that references the Swagger file.
    * E. Define an inline Swagger definition in a Lambda function. Invoke the Lambda function.
* [Answer](https://i.imgur.com/b1qkrBX.png) error
67) A set of APIs are exposed to customers using the Amazon API Gateway. These APIs have caching enabled on the API Gateway. Customers have asked for an option to invalidate this cache for each of the APIs.<br/>What action can be taken to allow API customers to invalidate the API Cache?
    * A. Ask customers to use AWS credentials to call the InvalidateCache API.
    * B. Ask customers to invoke an AWS API endpoint which invalidates the cache.
    * C. Ask customers to pass an HTTP header called Cache-Control:max-age=0.
    * D. Ask customers to add a query string parameter called "INVALIDATE_CACHE" when making an API call. 
* [Answer](https://i.imgur.com/2HDvnRb.png)
68) A Developer uses AWS CodeDeploy to automate application deployment that connects to an external MySQL database. The Developer wants to securely access the encrypted secrets, such as API keys and database passwords.<br/>Which of the following solutions would involve the LEAST administrative effort?
    * A. Save the secrets in Amazon S3 with AWS KMS server-side encryption, and use a signed URL to access them by using the IAM role from Amazon EC2 instances.
    * B. Use the instance metadata to store the secrets and to programmatically access the secrets from EC2 instances.
    * C. Use the Amazon DynamoDB client-side encryption library to save the secrets in DynamoDB and to programmatically access the secrets from EC2 instances.
    * D. Use AWS SSM Parameter Store to store the secrets and to programmatically access them by using the IAM role from EC2 instances.
* [Answer](https://i.imgur.com/jsLPAHm.png)
69) An application running on EC2 instances is storing data in an S3 bucket. Security policy mandates that all data must be encrypted in transit.<br/>How can the Developer ensure that all traffic to the S3 bucket is encrypted?
    * A. Install certificates on the EC2 instances.
    * B. Create a bucket policy that allows traffic where SecureTransport is true.
    * C. Create an HTTPS redirect on the EC2 instances.
    * D. Create a bucket policy that denies traffic where SecureTransport is false.
* [Answer](https://i.imgur.com/55vNddf.png) error
70) A company is developing a new online game that will run on top of Amazon ECS. Four distinct Amazon ECS services will be part of the architecture, each requiring specific permissions to various AWS services. The company wants to optimize the use of the underlying Amazon EC2 instances by bin packing the containers based on memory reservation.<br/>Which configuration would allow the Development team to meet these requirements MOST securely?
    * A. Create a new Identity and Access Management (IAM) instance profile containing the required permissions for the various ECS services, then associate that instance role with the underlying EC2 instances.
    * B. Create four distinct IAM roles, each containing the required permissions for the associated ECS service, then configure each ECS service to reference the associated IAM role.
    * C. Create four distinct IAM roles, each containing the required permissions for the associated ECS service, then, create an IAM group and configure the ECS cluster to reference that group.
    * D. Create four distinct IAM roles, each containing the required permissions for the associated ECS service, then configure each ECS task definition to referenne the associated IAM role.
* [Answer](https://i.imgur.com/c7sl6E4.png) error
71) A company needs to encrypt data at rest, but it wants to leverage an AWS managed service using its own master key.<br/>Which of the following AWS service can be used to meet these requirements?
    * A. SSE with Amazon S3
    * B. SSE with AWS KMS
    * C. Client-side encryption
    * D. AWS IAM roles and policies
* [Answer](https://i.imgur.com/rTj3EPg.png)
72) When a Developer tries to run an AWS CodeBuild project, it raises an error because the length of all environment variables exceeds the limit for the combined maximum of characters.<br/>What is the recommended solution?
    * A. Add the export LC_ALL="en_US.utf8" command to the pre_build section to ensure POSIX localization.
    * B. Use Amazon Cognito to store key-value pairs for large numbers of environment variables.
    * C. Update the settings for the build project to use an Amazon S3 bucket for large numbers of environment variables.
    * D. Use AWS Systems Manager Parameter Store to store large numbers of environment variables.
* [Answer](https://i.imgur.com/eRZJEH4.png) error
73) A Lambda function is packaged for deployment to multiple environments, including development, test, production, etc. Each environment has unique set of resources such as databases, etc.<br/>How can the Lambda function use the resources for the current environment?
    * A. Apply tags to the Lambda functions.
    * B. Hardcore resources in the source code.
    * C. Use environment variables for the Lambda functions.
    * D. Use separate function for development and production.
* [Answer](https://i.imgur.com/j6JftMB.png)
74) The Developer for a retail company must integrate a fraud detection solution into the order processing solution. The fraud detection solution takes between ten and thirty minutes to verify an order. At peak, the web site can receive one hundred orders per minute.<br/>What is the most scalable method to add the fraud detection solution to the order processing pipeline?
    * A. Add all new orders to an Amazon SQS queue. Configure a fleet of 10 EC2 instances spanning multiple AZs with the fraud detection solution installed on them to pull orders from this queue. Update the order with a pass or fails status.
    * B. Add all new orders to an SQS queue. Configure an Auto Scaling group that uses the queue depth metric as its unit of scale to launch a dynamically-sized fleet of EC2 instances spanning multiple AZs with the fraud detection solution installed on them to pull orders from this queue. Update the order with a pass or fails status.
    * C. Add all new orders to an Amazon Kinesis Stream. Subscribe a Lambda function to automatically read batches of records from the Kinesis Stream. The Lambda function includes the fraud detection software and will update the order with a pass or fail status.
    * D. Write all new orders to Amazon DynamoDB. Configure DynamoDB Streams to include all new orders. Subscribe a Lambda function to automatically read batches of records from the Kinesis Stream. The Lambda function includes the fraud detection software and will update the order with a pass or fail status.
* [Answer](https://i.imgur.com/6w1kULC.png)
75) A Developer is creating a mobile application with a limited budget. The solution requires a scalable service that will enable customers to sign up and authenticate into the mobile application while using the organization's current SAML 2.0 identity provider.<br/>Which AWS service should be used to meet these requirements?
    * A. AWS Lambda
    * B. Amazon Cognito
    * C. AWS IAM
    * D. Amazon EC2
* [Answer](https://i.imgur.com/8DzXRXW.png)
76) An application is real-time processing millions of events that are received through an API.<br/>What service could be used to allow multiple consumers to process the data concurrently and MOST cost-effectively?
    A. Amazon SNS with fanout to an SQS queue for each application
    B. Amazon SNS with fanout to an SQS FIFO queue for each application
    C. Amazon Kinesis Firehouse
    D. Amazon Kinesis Streams
* [Answer](https://i.imgur.com/wlYmnrN.png)
77) A Developer needs to use AWS X-Ray to monitor an application that is deployed on EC2 instances.<br/>What steps have to be executed to perform the monitoring?
    * A. Deploy the X-Ray SDK with the application and use X-Ray annotation.
    * B. Install the X-Ray daemon and instrument the application code.
    * C. Install the X-Ray daemon and configure it to forward data to Amazon CloudWatch Events.
    * D. Deploy the X-Ray SDK with the application and instrument the application code.
* [Answer](https://i.imgur.com/CA4wWxw.png) error
78) A Developer will be using the AWS CLI on a local development server to manage AWS services.<br/>What can be done to ensure that the CLI uses the Developer's IAM permissions when making commands?
    * A. Specify the Developer's IAM access key ID and secret access key as parameters for each CLI command.
    * B. Run the aws configure CLI command, and provide the Developer's IAM access key ID and secret access key.
    * C. Specify the Developer's IAM user name and password as parameters for each CLI command.
    * D. Use the Developer's IAM role when making the CLI command. 
* [Answer](https://i.imgur.com/mqTUDCt.png)
79) After installing the AWS CLI, a Developer tries to run the command aws configure but receives the following error:<br/>Error: aws: command not found -
What is the most likely cause of this error?
    * A. The aws executable is not in the PATH environment variable.
    * B. Access to the aws executable has been denied to the installer.
    * C. Incorrect AWS credentials were provided.
    * D. The aws script does not have an executable file mode.
* [Answer](https://i.imgur.com/DwADNYD.png) error
80) An on-premises legacy application is caching data files locally and writing shared images to local disks.<br/>What is necessary to allow for horizontal scaling when migrating the application to AWS?
    * A. Modify the application to have both shared images and caching data written to Amazon EBS.
    * B. Modify the application to read and write cache data on Amazon S3, and also store shared images on S3.
    * C. Modify the application to use Amazon S3 for serving shared images; cache data can then be written to local disks.
    * D. Modify the application to read and write cache data on Amazon S3, while continuing to write shared images to local disks.
* [Answer](https://i.imgur.com/fsVhl5f.png) error
81) A Developer must trigger an AWS Lambda function based on the item lifecycle activity in an Amazon DynamoDB table.<br/>How can the Developer create the solution?
    * A. Enable a DynamoDB stream that publishes an Amazon SNS message. Trigger the Lambda function synchronously from the SNS message.
    * B. Enable a DynamoDB stream that publishes an SNS message. Trigger the Lambda function asynchronously from the SNS message.
    * C. Enable a DynamoDB stream, and trigger the Lambda function synchronously from the stream.
    * D. Enable a DynamoDB stream, and trigger the Lambda function asynchronously from the stream.
* [Answer](https://i.imgur.com/ZjQ4dHl.png) error
82) A gaming company is developing a mobile game application for iOS and Android platforms. This mobile game securely stores user data locally on the device.
The company wants to allow users to use multiple device for the game, which requires user data synchronization across device.<br/>Which service should be used to synchronize user data across devices without the need to create a backend application?
    * A. AWS Lambda
    * B. Amazon S3
    * C. Amazon DynamoDB
    * D. Amazon Cognito
* [Answer](https://i.imgur.com/02r7lDk.png)
83) An on-premises application is implemented using a Linux, Apache, MySQL and PHP (LAMP) stack. The Developer wants to run this application in AWS.<br/>Which of the following sets of AWS services can be used to run this stack?
    * A. Amazon API Gateway, Amazon S3
    * B. AWS Lambda, Amazon DynamoDB
    * C. Amazon EC2, Amazon Aurora
    * D. Amazon Cognito, Amazon RDS
    * E. Amazon ECS, Amazon EBS
* [Answer](https://i.imgur.com/DMlO0sF.png) error
84) An application displays a status dashboard. The status is updated by 1 KB messages from an SQS queue. Although the status changes infrequently, the
Developer must minimize the time between the message arrival in the queue and the dashboard update.<br/>What technique provides the shortest delay in updating the dashboard?
    * A. Retrieve the messages from the queue using long polling every 20 seconds.
    * B. Reduce the size of the messages by compressing them before sending.
    * C. Retrieve the messages from the queue using short polling every 10 seconds.
    * D. Reduce the size of each message payload by sending it in two parts. 
* [Answer](https://i.imgur.com/vIMz0BH.png)
85) A company is using AWS CodePipeline to deliver one of its applications. The delivery pipeline is triggered by changes to the master branch of an AWS
CodeCommit repository and uses AWS CodeBuild to implement the test and build stages of the process and AWS CodeDeploy to deploy the application.
The pipeline has been operating successfully for several months and there have been no modifications. Following a recent change to the application's source code, AWS CodeDeploy has not deployed the updates application as expected.<br/>What are the possible causes? (**Choose two**.)
    * A. The change was not made in the master branch of the AWS CodeCommit repository.
    * B. One of the earlier stages in the pipeline failed and the pipeline has terminated.
    * C. One of the Amazon EC2 instances in the company's AWS CodePipeline cluster is inactive.
    * D. The AWS CodePipeline is incorrectly configured and is not executing AWS CodeDeploy.
    * E. AWS CodePipeline does not have permissions to access AWS CodeCommit.
* [Answer](https://i.imgur.com/oiLkJtY.png)
86) A social media company is using Amazon Cognito in order to synchronize profiles across different mobile devices, to enable end users to have a seamless experience.<br/>Which of the following configurations can be used to silently notify users whenever an update is available on all other devices?
    * A. Modify the user pool to include all the devices which keep them in sync.
    * B. Use the SyncCallback interface to receive notifications on the application.
    * C. Use an Amazon Cognito stream to analyze the data and push the notifications.
    * D. Use the push synchronization feature with the appropriate IAM role.
* [Answer](https://i.ibb.co/pZ6Wwtz/image.png) error
87) A website's page load times are gradually increasing as more users access the system at the same time. Analysis indicates that a user profile is being loaded from a database in all the web pages being visited by each user and this is increasing the database load and the page load latency. To address this issue the
Developer decides to cache the user profile data.<br/>Which caching strategy will address this situation MOST efficiently?
    * A. Create a new Amazon EC2 Instance and run a NoSQL database on it. Cache the profile data within this database using the write-through caching strategy.
    * B. Create an Amazon ElastiCache cluster to cache the user profile data. Use a cache-aside caching strategy.
    * C. Use a dedicated Amazon RDS instance for caching profile data. Use a write-through caching strategy.
    * D. Create an ElastiCache cluster to cache the user profile data. Use a write-through caching strategy.
* [Answer](https://i.ibb.co/JCXnDGz/image.png)
88) An application needs to use the IP address of the client in its processing. The application has been moved into AWS and has been placed behind an ALB. However, all the client IP addresses now appear to be the same. The application must maintain the ability to scale horizontally.<br/>Based on this scenario, what is the MOST cost-effective solution to this problem?
    * A. Remove the application from the ALB. Delete the ALB and change Amazon Route 53 to direct traffic to the instance running the application.
    * B. Remove the application from the ALB. Create a Classic Load Balancer in its place. Direct traffic to the application using the HTTP protocol.
    * C. Alter the application code to inspect the X-Forwarded-For header. Ensure that the code can work properly if a list of IP addresses is passed in the header.
    * D. Alter the application code to inspect a custom header. Alter the client code to pass the IP address in the custom header.
* [Answer](https://i.ibb.co/PMXHmPg/image.png)
89) A development team is using AWS Elastic Beanstalk to deploy a two-tier application that consists of a load-balanced web tier and an Amazon RDS database tier in production. The team would like to separate the RDS instance from the Elastic Beanstalk.<br/>How can this be accomplished?
    * A. Use the Elastic Beanstalk CLI to disassociate the database.
    * B. Use the AWS CLI to disassociate the database.
    * C. Change the deployment policy to disassociate the database.
    * D. Recreate a new Elastic Beanstalk environment without Amazon RDS. 
* [Answer](https://i.ibb.co/NjQ3Vhz/image.png)
90) According to best practice, how should access keys be managed in AWS? (Choose two.)
    * A. Use the same access key in all applications for consistency.
    * B. Delete all access keys for the account root user.
    * C. Leave unused access keys in the account for tracking purposes.
    * D. Embed and encrypt access keys in code for continuous deployment.
    * E. Use Amazon IAM roles instead of access keys where possible.
* [Answer](https://i.ibb.co/dfg3Hnx/image.png)
91) The development team is working on an API that will be served from Amazon API gateway. The API will be served from three environments: development, test, and production. The API Gateway is configured to use 237 GB of cache in all three stages.<br/>Which is the MOST cost-efficient deployment strategy?
    * A. Create a single API Gateway with all three stages.
    * B. Create three API Gateways, one for each stage in a single AWS account.
    * C. Create an API Gateway in three separate AWS accounts.
    * D. Enable the cache for development and test environments only when needed.
* [Answer](https://i.ibb.co/VV19TrX/image.png)
92) An application running on an Amazon Linux EC2 instance needs to manage the AWS infrastructure.<br/>How can the EC2 instance be configured to make AWS API calls securely?
    * A. Sign the AWS CLI command using the signature version 4 process.
    * B. Run the aws configure AWS CLI command and specify the access key id and secret access key.
    * C. Specify a role for the EC2 instance with the necessary privileges.
    * D. Pass the access key id and secret access key as parameters for each AWS CLI command.
* [Answer](https://i.ibb.co/B2Xmpvy/image.png)
93) A company is migrating from a monolithic architecture to a microservices-based architecture. The Developers need to refactor the application so that the many microservices can asynchronously communicate with each other without impacting performance.<br/>Use of which managed AWS services will enable asynchronous message passing? (**Choose two**.)
    * A. Amazon SQS
    * B. Amazon Cognito
    * C. Amazon Kinesis
    * D. Amazon SNS
    * E. Amazon ElastiCache
* [Answer](https://i.ibb.co/nLT4cdf/image.png)
94) An application runs on multiple EC2 instances behind an ELB.<br/>Where is the session data best written so that it can be served reliably across multiple requests?
    * A. Write data to Amazon ElastiCache
    * B. Write data to Amazon Elastic Block Store.
    * C. Write data to Amazon EC2 Instance Store.
    * D. Write data to the root filesystem.
* [Answer](https://i.ibb.co/fpS4vCK/image.png)
95) A Developer is creating a Lambda function that will generate and export a file. The function requires 100 MB of temporary storage for temporary files while executing. These files will not be needed after the function is complete.<br/>How can the Developer MOST efficiently handle the temporary files?
    * A. Store the files in EBS and delete the files at the end of the Lambda function.
    * B. Copy the files to EFS and delete the files at the end of the Lambda function.
    * C. Store the files in the /tmp directory and delete the files at the end of the Lambda function.
    * D. Copy the files to an S3 bucket with a lifecycle policy to delete the files.
* [Answer](https://i.ibb.co/CQ3MtVf/image.png)
96) A Developer has developed a web application and wants to deploy it quickly on a Tomcat server on AWS. The Developer wants to avoid having to manage the underlying infrastructure.<br/>What is the easiest way to deploy the application, based on these requirements?
    * A. AWS CloudFormation
    * B. AWS Elastic Beanstalk
    * C. Amazon S3
    * D. AWS CodePipeline
* [Answer](https://i.ibb.co/C8Ybsrq/image.png)
97) An application uses Lambda functions to extract metadata from files uploaded to an S3 bucket; the metadata is stored in Amazon DynamoDB. The application starts behaving unexpectedly, and the Developer wants to examine the logs of the Lambda function code for errors.<br/>Based on this system configuration, where would the Developer find the logs?
    * A. Amazon S3
    * B. AWS CloudTrail
    * C. Amazon CloudWatch
    * D. Amazon DynamoDB
* [Answer](https://i.ibb.co/wr4mnTQ/image.png)
98) An organization is using Amazon CloudFront to ensure that its users experience low-latency access to its web application. The organization has identified a need to encrypt all traffic between users and CloudFront, and all traffic between CloudFront and the web application.<br/>How can these requirements be met? (**Choose two**.)
    * A. Use AWS KMS to encrypt traffic between CloudFront and the web application.
    * B. Set the Origin Protocol Policy to "HTTPS Only".
    * C. Set the Origin's HTTP Port to 443.
    * D. Set the Viewer Protocol Policy to "HTTPS Only" or "Redirect HTTP to HTTPS".
    * E. Enable the CloudFront option Restrict Viewer Access.
* [Answer](https://i.ibb.co/w4ynzjy/image.png) error
99) An application is using Amazon DynamoDB as its data store, and should be able to read 100 items per second as strongly consistent reads. Each item is 5 KB in size.<br/>To what value should the table's provisioned read throughput be set?
    * A. 50 read capacity units
    * B. 100 read capacity units
    * C. 200 read capacity units
    * D. 500 read capacity units 
* [Answer](https://i.ibb.co/vzBbVDc/image.png)
100) A web application is designed to allow new users to create accounts using their email addresses. The application will store attributes for each user, and is expecting millions of user to sign up.What should the Developer implement to achieve the design goals?
   * A. Amazon Cognito user pools
   * B. AWS Mobile Hub user data storage
   * C. Amazon Cognito Sync
   * D. AWS Mobile Hub cloud logic
* [Answer](https://i.ibb.co/0tw5kmh/image.png)
101) A company needs a new REST API that can return information about the contents of an Amazon S3 bucket, such as a count of the objects stored in it. The company has decided that the new API should be written as a microservice using AWS Lambda and Amazon API Gateway.How should the Developer ensure that the microservice has the necessary access to the Amazon S3 bucket, while adhering to security best practices?
   * A. Create an IAM user that has permissions to access the Amazon S3 bucket, and store the IAM user credentials in the Lambda function source code.
   * B. Create an IAM role that has permissions to access the Amazon S3 bucket and assign it to the Lambda function as its execution role.
   * C. Create an Amazon S3 bucket policy that specifies the Lambda service as its principal and assign it to the Amazon S3 bucket.
   * D. Create an IAM role, attach the AmazonS3FullAccess managed policy to it, and assign the role to the Lambda function as its execution role.
* [Answer](https://i.ibb.co/GTZ0mKh/image.png) error
102) An application is running on an EC2 instance. The Developer wants to store an application metric in Amazon CloudWatch.What is the best practice for implementing this requirement?
   * A. Use the PUT Object API call to send data to an S3 bucket. Use an event notification to invoke a Lambda function to publish data to CloudWatch.
   * B. Publish the metric data to an Amazon Kinesis Stream using a PutRecord API call. Subscribe a Lambda function that publishes data to CloudWatch.
   * C. Use the CloudWatch PutMetricData API call to submit a custom metric to CloudWatch. Provide the required credentials to enable the API call.
   * D. Use the CloudWatch PutMetricData API call to submit a custom metric to CloudWatch. Launch the EC2 instance with the required IAM role to enable the API call.
* [Answer](https://i.ibb.co/gzhZjgs/image.png)
103) Queries to an Amazon DynamoDB table are consuming a large amount of read capacity. The table has a significant number of large attributes. The application does not need all of the attribute data.<br/>How can DynamoDB costs be minimized while maximizing application performance?
   * A. Batch all the writes, and perform the write operations when no or few reads are being performed.
   * B. Create a global secondary index with a minimum set of projected attributes.
   * C. Implement exponential backoffs in the application.
   * D. Load balance the reads to the table using an Application Load Balancer.
* [Answer](https://i.ibb.co/LNYfrgH/image.png)
104) AWS CodeBuild builds code for an application, creates the Docker image, pushes the image to Amazon Elastic Container Registry (Amazon ECR), and tags the image with a unique identifier.<br/>If the Developers already have AWS CLI configured on their workstations, how can the Docker images be pulled to the workstations?
   * A. Run the following: docker pull REPOSITORY URI : TAG
   * B. Run the output of the following: aws ecr get-login and then run: docker pull REPOSITORY URI : TAG
   * C. Run the following: aws ecr get-login and then run: docker pull REPOSITORY URI : TAG
   * D. Run the output of the following: aws ecr get-download-url-for-layer and then run: docker pull REPOSITORY URI : TAG
* [Answer](https://i.ibb.co/LNqFk9T/image.png) error
105) A company caches session information for a web application in an Amazon DynamoDB table. The company wants an automated way to delete old items from the table.<br/>What is the simplest way to do this?
   * A. Write a script that deletes old records; schedule the scripts as a cron job on an Amazon EC2 instance.
   * B. Add an attribute with the expiration time; enable the Time To Live feature based on that attribute.
   * C. Each day, create a new table to hold session data; delete the previous day's table.
   * D. Add an attribute with the expiration time; name the attribute ItemExpiration.
* [Answer](https://i.ibb.co/8zxCH0T/image.png)
106) An application is expected to process many files. Each file takes four minutes to process each AWS Lambda invocation. The Lambda function does not return any important data.<br/>What is the fastest way to process all the files?
   * A. First split the files to make them smaller, then process with synchronous RequestResponse Lambda invocations.
   * B. Make synchronous RequestResponse Lambda invocations and process the files one by one.
   * C. Make asynchronous Event Lambda invocations and process the files in parallel.
   * D. First join all the files, then process it all at once with an asynchronous Event Lambda invocation.
* [Answer](https://i.imgur.com/RnaxYxh.png)
107) The upload of a 15 GB object to Amazon S3 fails. The error message reads: "Your proposed upload exceeds the maximum allowed object size."<br/>What technique will allow the Developer to upload this object?
   * A. Upload the object using the multi-part upload API.
   * B. Upload the object over an AWS Direct Connect connection.
   * C. Contact AWS Support to increase the object size limit.
   * D. Upload the object to another AWS region.
* [Answer](https://i.imgur.com/cBsOJfy.png)
108) A company has an AWS CloudFormation template that is stored as a single file. The template is able to launch and create a full infrastructure stack.<br/>Which best practice would increase the maintainability of the template?
   * A. Use nested stacks for common template patterns.
   * B. Embed credentials to prevent typos.
   * C. Remove mappings to decrease the number of variables.
   * D. Use AWS::Include to reference publicly-hosted template files.
* [Answer](https://i.imgur.com/SPjTKUo.png)
109) A Developer wants to encrypt new objects that are being uploaded to an Amazon S3 bucket by an application. There must be an audit trail of who has used the key during this process. There should be no change to the performance of the application.Which type of encryption meets these requirements?
   * A. Server-side encryption using S3-managed keys
   * B. Server-side encryption with AWS KMS-managed keys
   * C. Client-side encryption with a client-side symmetric master key
   * D. Client-side encryption with AWS KMS-managed keys
* [Answer](https://i.imgur.com/NymobRZ.png)
110) An on-premises application makes repeated calls to store files to Amazon S3. As usage of the application has increased, "LimitExceeded" errors are being logged.What should be changed to fix this error?
   * A. Implement exponential backoffs in the application.
   * B. Load balance the application to multiple servers.
   * C. Move the application to Amazon EC2.
   * D. Add a one second delay to each API call.
* [Answer](https://i.imgur.com/HLiakW0.png)
111) An organization is storing large files in Amazon S3, and is writing a web application to display meta-data about the files to end-users. Based on the metadata a user selects an object to download. The organization needs a mechanism to index the files and provide single-digit millisecond latency retrieval for the metadata.
What AWS service should be used to accomplish this?
   * A. Amazon DynamoDB
   * B. Amazon EC2
   * C. AWS Lambda
   * D. Amazon RDS
* [Answer](https://i.imgur.com/3PlZ90p.png)
112) While developing an application that runs on Amazon EC2 in an Amazon VPC, a Developer identifies the need for centralized storage of application-level logs.
Which AWS service can be used to securely store these logs?
   * A. Amazon EC2 VPC Flow Logs
   * B. Amazon CloudWatch Logs
   * C. Amazon CloudSearch
   * D. AWS CloudTrail
* [Answer](https://i.imgur.com/Om5QVg9.png) error
113) A stock market monitoring application uses Amazon Kinesis for data ingestion. During simulated tests of peak data rates, the Kinesis stream cannot keep up with the incoming data.
What step will allow Kinesis to accommodate the traffic during peak hours?
   * A. Install the Kinesis Producer Library (KPL) for ingesting data into the stream.
   * B. Reduce the data retention period to allow for more data ingestion using DecreaseStreamRetentionPeriod.
   * C. Increase the shard count of the stream using UpdateShardCount.
   * D. Ingest multiple records into the stream in a single call using PutRecords.
* [Answer](https://i.imgur.com/VqFpGOx.png) error
114) Where can PortMapping be defined when launching containers in Amazon ECS?
   * A. Security groups
   * B. Amazon Elastic Container Registry (Amzon ECR)
   * C. Container agent
   * D. Task definition
* [Answer](https://i.imgur.com/m6KWJ2k.png)
115) An application uses Amazon Kinesis Data Streams to ingest and process large streams of data records in real time. Amazon EC2 instances consume and process the data from the shards of the Kinesis data stream by using Amazon Kinesis Client Library (KCL). The application handles the failure scenarios and does not require standby workers. The application reports that a specific shard is receiving more data than expected. To adapt to the changes in the rate of data flow, the "hot" shard is resharded.
Assuming that the initial number of shards in the Kinesis data stream is 4, and after resharding the number of shards increased to 6, what is the maximum number of EC2 instances that can be deployed to process data from all the shards?
   * A. 12
   * B. 6
   * C. 4
   * D. 1
* [Answer](https://i.imgur.com/vlfpnDe.png) error
116) A Development team is working on a case management solution that allows medical claims to be processed and reviewed. Users log in to provide information related to their medical and financial situations.
As part of the application, sensitive documents such as medical records, medical imaging, bank statements, and receipts are uploaded to Amazon S3. All documents must be securely transmitted and stored. All access to the documents must be recorded for auditing.
What is the MOST secure approach?
   * A. Use S3 default encryption using Advanced Encryption Standard-256 (AES-256) on the destination bucket.
   * B. Use Amazon Cognito for authorization and authentication to ensure the security of the application and documents.
   * C. Use AWS Lambda to encrypt and decrypt objects as they are placed into the S3 bucket.
   * D. Use client-side encryption/decryption with Amazon S3 and AWS KMS.
* [Answer](https://i.imgur.com/q9gpgCr.png)
117) A company has an internet-facing application that uses Web Identity Federation to obtain a temporary credential from AWS Security Token Service (AWS STS).
The app then uses the token to access AWS services.
Review the following response:
````xml
<AssumeRoleWithWebIdentityResponse xmlns="https://st.amazonaws.com/doc/2011-06-15/"
  <AssuremeRoleWithWebIdentityResult>
    <SubjectFromWebIdentityToken>amzn1.acccount.AF6RHO7KZU5XRQJGXK6HB56KR2A</SubjectFromWebIdentityToken>
    <Audience>client.5498841531868486423.1548@apps.example.com</Audience>
    <AssumeRoleUser>
      <Arn>arn:aws:sts:123456789012:assumed-role/FederatedWebIdentityRole/app1</arn>
      <AssumeRoleId>AROACLKWSDQRAOEXAMPLE:app1</AssumeRoleId>
    </AssumeRoleUser>
    <Credentials>
      <SessionToken>AQoDYXdzEE0a8ANXXXXXN01ewxE5TijQyp+IEXAMPLE</SessionToken>
      <SecretAccessKey>wJa1rXUtnFEMI/K7MDENG/bPxRfiCYzEXAMPLEKEY</SecretAccessKey>
      <Expiration>2014-10-24T23:00:23x</Expiration>
      <AccessKeyId>ASgeIAIOSFODNN7EXAMPLE</AccessKeyId>
    </Credentials>
    <Provider>www.amazon.com</Provider>
  </AssuremeRoleWithWebIdentityResult>
  <ResponseMetadata>
    <RequestId>ad4156e9-bce1-11e2-82e6-6b6efEXAMPLE</RequestId>
  </ResponseMetadata>
</AssumeRoleWithWebIdentityResponse>
````
Based on the response displayed what permissions are associated with the call from the application?
   * A. Permissions associated with the role AROACLKWSDQRAOEXAMPLE:app1
   * B. Permissions associated with the default role used when the AWS service was built
   * C. Permission associated with the IAM principal that owns the AccessKeyID ASgeIAIOSFODNN7EXAMPLE
   * D. Permissions associated with the account that owns the AWS service
* [Answer](https://i.imgur.com/umwjCQ4.png) error
118) A Developer is using AWS CLI, but when running list commands on a large number of resources, it is timing out.What can be done to avoid this time-out?
   * A. Use pagination
   * B. Use shorthand syntax
   * C. Use parameter values
   * D. Use quoting strings
* [Answer](https://i.imgur.com/wSLgcu7.png)
119) What does an Amazon SQS delay queue accomplish?
   * A. Messages are hidden for a configurable amount of time when they are first added to the queue.
   * B. Messages are hidden for a configurable amount of time after they are consumed from the queue.
   * C. The consumer can poll the queue for a configurable amount of time before retrieving a message.
   * D. Message cannot be deleted for a configurable amount of time after they are consumed from the queue.
* [Answer](https://i.imgur.com/3pZMP7V.png)
120) A company has multiple Developers located across the globe who are updating code incrementally for a development project. When Developers upload code concurrently, internet connectivity is slow and it is taking a long time to upload code for deployment in AWS Elastic Beanstalk.
Which step will result in minimized upload and deployment time with the LEAST amount of administrative effort?
   * A. Allow the Developers to upload the code to an Amazon S3 bucket, and deploy it directly to Elastic Beanstalk.
   * B. Allow the Developers to upload the code to a central FTP server to deploy the application to Elastic Beanstalk.
   * C. Create an AWS CodeCommit repository, allow the Developers to commit code to it, and then directly deploy the code to Elastic Beanstalk.
   * D. Create a code repository on an Amazon EC2 instance so that all Developers can update the code, and deploy the application from the instance to Elastic Beanstalk.
* [Answer](https://i.imgur.com/WLBhmb8.png)
121) A company recently migrated its web, application and NoSQL database tiers to AWS. The company is using Auto Scaling to scale the web and application tiers.
More than 95 percent of the Amazon DynamoDB requests are repeated read-requests.
How can the DynamoDB NoSQL tier be scaled up to cache these repeated requests?
   * A. Amazon EMR
   * B. Amazon DynamoDB Accelerator
   * C. Amazon SQS
   * D. Amazon CloudFront
* [Answer](https://i.imgur.com/p9L7IVe.png)
122) A company is building an application to track athlete performance using an Amazon DynamoDB table. Each item in the table is identified by a partition key
(user_id) and a sort key (sport_name). The table design is shown below:
````dynamoDB
Partition Key: user_id
Sort Key: sport_name
Attributes: score
            score_datetimme
````
A Developer is asked to write a leaderboard application to display the top performers (user_id) based on the score for each sport_name.
What process will allow the Developer to extract results MOST efficiently from the DynamoDB table?
   * A. Use a DynamoDB query operation with the key attributes of user_id and sport_name and order the results based on the score attribute.
   * B. Create a global secondary index with a partition key of sport_name and a sort key of score, and get the results
   * C. Use a DynamoDB scan operation to retrieve scores and user_id based on sport_name, and order the results based on the score attribute.
   * D. Create a local secondary index with a primary key of sport_name and a sort key of score and get the results based on the score attribute.
* [Answer](https://i.imgur.com/TQHFO7n.png) error
123) A Developer is creating a mobile application that will not require users to log in.
What is the MOST efficient method to grant users access to AWS resources?
   * A. Use an identity provider to securely authenticate with the application.
   * B. Create an AWS Lambda function to create an IAM user when a user accesses the application.
   * C. Create credentials using AWS KMS and apply these credentials to users when using the application.
   * D. Use Amazon Cognito to associate unauthenticated users with an IAM role that has limited access to resources
* [Answer](https://i.imgur.com/ImYIeAp.png) error
124) An application running on Amazon EC2 instances must access objects within an Amaon S3 busket that are encrypted using server-side encryption using AWS
KMS encryption keys (SSE-KMS). The application must have access to the customer master key (CMK) to decrypt the objects.
Which combination of steps will grant the application access? (**Select TWO**.)
   * A. Write an S3 bucket policy that grants the bucket access to the key.
   * B. Grant access to the key in the IAM EC2 role attached to the application's EC2 instances.
   * C. Write a key policy that enables IAM policies to grant access to the key.
   * D. Grant access to the key in the S3 bucket's ACL
   * E. Create a Systems Manager parameter that exposes the KMS key to the EC2 instances.
* [Answer](https://i.imgur.com/Fwahhlw.png) error
125) A company needs a fully-managed source control service that will work in AWS. The service must ensure that revision control synchronizes multiple distributed repositories by exchanging sets of changes peer-to-peer. All users need to work productively even when not connected to a network.
Which source control service should be used?
   * A. Subversion
   * B. AWS CodeBuild
   * C. AWS CodeCommit
   * D. AWS CodeStar
* [Answer](https://i.imgur.com/sOmysXy.png)
126) A Developer is writing a serverless application that requires that an AWS Lambda function be invoked every 10 minutes.
What is an automated and serverless way to trigger the function?
   * A. Deploy an Amazon EC2 instance based on Linux, and edit its /etc/crontab file by adding a command to periodically invoke the Lambda function.
   * B. Configure an environment variable named PERIOD for the Lambda function. Set the value to 600.
   * C. Create an Amazon CloudWatch Events rule that triggers on a regular schedule to invoke the Lambda function.
   * D. Create an Amazon SNS topic that has a subscription to the Lambda function with a 600-second timer.
* [Answer](https://i.imgur.com/xpE5X5Q.png) error
127) A Developer is writing an imaging micro service on AWS Lambda. The service is dependent on several libraries that are not available in the Lambda runtime environment.
Which strategy should the Developer follow to create the Lambda deployment package?
   * A. Create a ZIP file with the source code and all dependent libraries.
   * B. Create a ZIP file with the source code and a script that installs the dependent libraries at runtime.
   * C. Create a ZIP file with the source code. Stage the dependent libraries on an Amazon S3 bucket indicated by the Lambda environment variable LD_LIBRARY_PATH
   * D. Create a ZIP file with the source code and a buildspec.yaml file that installs the dependent libraries on AWS Lambda.
* [Answer](https://i.imgur.com/Kagfyhz.png) error
128) A Developer is designing a fault-tolerant environment where client sessions will be saved.
How can the Developer ensure that no sessions are lost if an Amazon EC2 instance fails?
   * A. Use sticky sessions with an Elastic Load Balancer target group.
   * B. Use Amazon SQS to save session data.
   * C. Use Amazon DynamoDB to perform scalable session hadling.
   * D. Use Elastic Load Balancer connection draining to stop sending requests to failing instances.
* [Answer](https://i.imgur.com/rvLwuqU.png) error
129) In a move toward using microservices, a company's Management team has asked all Development teams to build their services so that API requests depend only on that service's data store. One team is building a Payments service which has its own database; the service needs data that originates in the Accounts database. Both are using Amazon DynamoDB.
What approach will result in the simplest, decoupled, and reliable method to get near-real time updates from the Accounts database?
   * A. Use Amazon Glue to perform frequent ETL updates from the Accounts database to the Payments database.
   * B. Use Amazon ElastiCache in Payments, with the cache updated by triggers in the Accounts database.
   * C. Use Amazon Kinesis Data Firehouse to deliver all changes from the Accounts database to the Payments database.
   * D. Use Amazon DynamoDB Streams to deliver all changes from the Accounts database to the Payments database.
* [Answer](https://i.imgur.com/MJpRjkO.png)
130) How should custom libraries be utilized in AWS Lambda?
   * A. Host the library on Amazon S3 and reference to it from the Lambda function.
   * B. Install the library locally and upload a ZIP file of the Lambda function.
   * C. Import the necessary Lambda blueprint when creating the function.
   * D. Modify the function runtime to include the necessary library.
* [Answer](https://i.imgur.com/brO8ZwY.png) error
131) A company needs to secure its existing website running behind an Elastic Load Balancer. The website's Amazon EC2 instances are CPU-constrained.
What should be done to secure the website while not increasing the CPU load on the EC2 web servers? (**Select TWO**.)
   * A. Configure an Elastic Load Balancer with SSL pass-through.
   * B. Configure SSL certificates on an Elastic Load Balancer.
   * C. Configure an Elastic Load Balancer with a Loadable Storage System.
   * D. Install SSL certificates on the EC2 instances.
   * E. Configure an Elastic Load Balancer with SSL termination.
* [Answer](https://i.imgur.com/EmCmRUF.png)
132) An AWS Lambda function generates a 3MB JSON file and then uploads it to an Amazon S3 bucket daily. The file contains sensitive information, so the Developer must ensure that it is encrypted before uploading to the bucket.
Which of the following modifications should the Developer make to ensure that the data is encrypted before uploading it to the bucket?
   * A. Use the default AWS KMS customer master key for S3 in the Lambda function code.
   * B. Use the S3 managed key and call the GenerateDataKey API to encrypt the file.
   * C. Use the GenerateDateKey API, then use that data key to encrypt the file in the Lambda function code.
   * D. Use a custom KMS customer master key created for S3 in the Lambda function code.
* [Answer](https://i.imgur.com/BFlQIgR.png)
133) A Developer wants to find a list of items in a global secondary index from an Amazon DynamoDB table.
Which DynamoDB API call can the Developer use in order to consume the LEAST number of read capacity units?
   * A. Scan operation using eventually-consistent reads
   * B. Query operation using strongly-consistent reads
   * C. Query operation using eventually-consistent reads
   * D. Scan operation using strongly-consistent reads
* [Answer](https://i.imgur.com/XpYMZJd.png)
134) A Developer has published an update to an application that is served to a global user base using Amazon CloudFront. After deploying the application, users are not able to see the updated changes.
How can the Developer resolve this issue?
   * A. Remove the origin from the CloudFront configuration and add it again.
   * B. Disable forwarding of query strings and request headers from the CloudFront distribution configuration.
   * C. Invalidate all the application objects from the edge caches.
   * D. Disable the CloudFront distribution and enable it again to update all the edge locations
* [Answer](https://i.imgur.com/QEsdpyq.png)
135) A Developer must deploy a new AWS Lambda function using an AWS CloudFormation template.
Which procedures will deploy a Lambda function? (**Select TWO**.)
   * A. Upload the code to an AWS CodeCommit repository, then add a reference to it in an AWS::Lambda::Function resource in the template.
   * B. Create an AWS::Lambda::Function resource in the template, then write the code directly inside the CloudFormation template.
   * C. Upload a .ZIP file containing the function code to Amazon S3, then add a reference to it in an AWS::Lambda::Function resource in the template.
   * D. Upload a .ZIP file to AWS CloudFormation containing the function code, then add a reference to it in an AWS::Lambda::Function resource in the template.
   * E. Upload the function code to a private Git repository, then add a reference to it in an AWS::Lambda::Function resource in the template. BD
* [Answer](https://i.imgur.com/YZXDhYg.png) error
136) A Developer wants to enable AWS X-Ray for a secure application that runs in an Amazon ECS environment.
What combination of steps will enable X-Ray? (**Select THREE**.)
   * A. Create a Docker image that runs the X-Ray daemon.
   * B. Add instrumentation to the application code for X-Ray.
   * C. Install the X-Ray daemon on the underlying EC2 instance.
   * D. Configure and use an IAM EC2 instance role.
   * E. Register the application with X-Ray.
   * F. Configure and use an IAM role for tasks.
* [Answer](https://i.imgur.com/kbmIjN9.png) error
137) A Developer is designing a new application that uses Amazon S3. To satisfy compliance requirements, the Developer must encrypt the data at rest.
How can the Developer accomplish this?
   * A. Use s3:x-amz-acl as a condition in the S3 bucket policy.
   * B. Use Amazon RDS with default encryption.
   * C. Use aws:SecureTransport as a condition in the S3 bucket policy.
   * D. Turn on S3 default encryption for the S3 bucket.
* [Answer](https://i.imgur.com/MYjTUwg.png) 
138) An AWS Elastic Beanstalk application needs to be deployed in multiple regions and requires a different Amazon Machine Image (AMI) in each region.
Which AWS CloudFormation template key can be used to specify the correct AMI for each region?
   * A. Parameters
   * B. Outputs
   * C. Mappings
   * D. Resources
* [Answer](https://i.imgur.com/u1iu9pl.png)
139) A Developer has been asked to make changes to the source code of an AWS Lambda function. The function is managed using an AWS CloudFormation template. The template is configured to load the source code from an Amazon S3 bucket. The Developer manually created a .ZIP file deployment package containing the changes and put the file into the correct location on Amazon S3. When the function is invoked, the code changes have not been applied.
What step is required to update the function with the changes?
   * A. Delete the .ZIP file on S3, and re-upload by using a different object key name.
   * B. Update the CloudFormation stack with the correct values for the function code properties S3Bucket, S3Key, or S3ObjectVersion.
   * C. Ensure that the function source code is base64-encoded before uploading the deployment package to S3.
   * D. Modify the execution role of the Lambda function to allow S3 access permission to the deployment package .ZIP file.
* [Answer](https://i.imgur.com/bJV8Vua.png)
140) A Developer needs to design an application running on AWS that will be used to consume Amazon SQS messages that range from 1 KB up to 1GB in size.
How should the Amazon SQS messages be managed?
   * A. Use Amazon S3 and the Amazon SQS CLI.
   * B. Use Amazon S3 and the Amazon SQS Extended Client Library for Java.
   * C. Use Amazon EBS and the Amazon SQS CLI.
   * D. Use Amazon EFS and the Amazon SQS CLI.
* [Answer](https://i.imgur.com/k14eEpr.png)
141) A company is developing an application that will run on several Amazon EC2 instances in an Auto Scaling group and can access a database running on Amazon
EC2. The application needs to store secrets required to connect to the database. The application must allow for periodic secret rotation, and there should be no changes to the application when a secret changes.
What is the SAFEST way to meet these requirements?
   * A. Associate an IAM role to the EC2 instance where the application is running with permission to access the database.
   * B. Use AWS Systems Manager Parameter Store with the SecureString data type to store secrets.
   * C. Configure the application to store secrets in Amazon S3 object metadata.
   * D. Hard code the database secrets in the application code itself
* [Answer](https://i.imgur.com/vXbOLUv.png)
142) A Developer writes an AWS Lambda function and uploads the code in a .ZIP file to Amazon S3. The Developer makes changes to the code and uploads a new
.ZIP file to Amazon S3. However, Lambda executes the earlier code.
How can the Developer fix this in the LEAST disruptive way?
   * A. Create another Lambda function and specify the new .ZIP file.
   * B. Call the update-function-code API.
   * C. Remove the earlier .ZIP file first, then add the new .ZIP file.
   * D. Call the create-alias API.
* [Answer](https://i.imgur.com/5S9D9gR.png)
143) An AWS Lambda function must read data from an Amazon RDS MySQL database in a VPC and also reach a public endpoint over the internet to get additional data.
Which steps must be taken to allow the function to access both the RDS resource and the public endpoint? (**Select TWO**.)
   * A. Modify the default configuration for the Lambda function to associate it with an Amazon VPC private subnet.
   * B. Modify the default network access control list to allow outbound traffic.
   * C. Add a NAT Gateway to the VPC.
   * D. Modify the default configuration of the Lambda function to associate it with a VPC public subnet.
   * E. Add an environmental variable to the Lambda function to allow outbound internet access.
* [Answer](https://i.imgur.com/3SODrUR.png)
144) A Developer must build an application that uses Amazon DynamoDB. The requirements state that items being stored in the DynamoDB table will be 7KB in size and that reads must be strongly consistent. The maximum read rate is 3 items per second, and the maximum write rate is 10 items per second.
How should the Developer size the DynamoDB table to meet these requirements?
   * A. Read: 3 read capacity units Write: 70 write capacity units
   * B. Read: 6 read capacity units Write: 70 write capacity units
   * C. Read: 6 read capacity units Write: 10 write capacity units
   * D. Read: 3 read capacity units Write: 10 write capacity units
* [Answer](https://i.imgur.com/CkBsRFm.png)
145) A Developer is creating an AWS Lambda function to process a stream of data from an Amazon Kinesis Data Stream. When the Lambda function parses the data and encounters a missing field, it exits the function with an error. The function is generating duplicate records from the Kinesis stream. When the Developer looks at the stream output without the Lambda function, there are no duplicate records.
What is the reason for the duplicates?
   * A. The Lambda function did not advance the Kinesis stream pointer to the next record after the error.
   * B. The Lambda event source used asynchronous invocation, resulting in duplicate records.
   * C. The Lambda function did not handle the error, and the Lambda service attempted to reprocess the data.
   * D. The Lambda function is not keeping up with the amount of data coming from the stream.
* [Answer](https://i.imgur.com/c2ypXxB.png) error
146) A company maintains an application responsible for processing several thousand external callbacks each day. The company's System administrators want to know how many callbacks are being received on a rolling basis, and they want this data available for 10 days.
The company also wants the ability to issue automated alerts if the number of callbacks exceeds the defined thresholds.
What is the MOST cost-effective way to address the need to track and alert on these statistics?
   * A. Push callback data to an Amazon RDS database that can be queried to show historical data and to alert on exceeded thresholds.
   * B. Push callback data to AWS X-Ray and use AWS Lambda to query, display, and alert on exceeded thresholds.
   * C. Push callback data to Amazon Kinesis Data Streams and invoke an AWS Lambda function that stores data in Amazon DynamoDB and sends the required alerts.
   * D. Push callback data to Amazon CloudWatch as a custom metric and use the CloudWatch alerting mechanisms to alert System Administrators.
* [Answer](https://i.imgur.com/OKGBRcC.png)
147) A company has a website that is developed in PHP and WordPress and is launched using AWS Elastic Beanstalk. There is a new version of the website that needs to be deployed in the Elastic Beanstalk environment. The company cannot tolerate having the website offline if an update fails. Deployments must have minimal impact and rollback as soon as possible.
What deployment method should be used?
   * A. All at once
   * B. Rolling
   * C. Snapshots
   * D. Immutable
* [Answer](https://i.imgur.com/SmCmHL0.png)
148) A company has a multi-tiered web application on AWS. During a recent spike in traffic, one of the primary relational databases on Amazon RDS could not serve all the traffic. Some read queries for repeatedly accessed items failed, so users received error messages.
What can be done to minimize the impact on database read queries MOST efficiently during future traffic spikes?
   * A. Use Amazon S3 to cache database query results.
   * B. Use Amazon RDS as a custom origin for Amazon CloudFront.
   * C. Use local storage and memory on Amazon EC2 instances to cache data.
   * D. Use Amazon ElastiCache in front of the primary database to cache data.
* [Answer](https://i.imgur.com/NC2zMDT.png)
149) A Development team currently supports an application that uses an in-memory store to save accumulated game results. Individual results are stored in a database. As part of migrating to AWS, the team needs to use automatic scaling. The team knows this will yield inconsistent results.
Where should the team store these accumulated game results to BEST allow for consistent results without impacting performance?
   * A. Amazon S3
   * B. Amazon RDS
   * C. Amazon ElastiCache
   * D. Amazon Kinesis 
* [Answer](https://i.imgur.com/iDwZvWB.png)
150) In a multi-container Docker environment in AWS Elastic Beanstalk, what is required to configure container instances in the environment?
   * A. An Amazon ECS task definition
   * B. An Amazon ECS cluster
   * C. A Docker in an application package
   * D. A CLI for Elastic Beanstalk
* [Answer](https://i.imgur.com/ES67mXL.png)
151) An application that runs on an Amazon EC2 instance needs to access and make API calls to multiple AWS services.
What is the MOST secure way to provide access to the AWS services with MINIMAL management overhead?
   * A. Use AWS KMS to store and retrieve credentials.
   * B. Use EC2 instance profiles.
   * C. Use AWS root user to make requests to the application.
   * D. Store and retrieve credentials from AWS CodeCommit.
* [Answer](https://i.imgur.com/bfzex6w.png) error
152) A company is creating an application that will require users to access AWS services and allow them to reset their own passwords.
Which of the following would allow the company to manage users and authorization while allowing users to reset their own passwords?
   * A. Amazon Cognito identify pools and AWS STS
   * B. Amazon Cognito identity pools and AWS IAM
   * C. Amazon Cognito user pools and AWS KMS
   * D. Amazon Cognito user pools and identity pools
* [Answer](https://i.imgur.com/gh48wPf.png) 
153) A company has three different environments: Development, QA, and Production. The company wants to deploy its code first in the Development environment, then QA, and then Production.
Which AWS service can be used to meet this requirement?
   * A. Use AWS CodeCommit to create multiple repositories to deploy the application.
   * B. Use AWS CodeBuild to create, configure, and deploy multiple build application projects.
   * C. Use AWS Data Pipeline to create multiple data pipeline provisions to deploy the application.
   * D. Use AWS CodeDeploy to create multiple deployment groups.
* [Answer](https://i.imgur.com/Q0WOCqM.png) error
154) A company uses Amazon DynamoDB for managing and tracking orders. The DynamoDB table is partitioned based on the order date. The company receives a huge increase in orders during a sales event, causing DynamoDB writes to throttle, and the consumed throughput is far below the provisioned throughput.
According to AWS best practices, how can this issue be resolved with MINIMAL costs?
   * A. Create a new DynamoDB table for every order date.
   * B. Increase the read and write capacity units of the DynamoDB table.
   * C. Add a random number suffix to the partition key values.
   * D. Add a global secondary index to the DynamoDB table.
* [Answer](https://i.imgur.com/A84PY7j.png) error
155) A company is providing services to many downstream consumers. Each consumer may connect to one or more services. This has resulted in a complex architecture that is difficult to manage and does not scale well. The company needs a single interface to manage these services to consumers.
Which AWS service should be used to refactor this architecture?
   * A. AWS Lambda
   * B. AWS X-Ray
   * C. Amazon SQS
   * D. Amazon API Gateway
* [Answer](https://i.imgur.com/UMIFJmm.png) error
156) A Developer is creating a serverless website with content that includes HTML files, images, videos, and JavaScript (client-side scripts).
Which combination of services should the Developer use to create the website?
   * A. Amazon S3 and Amazon CloudFront
   * B. Amazon EC2 and Amazon ElastiCache
   * C. Amazon ECS and Redis
   * D. AWS Lambda and Amazon API Gateway
* [Answer](https://i.imgur.com/TcIOqda.png) error
157) A Development team has pushed out 10 applications running on several Amazon EC2 instances. The Operations team is asking for a graphical representation of one key performance metric for each application. These metrics should be available on one screen for easy monitoring.
Which steps should the Developer take to accomplish this using Amazon CloudWatch?
   * A. Create a custom namespace with a unique metric name for each application.
   * B. Create a custom dimension with a unique metric name for each application.
   * C. Create a custom event with a unique metric name for each application.
   * D. Create a custom alarm with a unique metric name for each application.
* [Answer](https://i.imgur.com/9XBYKdc.png)
158) A Developer wants access to make the log data of an application running on an EC2 instance available to systems administrators.
Which of the following enables monitoring of this metric in Amazon CloudWatch?
   * A. Retrieve the log data from CloudWatch using the GetMetricData API call
   * B. Retrieve the log data from AWS CloudTrail using the LookupEvents API call.
   * C. Launch a new EC2 instance, configure Amazon CloudWatch Events, and then install the application.
   * D. Install the Amazon CloudWatch Logs agent on the EC2 instance that the application is running on.
* [Answer](https://i.imgur.com/xwsbqhp.png)
159) A nightly batch job loads 1 million new records into a DynamoDB table. The records are only needed for one hour, and the table needs to be empty by the next night's batch job.
Which is the MOST efficient and cost-effective method to provide an empty table?
   * A. Use DeleteItem using a ConditionExpression.
   * B. Use BatchWriteItem to empty all of the rows.
   * C. Write a recursive function that scans and calls out DeleteItem.
   * D. Create and then delete the table after the task has completed.
* [Answer](https://i.imgur.com/OfFhtca.png)
160) A company has an application that logs all information to Amazon S3. Whenever there is a new log file, an AWS Lambda function is invoked to process the log files. The code works, gathering all of the necessary information. However, when checking the Lambda function logs, duplicate entries with the same request ID are found.
What is causing the duplicate entries?
   * A. The S3 bucket name was specified incorrectly.
   * B. The Lambda function failed, and the Lambda service retired the invocation with a delay.
   * C. There was an S3 outage, which caused duplicate entries of the sale log file.
   * D. The application stopped intermittently and then resumed.
* [Answer](https://i.imgur.com/mKtvI8c.png)
161) A company maintains a REST service using Amazon API Gateway and the API Gateway native API key validation. The company recently launched a new registration page, which allows users to sign up for the service. The registration page creates a new API key using CreateApiKey and sends the new key to the user. When the user attempts to call the API using this key, the user receives a 403 Forbidden error. Existing users are unaffected and can still call the API.
What code updates will grant these new users access to the API?
   * A. The createDeployment method must be called so the API can be redeployed to include the newly created API key.
   * B. The updateAuthorizer method must be called to update the API's authorizer to include the newly created API key.
   * C. The importApiKeys method must be called to import all newly created API keys into the current stage of the API.
   * D. The createUsagePlanKey method must be called to associate the newly created API key with the correct usage plan
* [Answer](https://i.imgur.com/yJwoCpF.png) error
162) A Developer is writing a mobile application that allows users to view images from an S3 bucket. The users must be able to log in with their Amazon login, as well as FacebookÂ® and/or GoogleÂ® accounts.
How can the Developer provide this authentication functionality?
   * A. Use Amazon Cognito with web identity federation.
   * B. Use Amazon Cognito with SAML-based identity federation.
   * C. Use AWS IAM Access/Secret keys in the application code to allow Get* on the S3 bucket.
   * D. Use AWS STS AssumeRole in the application code and assume a role with Get* permissions on the S3 bucket. 
* [Answer](https://i.imgur.com/u9e0Dp1.png)
163) A Developer has created a Lambda function and is finding that the function is taking longer to complete than expected. After some debugging, the Developer has discovered that increasing compute capacity would improve performance.
How can the Developer increase the Lambda compute resources?
   * A. Run on a larger instance size with more compute capacity.
   * B. Increase the maximum execution time.
   * C. Specify a larger compute capacity when calling the Lambda function.
   * D. Increase the allocated memory for the Lambda function.
* [Answer](https://i.imgur.com/9IAjGMW.png)
164) An e-commerce site allows returning users to log in to display customized web pages. The workflow is shown in the image below:
[<img src="https://i.imgur.com/U1J8jYi.png">](https://i.imgur.com/U1J8jYi.png)

An application is running on EC2 instances. Amazon RDS is used for the database that stores user accounts and preferences. The website freezes or is slow to load while waiting for the login step to complete. The remaining components of the site are well-optimized.
Which of the following techniques will resolve this issue? (**Select Two**.)
   * A. Implement the user login page as an asynchronous Lambda function.
   * B. Use Amazon ElastiCache for MemCached to cache user data.
   * C. Use Amazon Application Load Balancer to load balance the traffic to the website.
   * D. Call the database asynchronously so the code can continue executing.
   * E. Batch login requests from hundreds of users together as a single read request to the database. 
* [Answer](https://i.imgur.com/1DDbgU1.png)
165) A Developer is building a mobile application and needs any update to user profile data to be pushed to all devices accessing the specific identity. The Developer does not want to manage a back end to maintain the user profile data.
What is the MOST efficient way for the Developer to achieve these requirements using Amazon Cognito?
   * A. Use Cognito federated identities.
   * B. Use a Cognito user pool.
   * C. Use Cognito Sync.
   * D. Use Cognito events.
* [Answer](https://i.imgur.com/OyN3jom.png)
166) A company is migrating a single-server, on-premises web application to AWS. The company intends to use multiple servers behind an Elastic Load Balancer
(ELB) to balance the load, and will also store session data in memory on the web server. The company does not want to lose that session data if a server fails or goes offline, and it wants to minimize user's downtime.
Where should the company move session data to MOST effectively reduce downtime and make users' session data more fault tolerant?
   * A. An Amazon ElastiCache for Redis cluster
   * B. A second Amazon EBS volume
   * C. The web server's primary disk
   * D. An Amazon EC2 instance dedicated to session data
* [Answer](https://i.imgur.com/IbDUN5u.png)
167) A Developer created configuration specifications for an AWS Elastic Beanstalk application in a file named healthcheckurl.yaml in the .ebextensions/directory of their application source bundle. The file contains the following:
````yaml
option_settings:
  - namespace: aws:elasticbeanstalk:application
    option_name: Application Healtcheck URL
    value: /health_check
````
After the application launches, the health check is not being run on the correct path, event though it is valid.
What can be done to correct this configuration file?
   * A. Convert the file to JSON format.
   * B. Rename the file to a .config extension.
   * C. Change the configuration section from options_settings to resources.
   * D. Change the namespace of the option settings to a custom namespace. 
* [Answer](https://i.imgur.com/wGZrY9G.png)
168) A Developer is making changes to a custom application that is currently using AWS Elastic Beanstalk.
After the Developer completes the changes, what solutions will update the Elastic Beanstalk environment with the new application version? (**Choose two**.)
   * A. Package the application code into a .zip file, and upload, then deploy the packaged application from the AWS Management Console
   * B. Package the application code into a .tar file, create a new application version from the AWS Management Console, then update the environment by using AWS CLI
    * C. Package the application code into a .tar file, and upload and deploy the packaged application from the AWS Management Console
    * D. Package the application code into a .zip file, create a new application version from the packaged application by using AWS CLI, then update the environment by using AWS CLI
    * E. Package the application code into a .zip file, create a new application version from the AWS Management Console, then rebuild the environment by using AWS CLI
* [Answer](https://i.imgur.com/pg0cc7s.png)
169) To include objects defined by the AWS Serverless Application Model (SAM) in an AWS CloudFormation template, in addition to Resources, what section MUST be included in the document root?
   * A. Conditions
   * B. Globals
   * C. Transform
   * D. Properties
* [Answer](https://i.imgur.com/KhxGnfc.png)
170) A company is using Amazon RDS MySQL instances for its application database tier and Apache Tomcat servers for its web tier. Most of the database queries from web applications are repeated read requests.
Use of which AWS service would increase in performance by adding in-memory store for repeated read queries?
   * A. Amazon RDS Multi-AZ
   * B. Amazon SQS
   * C. Amazon ElastiCache
   * D. Amazon RDS read replica
* [Answer](https://i.imgur.com/klQTdOu.png) error
171) A Developer is investigating an issue whereby certain requests are passing through an Amazon API Gateway endpoint /MyAPI, but the requests do not reach the
AWS Lambda function backing /MyAPI. The Developer found that a second Lambda function sometimes runs at maximum concurrency allowed for the given AWS account.
How can the Developer address this issue?
   * A. Manually reduce the concurrent execution limit at the account level
   * B. Add another API Gateway stage for /MyAPI, and shard the requests
   * C. Configure the second Lambda function's concurrency execution limit
   * D. Reduce the throttling limits in the API Gateway /MyAPI endpoint C
* [Answer](https://i.imgur.com/Dw81lMT.png)
172) A Developer must analyze performance issues with production-distributed applications written as AWS Lambda functions. These distributed Lambda applications invoke other components that make up the applications.
How should the Developer identify and troubleshoot the root cause of the performance issues in production?
   * A. Add logging statements to the Lambda functions, then use Amazon CloudWatch to view the logs.
   * B. Use AWS Cloud Trail and then examine the logs
   * C. Use AWS X-Ray, then examine the segments and errors
   * D. Run Amazon Inspector agents and then analyze performance
* [Answer](https://i.imgur.com/PuyzSHI.png)
173) A Developer wants to debug an application by searching and filtering log data. The application logs are stored in Amazon CloudWatch Logs. The Developer creates a new metric filter to count exceptions in the application logs. However, no results are returned from the logs.
What is the reason that no filtered results are being returned?
   * A. A setup of the Amazon CloudWatch interface VPC endpoint is required for filtering the CloudWatch Logs in the VPC
   * B. CloudWatch Logs only publishes metric data for events that happen after the filter is created
   * C. The log group for CloudWatch Logs should be first streamed to Amazon Elasticsearch Service before metric filtering returns the results
   * D. Metric data points for logs groups can be filtered only after they are exported to an Amazon S3 bucket
* [Answer](https://i.imgur.com/mNbQg3w.png)
174) An e-commerce web application that shares session state on-premises is being migrated to AWS. The application must be fault tolerant, natively highly scalable, and any service interruption should not affect the user experience.
What is the best option to store the session state?
   * A. Store the session state in Amazon ElastiCache
   * B. Store the session state in Amazon CloudFront
   * C. Store the session state in Amazon S3
   * D. Enable session stickiness using elastic load balancers
* [Answer](https://i.imgur.com/qcZg5jd.png)
175) A Developer is creating a template that uses AWS CloudFormation to deploy an application. This application is serverless and uses Amazon API Gateway,
Amazon DynamoDB, and AWS Lambda.
Which tool should the Developer use to define simplified syntax for expressing serverless resources?
   * A. CloudFormation serverless intrinsic functions
   * B. AWS serverless express
   * C. An AWS serverless application model
   * D. A CloudFormation serverless plugin
* [Answer](https://i.imgur.com/20RpYs7.png)
176) A Developer has a stateful web server on-premises that is being migrated to AWS. The Developer must have greater elasticity in the new design.
How should the Developer re-factor the application to make it more elastic? (**Choose two**.)
   * A. Use pessimistic concurrency on Amazon DynamoDB
   * B. Use Amazon CloudFront with an Auto Scaling group
   * C. Use Amazon CloudFront with an AWS Web Application Firewall
   * D. Store session state data in an Amazon DynamoDB table
   * E. Use an ELB with an Auto Scaling group
* [Answer](https://i.imgur.com/woq5SPR.png)
177) A company needs to distribute firmware updates to its customers around the world.
Which service will allow easy and secure control of the access to the downloads at the lowest cost?
   * A. Use Amazon CloudFront with signed URLs for Amazon S3
   * B. Create a dedicated Amazon CloudFront Distribution for each customer
   * C. Use Amazon CloudFront with AWS Lambda@Edge
   * D. Use Amazon API Gateway and AWS Lambda to control access to an S3 bucket
* [Answer](https://i.imgur.com/whOAmrh.png)
178) A company is running an application built on AWS Lambda functions. One Lambda function has performance issues when it has to download a 50MB file from the
Internet in every execution. This function is called multiple times a second.
What solution would give the BEST performance increase?
   * A. Cache the file in the /tmp directory
   * B. Increase the Lambda maximum execution time
   * C. Put an Elastic Load Balancer in front of the Lambda function
   * D. Cache the file in Amazon S3
* [Answer](https://i.imgur.com/fnohnYd.png) error
179) An application writes items to an Amazon DynamoDB table. As the application scales to thousands of instances, calls to the DynamoDB API generate occasional
ThrottlingException errors. The application is coded in a language incompatible with the AWS SDK.
How should the error be handled?
   * A. Add exponential backoff to the application logic
   * B. Use Amazon SQS as an API message bus
   * C. Pass API calls through Amazon API Gateway
   * D. Send the items to DynamoDB through Amazon Kinesis Data Firehose
* [Answer](https://i.imgur.com/j7Fq512.png)
180) An application deployed on AWS Elastic Beanstalk experiences increased error rates during deployments of new application versions, resulting in service degradation for users. The Development team believes that this is because of the reduction in capacity during the deployment steps. The team would like to change the deployment policy configuration of the environment to an option that maintains full capacity during deployment while using the existing instances.
Which deployment policy will meet these requirements while using the existing instances?
   * A. All at once
   * B. Rolling
   * C. Rolling with additional batch
   * D. Immutable
* [Answer](https://i.imgur.com/lQIvWPI.png)
181) A Developer is building a web application that uses Amazon API Gateway to expose an AWS Lambda function to process requests from clients. During testing, the Developer notices that the API Gateway times out even though the Lambda function finishes under the set time limit.
Which of the following API Gateway metrics in Amazon CloudWatch can help the Developer troubleshoot the issue? (Choose two.)
   * A. CacheHitCount
   * B. IntegrationLatency
   * C. CacheMissCount
   * D. Latency
   * E. Count
* [Answer](https://i.imgur.com/BPOPW0D.png) error
182) An AWS Lambda function must access an external site by using a regularly rotated user name and password. These items must be kept securely and cannot be stored in the function code.
What combination of AWS services can be used to accomplish this? (**Choose two**.)
   * A. AWS Certificate Manager (ACM)
   * B. AWS Systems Manager Parameter Store
   * C. AWS Trusted Advisor
   * D. AWS KMS
   * E. Amazon GuardDuty
* [Answer](https://i.imgur.com/EPwEmsu.png)
183) A Developer is trying to deploy a serverless application using AWS CodeDeploy. The application was updated and needs to be redeployed.
What file does the Developer need to update to push that change through CodeDeploy?
   * A. dockerrun.aws.json
   * B. buildspec.yml
   * C. appspec.yml
   * D. ebextensions.config
* [Answer](https://i.imgur.com/02nR44m.png)
184) A Developer wants to upload data to Amazon S3 and must encrypt the data in transit.
Which of the following solutions will accomplish this task? (**Choose two**.)
   * A. Set up hardware VPN tunnels to a VPC and access S3 through a VPC endpoint
   * B. Set up Client-Side Encryption with an AWS KMS-Managed Customer Master Key
   * C. Set up Server-Side Encryption with AWS KMS-Managed Keys
   * D. Transfer the data over an SSL connection
   * E. Set up Server-Side Encryption with S3-Managed Keys
* [Answer](https://i.imgur.com/T1BI7YY.png)
185) A company is running a Docker application on Amazon ECS. The application must scale based on user load in the last 15 seconds.
How should a Developer instrument the code so that the requirement can be met?
   * A. Create a high-resolution custom Amazon CloudWatch metric for user activity data, then publish data every 30 seconds
   * B. Create a high-resolution custom Amazon CloudWatch metric for user activity data, then publish data every 5 seconds
   * C. Create a standard-resolution custom Amazon CloudWatch metric for user activity data, then publish data every 30 seconds
   * D. Create a standard-resolution custom Amazon CloudWatch metric for user activity data, then publish data every 5 seconds
* [Answer](https://i.imgur.com/hxEhift.png)
186) A company needs to ingest terabytes of data each hour from thousands of sources that are delivered almost continually throughout the day. The volume of messages generated varies over the course of the day. Messages must be delivered in real time for fraud detection and live operational dashboards.
Which approach will meet these requirements?
   * A. Send the messages to an Amazon SQS queue, then process the messages by using a fleet of Amazon EC2 instances
   * B. Use the Amazon S3 API to write messages to an S3 bucket, then process the messages by using Amazon Redshift
   * C. Use AWS Data Pipeline to automate the movement and transformation of data
   * D. Use Amazon Kinesis Data Streams with Kinesis Client Library to ingest and deliver messages
* [Answer](https://i.imgur.com/1F8e58U.png)
187) A Developer accesses AWS CodeCommit over SSH. The SSH keys configured to access AWS CodeCommit are tied to a user with the following permissions:
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "codecommit:BatchGetRepositories",
        "codecommit:Get*",
        "codecommit:List*",
        "codecommit:GitPull"
      ],
      "Resource": "*"
    }
  ]
}
````
The Developer needs to create/delete branches.
Which specific IAM permissions need to be added, based on the principle of least privilege?
   * A. "codecommit:CreateBranch" "codecommit:DeleteBranch"
   * B. "codecommit:Put*"
   * C. "codecommit:Update*"
   * D. "codecommit:*"
* [Answer](https://i.imgur.com/ZXPnYm2.png)
188) A Developer has been asked to create an AWS Lambda function that is triggered any time updates are made to items in an Amazon DynamoDB table. The function has been created, and appropriate permissions have been added to the Lambda execution role. Amazon DynamoDB streams have been enabled for the table, but the function is still not being triggered.
Which option would enable DynamoDB table updates to trigger the Lambda function?
   * A. Change the StreamViewType parameter value to NEW_AND_OLD_IMAGES for the DynamoDB table
   * B. Configure event source mapping for the Lambda function
   * C. Map an Amazon SNS topic to the DynamoDB streams
   * D. increase the maximum execution time (timeout) setting of the Lambda function
* [Answer](https://i.imgur.com/rl5f1BE.png)
189) An application is being developed to audit several AWS accounts. The application will run in Account A and must access AWS services in Accounts B and C.
What is the MOST secure way to allow the application to call AWS services in each audited account?
   * A. Configure cross-account roles in each audited account. Write code in Account a that assumes those roles
   * B. Use S3 cross-region replication to communicate among accounts, with Amazon S3 event notifications to trigger Lambda functions
   * C. Deploy an application in each audited account with its own role. Have Account A authenticate with the application
   * D. Create an IAM user with an access key in each audited account. Write code in Account A that uses those access keys
* [Answer](https://i.imgur.com/mfQMHpJ.png)
190) A Developer is building a three-tier web application that should be able to handle a minimum of 5000 requests per minute. Requirements state that the web tier should be completely stateless while the application maintains session state for the users.
How can session data be externalized, keeping latency at the LOWEST possible value?
   * A. Create an Amazon RDS instance, then implement session handling at the application level to leverage a database inside the RDS database instance for session data storage
   * B. Implement a shared file system solution across the underlying Amazon EC2 instances, then implement session handling at the application level to leverage the shared file system for session data storage
   * C. Create an Amazon ElastiCache Memcached cluster, then implement session handling at the application level to leverage the cluster for session data storage
   * D. Create an Amazon DynamoDB table, then implement session handling at the application level to leverage the table for session data storage
* [Answer](https://i.imgur.com/DxuI7hu.png)
191) An Amazon DynamoDB table uses a Global Secondary Index (GSI) to support read queries. The primary table is write-heavy, whereas the GSI is used for read operations. Looking at Amazon CloudWatch metrics, the Developer notices that write operations to the primary table are throttled frequently under heavy write activity. However, write capacity units to the primary table are available and not fully consumed.
Why is the table being throttled?
   * A. The GSI write capacity units are underprovisioned
   * B. There are not enough read capacity units on the primary table
   * C. Amazon DynamoDB Streams is not enabled on the table
   * D. A large write operation is being performed against another table
* [Answer](https://i.imgur.com/ed79F46.png)
192) A company runs an e-commerce website that uses Amazon DynamoDB where pricing for items is dynamically updated in real time. At any given time, multiple updates may occur simultaneously for pricing information on a particular product. This is causing the original editor's changes to be overwritten without a proper review process.
Which DynamoDB write option should be selected to prevent this overwriting?
   * A. Concurrent writes
   * B. Conditional writes
   * C. Atomic writes
   * D. Batch writes
* [Answer](https://i.imgur.com/2UqzQIA.png)
193) A company needs a version control system for collaborative software development. Features of the system must include the following:
✑ Support for batches of changes across multiple files
✑ Parallel branching
✑ Version tracking
Which AWS service will meet these requirements?
   * A. AWS CodePipeline
   * B. Amazon S3
   * C. AWS Code Build
   * D. AWS CodeCommit 
* [Answer](https://i.imgur.com/4yZMiJC.png)
194) A company is using continuous integration and continuous delivery systems. A Developer now needs to automate a software package deployment to both
Amazon EC2 instances and virtual servers running on-premises.
Which AWS service should be used to accomplish this?
   * A. AWS CodePipeline
   * B. AWS CodeBuild
   * C. AWS Elastic Beanstalk
   * D. AWS CodeDeploy
* [Answer](https://i.imgur.com/3NhBb9T.png)
195) A Developer created a new AWS account and must create a scalable AWS Lambda function that meets the following requirements for concurrent execution:
✑ Average execution time of 100 seconds
✑ 50 requests per second
Which step must be taken prior to deployment to prevent errors?
   * A. Implement dead-letter queues to capture invocation errors
   * B. Add an event source from Amazon API Gateway to the Lambda function
   * C. Implement error handling within the application code
   * D. Contact AWS Support to increase the concurrent execution limits
* [Answer](https://i.imgur.com/LNs6Hmh.png) error
196) A Development team wants to instrument their code to provide more detailed information to AWS X-Ray than simple outgoing and incoming requests. This will generate large amounts of data, so the Development team wants to implement indexing so they can filter the data.
What should the Development team do to achieve this?
  * A. Add annotations to the segment document and the code
  * B. Add metadata to the segment document and the code
  * C. Configure the necessary X-Ray environment variables
  * D. Install required plugins for the appropriate AWS SDK
* [Answer](https://i.imgur.com/FMTxToq.png)
197) A team of Developers must migrate an application running inside an AWS Elastic Beanstalk environment from a Classic Load Balancer to an Application Load
Balancer.
Which steps should be taken to accomplish the task using the AWS Management Console?
   * A. 1. Update the application code in the existing deployment. 2. Select a new load balancer type before running the deployment. 3. Deploy the new version of the application code to the environment.
   * B. 1. Create a new environment with the same configurations except for the load balancer type. 2. Deploy the same application version as used in the original environment. 3. Run the swap-environment-cnames action.
   * C. 1. Clone the existing environment, changing the associated load balancer type. 2. Deploy the same application version as used in the original environment. 3. Run the swap-environment-cnames action.
   * D. 1. Edit the environment definitions in the existing deployment. 2. Change the associated load balancer type according to the requirements. 3. Rebuild the environment with the new load balancer type.
* [Answer](https://i.imgur.com/MtWQRpL.png) error
198) A Developer must encrypt a 100-GB object using AWS KMS.
What is the BEST approach?
   * A. Make an Encrypt API call to encrypt the plaintext data as ciphertext using a customer master key (CMK)
   * B. Make an Encrypt API call to encrypt the plaintext data as ciphertext using a customer master key (CMK) with imported key material
   * C. Make an GenerateDataKey API call that returns a plaintext key and an encrypted copy of a data key. Use a plaintext key to encrypt the data
   * D. Make an GenerateDataKeyWithoutPlaintext API call that returns an encrypted copy of a data key. Use an encrypted key to encrypt the data
* [Answer](https://i.imgur.com/RSEMeBN.png)
199) A Development team would like to migrate their existing application code from a GitHub repository to AWS CodeCommit.
What needs to be created before they can migrate a cloned repository to CodeCommit over HTTPS?
   * A. A GitHub secure authentication token
   * B. A public and private SSH key file
   * C. A set of Git credentials generated from IAM
   * D. An Amazon EC2 IAM role with CodeCommit permissions
* [Answer](https://i.imgur.com/j642DKN.png)
200) A Developer is writing a REST service that will add items to a shopping list. The service is built on Amazon API Gateway with AWS Lambda integrations. The shopping list items are send as query string parameters in the method request.
How should the Developer convert the query string parameters to arguments for the Lambda function?
   * A. Enable request validation
   * B. Include the Amazon Resource Name (ARN) of the Lambda function
   * C. Change the integration type
   * D. Create a mapping template 
* [Answer](https://i.imgur.com/FIhTNMj.png)
201) When developing an AWS Lambda function that processes Amazon Kinesis Data Streams, Administrators within the company must receive a notice that includes the processed data.
How should the Developer write the function to send processed data to the Administrators?
   * A. Separate the Lambda handler from the core logic
   * B. Use Amazon CloudWatch Events to send the processed data
   * C. Publish the processed data to an Amazon SNS topic
   * D. Push the processed data to Amazon SQS
* [Answer](https://i.imgur.com/OWID8E7.png)
202) A Developer is storing documents in Amazon S3 that will require encryption at rest. The encryption keys must be rotated annually, at least.
What is the easiest way to achieve this?
   * A. Encrypt the data before sending it to Amazon S3
   * B. Import a custom key into AWS KMS with annual rotation enabled
   * C. Use AWS KMS with automatic key rotation
   * D. Export a key from AWS KMS to encrypt the data
* [Answer](https://i.imgur.com/dg41Ael.png)
203) A company is creating a REST service using an Amazon API Gateway with AWS Lambda integration. The service run different versions for testing purposes.
What would be the BEST way to accomplish this?
   * A. Use an x-Version header to denote which version is being called and pass that header to the Lambda function(s)
   * B. Create an API Gateway Lambda authorizer to route API clients to the correct API version
   * C. Create an API Gateway resource policy to isolate versions and provide context to the Lambda function(s)
   * D. Deploy the API versions as unique stages with unique endpoints and use stage variables to provide further context
* [Answer](https://i.imgur.com/ztHTKdD.png)
204) A company wants to implement authentication for its new REST service using Amazon API Gateway. To authenticate the calls, each request must include HTTP headers with a client ID and user ID. These credentials must be compared to authentication data in an Amazon DynamoDB table.
What MUST the company do to implement this authentication in API Gateway?
   * A. Implement an AWS Lambda authorizer that references the DynamoDB authentication table
   * B. Create a model that requires the credentials, then grant API Gateway access to the authentication table
   * C. Modify the integration requests to require the credentials, then grant API Gateway access to the authentication table
   * D. Implement an Amazon Cognito authorizer that references the DynamoDB authentication table
* [Answer](https://i.imgur.com/DZJ1wbQ.png) error
205) An Amazon RDS database instance is used by many applications to look up historical data. The query rate is relatively constant. When the historical data is updated each day, the resulting write traffic slows the read query performance and affects all application users.
What can be done to eliminate the performance impact on application users?
   * A. Make sure Amazon RDS is Multi-AZ so it can better absorb increased traffic.
   * B. Create an RDS Read Replica and direct all read traffic to the replica.
   * C. Implement Amazon ElastiCache in front of Amazon RDS to buffer the write traffic.
   * D. Use Amazon DynamoDB instead of Amazon RDS to buffer the read traffic. 
* [Answer](https://i.imgur.com/kpzyhsW.png)
206) Company C is currently hosting their corporate site in an Amazon S3 bucket with Static Website Hosting enabled. Currently, when visitors go to http://www.companyc.com the index.html page is returned. Company C now would like a new page welcome.html to be returned when a visitor enters http://www.companyc.com in the browser.
Which of the following steps will allow Company C to meet this requirement? (**Choose two**.)
   * A. Upload an html page named welcome.html to their S3 bucket
   * B. Create a welcome subfolder in their S3 bucket
   * C. Set the Index Document property to welcome.html
   * D. Move the index.html page to a welcome subfolder
   * E. Set the Error Document property to welcome.html
* [Answer](https://i.imgur.com/oh64RCN.png)
207) What type of block cipher does Amazon S3 offer for server side encryption?
   * A. Triple DES
   * B. Advanced Encryption Standard
   * C. Blowfish
   * D. RC5
* [Answer](https://i.imgur.com/HuSzovZ.png)
208) If an application is storing hourly log files from thousands of instances from a high traffic web site, which naming scheme would give optimal performance on S3?
   * A. Sequential
   * B. instanceID_log-HH-DD-MM-YYYY
   * C. instanceID_log-YYYY-MM-DD-HH
   * D. HH-DD-MM-YYYY-log_instanceID
   * E. YYYY-MM-DD-HH-log_instanceID
* [Answer](https://i.imgur.com/FstiVPz.png)
209) Which of the following statements about SQS is true?
   * A. Messages will be delivered exactly once and messages will be delivered in First in, First out order
   * B. Messages will be delivered exactly once and message delivery order is indeterminate
   * C. Messages will be delivered one or more times and messages will be delivered in First in, First out order
   * D. Messages will be delivered one or more times and message delivery order is indeterminate
* [Answer](https://i.imgur.com/U6BzJgm.png)
210) A corporate web application is deployed within an Amazon VPC, and is connected to the corporate data center via IPSec VPN. The application must authenticate against the on-premise LDAP server. Once authenticated, logged-in users can only access an S3 keyspace specific to the user.
Which two approaches can satisfy the objectives? (**Choose two**.)
   * A. The application authenticates against LDAP. The application then calls the IAM Security Service to login to IAM using the LDAP credentials. The application can use the IAM temporary credentials to access the appropriate S3 bucket.
   * B. The application authenticates against LDAP, and retrieves the name of an IAM role associated with the user. The application then calls the IAM Security Token Service to assume that IAM Role. The application can use the temporary credentials to access the appropriate S3 bucket.
   * C. The application authenticates against IAM Security Token Service using the LDAP credentials. The application uses those temporary AWS security credentials to access the appropriate S3 bucket.
   * D. Develop an identity broker which authenticates against LDAP, and then calls IAM Security Token Service to get IAM federated user credentials. The application calls the identity broker to get IAM federated user credentials with access to the appropriate S3 bucket.
   * E. Develop an identity broker which authenticates against IAM Security Token Service to assume an IAM Role to get temporary AWS security credentials. The application calls the identity broker to get AWS
* [Answer](https://i.imgur.com/iXn2USc.png) error
211) Company B provides an online image recognition service and utilizes SQS to decouple system components for scalability The SQS consumers poll the imaging queue as often as possible to keep end-to-end throughput as high as possible. However, Company B is realizing that polling in tight loops is burning CPU cycles and increasing costs with empty responses.
How can Company B reduce the number of empty responses?
   * A. Set the imaging queue visibility Timeout attribute to 20 seconds
   * B. Set the Imaging queue ReceiveMessageWaitTimeSeconds attribute to 20 seconds
   * C. Set the imaging queue MessageRetentionPeriod attribute to 20 seconds
   * D. Set the DelaySeconds parameter of a message to 20 seconds
* [Answer](https://i.imgur.com/VrMad2z.png) error
212) An Amazon S3 bucket, "myawsbucket" is configured with website hosting in Tokyo region, what is the region- specific website endpoint?
   * A. www.myawsbucket.ap-northeast-1.amazonaws.com
   * B. myawsbucket.s3-website-ap-northeast-1.amazonawscom
   * C. myawsbucket.amazonaws.com
   * D. myawsbucket.tokyo.amazonaws.com
* [Answer](https://i.imgur.com/DIAvApg.png)
