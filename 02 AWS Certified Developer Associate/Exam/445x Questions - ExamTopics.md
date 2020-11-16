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
