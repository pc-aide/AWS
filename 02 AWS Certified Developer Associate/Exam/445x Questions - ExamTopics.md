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
100) A web application is designed to allow new users to create accounts using their email addresses. The application will store attributes for each user, and is expecting millions of user to sign up.<br/>What should the Developer implement to achieve the design goals?
    * A. Amazon Cognito user pools
    * B. AWS Mobile Hub user data storage
    * C. Amazon Cognito Sync
    * D. AWS Mobile Hub cloud logic
* [Answer](https://i.ibb.co/0tw5kmh/image.png)
101) A company needs a new REST API that can return information about the contents of an Amazon S3 bucket, such as a count of the objects stored in it. The company has decided that the new API should be written as a microservice using AWS Lambda and Amazon API Gateway.<br/>How should the Developer ensure that the microservice has the necessary access to the Amazon S3 bucket, while adhering to security best practices?
    * A. Create an IAM user that has permissions to access the Amazon S3 bucket, and store the IAM user credentials in the Lambda function source code.
    * B. Create an IAM role that has permissions to access the Amazon S3 bucket and assign it to the Lambda function as its execution role.
    * C. Create an Amazon S3 bucket policy that specifies the Lambda service as its principal and assign it to the Amazon S3 bucket.
    * D. Create an IAM role, attach the AmazonS3FullAccess managed policy to it, and assign the role to the Lambda function as its execution role.
* [Answer](https://i.ibb.co/GTZ0mKh/image.png) error
102) An application is running on an EC2 instance. The Developer wants to store an application metric in Amazon CloudWatch.<br/>What is the best practice for implementing this requirement?
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
* [Answer]()
