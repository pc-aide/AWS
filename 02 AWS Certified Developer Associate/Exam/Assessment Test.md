# Assessment Test

## Questions
1. You have an application running on Amazon EC2 that
needs read-only access to several AWS services. What is the best way to grant that application permissions only to a specific set of resources within your account?
    * A. Use API credentials derived based on the AWS account.
    * B. Launch the EC2 instance into an AWS IAM role
and attach the ReadOnlyAccess IAM-managed policy.
    * C. Declare the necessary permissions as statements in the AWS SDK configuration file on
the EC2 instance.
    * D. Launch the EC2 instance into an IAM role with custom IAM policies for the permissions.
2. You have deployed a new application in the US West (Oregon) Region. However, you have
accidentally deployed an Amazon Polly lexicon needed for your application in EU (London).
How can you use your lexicon to synthesize speech while minimizing the changes to your
application code and reducing cost?
    * A. Point your SDK client to the EU (London) for all requests to Amazon Polly, but to US
West (Oregon) for all other API calls.
    * B. No action needed; the data is automatically available from all Regions.
    * C. Upload a copy of the lexicon to US West (Oregon).
    * D. Move the rest of the application resources to EU (London).
3. When you’re placing subnets for a specific Amazon VPC,
you can place the subnets in which of the following?
    * A. In any Availability Zone within the Region for the Amazon VPC
    * B. In any Availability Zone in any Region
    * C. In any AWS edge location
    * D. In any specific AWS data center
4. You have identified two Amazon EC2 instances in your
account that appear to have the same private IP address. What could be the cause?
    * A. These instances are in different Amazon VPCs.
    * B. The instances are in different subnets
    * C. The instances have different network ACLs.
    * D. The instances have different security groups.
5. You have a workload that requires 15,000 consistent IOPS for data that must be durable.
What combination of the following do you need? (**Select TWO**.)
    * A. Use an Amazon EBS optimized instance.
    * B. Use an instance store.
    * C. Use a Provisioned IOPS SSD volume.
    * D. Use a previous-generation EBS volume.
6. Your company stores critical documents in Amazon S3,
but it wants to minimize cost. Most documents are used actively for only about one month
and then used much less frequently after that. However, all data needs to be available
within minutes when requested. How can you meet these requirements?
    * A. Migrate the data to Amazon S3 RRS after 30 days.
    * B. Migrate the data to Amazon S3 Glacier after 30 days.
    * C. Migrate the data to Amazon S3 Standard – IA after 30 days.
    * D. Turn on versioning and then migrate the older version to Amazon S3 Glacier.
7. You are migrating your company’s applications and data from on-premises to the AWS
Cloud. You have performed a data inventory and discovered that you will need to transfer
about 2 PB of data to AWS. Which migration option will be the best choice for your com-
pany with minimal cost and shortest time?
    * A. AWS Snowball
    * B. AWS Snowmobile
    * C. Upload files directly to AWS over the internet using Amazon S3 Transfer Acceleration.
    * D. Amazon Kinesis Data Firehose
8. You are changing your application to take advantage of the elasticity and cost benefits provided by AWS Auto Scaling. To do this, you must move session state information from the
individual Amazon EC2 instances. Which of the following AWS Cloud services is best suited as an alternative for storing session state information?
    * A. Amazon DynamoDB
    * B. Amazon Redshift
    * C. AWS Storage Gateway
    * D. Amazon Kinesis
9. Your company’s senior management wants to query several data stores to obtain a “big pic-
ture” view of the business. The amount of data contained within the data stores is at least
2 TB in size. Which of the following is the best AWS service to deliver results to senior
management?
    * A. Amazon EBS
    * B. Amazon S3
    * C. Amazon RDS
    * D. Amazon Redshift
10. our ecommerce application provides daily and ad hoc reporting to various business
units on customer purchases. These operations result in a high level of read traffic to your
MySQL Amazon RDS instance. What can you do to
scale up read traffic without impacting your database’s performance?
    * A. Increase the allocated storage for the Amazon RDS instance.
    * B. Modify the Amazon RDS instance to be a Multi-AZ deployment.
    * C. Create a read replica for an Amazon RDS instance.
    * D. Change the Amazon RDS instance DB engine version.
11. Your company has refactored their application to use NoSQL instead of SQL. They would
like to use a managed service for running the new NoSQL database. Which AWS service
should you recommend?
    * A. Amazon RDS
    * B. Amazon EC2
    * C. Amazon DynamoDB
    * D. Amazon Redshift
12. A company is currently using Amazon RDS;
however, they are retiring a database that is currently running. They have automatic back-
ups enabled on the database. They want to make sure that they retain the last backup
before deleting the Amazon RDS database. As the lead developer on the project, what
should you do?
    * A. Delete the database. Amazon RDS automatic backups are already enabled
    * B. Create a manual snapshot before deleting the database.
    * C. Use the AWS DMS to back up the database.
    * D. SSH into the Amazon RDS database and perform a SQL dump.
13. When using Amazon Redshift, which node do you use to run your SQL queries?
    * A. Compute node
    * B. Cluster node
    * C. Master node
    * D. Leader node
14. Your company is building a recommendation feature for their application. They would like
to use an AWS managed graph database. Which service should you recommend?
    * A. Amazon RDS
    * B. Amazon Neptune
    * C. Amazon ElastiCache
    * D. Amazon Redshift
15. You have an Amazon DynamoDB table that has a partition key and a sort key. However, a
business analyst on your team wants to be able to query the DynamoDB table with a differ-
ent partition key. What should you do?
    * A. Create a local secondary index.
    * B. Create a global secondary index.
    * C. Create a new DynamoDB table.
    * D. Advise the business analyst that this is not possible.
16. An application is using Amazon DynamoDB. Recently, a developer on your team has
noticed that occasionally the application does not return the most up-to-date data after a
read from the database. How can you solve this issue?
    * A. Increase the number of RCUs for the table
    * B. Increase the number of WCUs for the table
    * C. Refactor the application to use a SQL database.
    * D. Configure the application to perform a strongly consistent read.
17. A developer on your team would like to test a new idea and requires a NoSQL database.
Your current applications are using Amazon DynamoDB. What should you recommend?
    * A. Create a new table inside DynamoDB.
    * B. Use DynamoDB local
    * C. Use another NoSQL database on-premises.
    * D. Create an Amazon EC2 instance, and install a
NoSQL database.
18. The AWS Encryption SDK provides an encryption library that integrates with AWS KMS as a master key provider. Which of the following opera-
tions does the AWS Encryption SDK perform to build on the AWS SDKs?
    * A. Generates, encrypts, and decrypts data keys
    * B. Uses the data keys to encrypt and decrypt your raw data
    * C. Stores the encrypted data keys with the corresponding encrypted data in a single
object
    * D. All of the above
19. Of all the cryptographic algorithms that the AWS Encryption SDK supports, which one is
the default algorithm
    * A. AES-256
    * B. AES-192
    * C. AES-128
    * D. SSH-256
20. Amazon EBS volumes are encrypted by default.
    * A. True
    * B. False
21. Which of the following cannot be retained when deleting an AWS Elastic Beanstalk
environment?
    * A. Source code from the Git repository
    * B. Data from the automatic backups of an Amazon RDS instance
    * C. Packaged code from the source bundle stored in an Amazon S3 bucket
    * D. Data from the snapshot of an Amazon RDS instance
22. Which of the following is not part of the AWS Elastic Beanstalk functionality?
    * A. Notify the account user of language runtime platform changes
    * B. Display events per environment
    * C. Show instance statuses per environment
    * D. Perform automatic changes to AWS IAM policies
23. What happens to AWS CodePipeline revisions that, upon reaching a manual approval gate,
are rejected?
    * A. The pipeline continues.
    * B. A notification is sent to the account administrator.
    * C. The revision is treated as failed.
    * D. The pipeline creates a revision clone and continues
24. Which of the following is an invalid strategy for migrating data to AWS CodeCommit?
    * A. Incrementally committing files from a large repository
    * B. Syncing the files from Amazon S3 using the sync
AWS CLI command
    * C. Cloning an existing repository, updating the remote, and pushing
    * D. Manually creating files in the AWS Management Console
25. You have an AWS CodeBuild task in your pipeline that requires large binary files that do
not frequently change. What would be the best way to include these files in your build?
    * A. Store the files in your source code repository. They will be passed in as part of the
revision.
    * B. Store the files in an Amazon S3 bucket and copy
them during the build.
    * C. Create a custom build container that includes the files.
    * D. It is not possible to include files above a certain size.
26. When you update an AWS::S3::Bucket resource, what is the expected behavior if the Name
property is updated?
    * A. The resource is updated with no interruption.
    * B. The resource is updated with some interruption.
    * C. The resource is replaced.
    * D. The resource is deleted.
27. What is the preferred method for updating resources created by AWS CloudFormation?
    * A. Updating the resource directly in the AWS Management Console
    * B. Submitting an updated template to AWS CloudFormation to modify the stack
    * C. Updating the resource using the AWS CLI
    * D. Updating the resource using an AWS SDK
28. When does the AWS OpsWorks Stacks configure lifecycle event run?
    * A. On individual instances immediately when they are first created
    * B. On individual instances after a deploy lifecycle event
    * C. On all instances in a stack when a single instance comes online or goes offline
    * D. On all instances in a stack after a deploy lifecycle event
29. Which non-Amazon EC2 AWS resources can AWS
OpsWorks Stacks manage? (**Select THREE**.)
    * A. Elastic IP addresses
    * B. Amazon EBS volumes
    * C. Amazon RDS database instances
    * D. Amazon ElastiCache clusters
    * E. Amazon Redshift data warehouses
30. Which AWS Cloud service can Simple Active Directory (Simple AD) use to authenticate
users?
    * A. Amazon WorkDocs
    * B. Amazon Cognito
    * C. Amazon EC2
    * D. Amazon S3
31. What is the best application of Amazon Cognito?
    * A. Use instead of Active Directory for AWS IAM users.
    * B. Provide authentication to third-party web applications.
    * C. Use as an Amazon Aurora database.
    * D. Use to access objects in an Amazon S3 bucket.
32. You manage a sales tracking system in which point-of-sale devices send transactions of this
form:
````json
{"date":"2017-01-30", "amount":100.20, "product_id": "1012", "region":
"WA", "customer_id": "3382"}
````
You need to generate two real-time reports. The first reports on the total sales per day for
each customer. The second reports on the total sales per day for each product. Which AWS
offerings and services can you use to generate these real-time reports?
   * A. Ingest the data through Amazon Kinesis Data Streams. Use Amazon Kinesis Data Analyt-
ics to query for sales per day for each product and sales per day for each customer using
SQL queries. Feed the result into two new streams in Amazon Kinesis Data Firehose.
   * B. Ingest the data through Kinesis Data Streams. Use Kinesis Data Firehose to query for
sales per day for each product and sales per day for each customer with SQL queries.
Feed the result into two new streams in Kinesis Data Firehose.
   * C. Ingest the data through Kinesis Data Analytics. Use Kinesis Data Streams to query for
sales per day for each product and sales per day for each customer with SQL queries. Feed
the result into two new streams in Kinesis Data Firehose.
   * D. Ingest the data in Amazon SQS. Use Kinesis Data
Firehose to query for sales per day for each product and sales per day for each
customer with SQL queries. Feed the result into two new streams in Kinesis Data
Firehose.


33. You design an application for selling toys online. Every time a customer orders a toy, you
want to add an item into the orders table in Amazon DynamoDB and send an email to the
customer acknowledging their order. The solution should be performant and cost-effective.
How can you trigger this email?
    * A. Use an Amazon SQS queue.
    * B. Schedule an AWS Lambda function to check for changes to the orders table every minute.
    * C. Schedule an Lambda function to check for changes to the orders table every second.
    * D. Use Amazon DynamoDB Streams.

34. A company would like to use Amazon DynamoDB. They want to set up a NoSQL-style
trigger. Is this something that can be accomplished? If so, how?
    * A. No. This cannot be done with DynamoDB and NoSQL.
    * B. Yes, but not with AWS Lambda.
    * C. No. DynamoDB is not a supported event source for Lambda.
    * D. Yes. You can use Amazon DynamoDB Streams and poll them with Lambda.
35. A company wants to access the infrastructure on which AWS Lambda runs. Is this possible?
    * A. No. Lambda is a managed service and runs the necessary infrastructure on your
behalf.
    * B. Yes. They can access the infrastructure and make changes to the underlying OS.
    * C. Yes. They need to open a support ticket.
    * D. Yes, but they need to contact their Solutions Architect to provide access to the environ-
ment.
36. Using the smallest amount of memory possible for an AWS Lambda function, currently
128 MB, will result in the lowest bill.
    * A. True. Lambda bills based on the total memory allocated.
    * B. False. Lambda has a flat rate—memory allocation is not important for billing, only
performance.
    * C. False. Lambda bills based on memory plus the number of times that you trigger the
function.
    * D. False. Lambda bills based on memory, the amount of compute time spent on a function
in 100-ms increments, and the number of times that you execute or trigger a function.
37. Which Amazon services can you use for caching? (**Select TWO**.)
    * A. AWS CloudFormation
    * B. Amazon S3
    * C. Amazon CloudFront
    * D. Amazon ElastiCache
38. Which Amazon API Gateway feature enables you to create a separate path that can be help-
ful in creating a development endpoint and a production endpoint?
    * A. Authorizers
    * B. API keys
    * C. Stages
    * D. CORS
39. Which of the following methods does Amazon API Gateway support?
    * A. GET
    * B. POST
    * C. OPTIONS
    * D. All of the above
40. Which authorization mechanisms does Amazon API Gateway support?
    * A. AWS IAM policies
    * B. AWS Lambda custom authorizers
    * C. Amazon Cognito user pools
    * D. All of the above
41. Which tool can you use to develop and test AWS Lambda functions locally?
    * A. AWS SAM
    * B. AWS SAM CLI
    * C. AWS CloudFormation
    * D. None of the above
42. Which serverless AWS service can you use to store user session state?
    * A. Amazon EC2
    * B. Amazon ElastiCache
    * C. AWS Elastic Beanstalk
    * D. Amazon DynamoDB
43. Which AWS service can you use to store user profile information?
    * A. Amazon CloudFront
    * B. Amazon Cognito
    * C. Amazon Kinesis
    * D. AWS Lambda
44. Which of the following objects are good candidates to store in a cache? (**Select THREE**.)
    * A. Session state
    * B. Shopping cart
    * C. Product catalog
    * D. Bank account balance
45. Which of the following cache engines does Amazon ElastiCache support? (**Select TWO**.)
    * A. Redis
    * B. MySQL
    * C. Couchbase
    * D. Memcached
46. How can you aggregate Amazon CloudWatch metrics across Regions?
    * A. CloudWatch does not aggregate data across Regions.
    * B. This is enabled by default.
    * C. Send the metric data from other Regions to Amazon S3 for retrieval by CloudWatch.
    * D. Stream the metric data to Amazon Kinesis, and retrieve it using an AWS Lambda
function.
47. Why would an Amazon CloudWatch alarm report as INSUFFICIENT_DATA instead of OK or
ALARM? (**Select THREE**.)
    * A. The alarm was just created.
    * B. The metric is not available.
    * C. There is an AWS IAM permission preventing the
metric from receiving data.
    * D. Not enough data is available for the metric to determine the alarm state.
    * E. The alarm period is missing.
48. You were asked to develop an administrative web application that consumes low through-
put and rarely receives high traffic. Which of the following instance type families will be
the most optimized choice?
    * A. Memory optimized
    * B. Compute optimized
    * C. General purpose
    * D. Accelerated computing
49. Which of the following AWS Cost Management Tools can you use to view your costs and
find ways to take advantage of elasticity?
    * A. AWS Cost Explorer
    * B. AWS Trusted Advisor
    * C. Amazon CloudWatch
    * D. Amazon EC2 Auto Scaling
50. Because cloud resources are easier to deploy and they incur usage-based costs, your organi-
zation is setting up good governance rules to manage costs. They are currently focusing on
controlling and restricting Amazon EC2 instance deploy-
ments. Which of the following is an effective recommendation?
    * A. Seek approval from Cost Engineering teams before deploying any EC2 instances.
    * B. Use AWS IAM policies to enable engineers to
deploy EC2 instances only when specific mandatory tags are used.
    * C. Review Amazon CloudWatch metrics to optimize the resource utilization.
    * D. Use AWS Cost Explorer usage and forecasting reports.
51. Because your applications are showing a consistent steady-state compute usage, you have
decided to purchase Amazon EC2 Reserved Instances to
gain significant pricing discounts. Which of the following is not the best purchase option?
    * A. All Upfront
    * B. Partial Upfront
    * C. No Upfront
    * D. Pay-as-you-go
52. Your application processes transaction-heavy and IOPS-intensive database workloads. You
need to choose the right Amazon EBS volume so that applica-
tion performance is not affected. Which of the following options would you suggest?
    * A. HDD-backed storage (st1)
    * B. SSD-backed storage (io1)
    * C. Amazon S3 Intelligent Tier class storage
    * D. Cold HDD-backed storage (sc1)
53. A legacy financial institution is planning for a huge technical upgrade and planning to go
global. The architecture depends heavily on using caching solutions. Which one of the fol-
lowing services does not fit into the caching solutions?
    * A. Amazon ElastiCache for Redis
    * B. Amazon ElastiCache for Memcached
    * C. Amazon DynamoDB Accelerator
    * D. Amazon EC2 memory-optimized
54. Which of the following characteristics separates Amazon DynamoDB from the Amazon RDS design?
    * A. Incurs the performance costs of an ACID-compliant transaction system
    * B. Normalizes data and stores it on multiple tables
    * C. Keeps related data together
    * D. May require expensive joins
55. Which of the following partition key choices is an inefficient design that leads to poor dis-
tribution of the data in an Amazon DynamoDB table?
    * A. User ID, where the application has many users
    * B. Device ID, where each device accesses data at relatively similar intervals
    * C. Status code, where there are only a few possible status codes
    * D. Session ID, where the user session remains distinct
56. You are planning to build serverless backends by using AWS Lambda to handle web,
mobile, IoT, and third-party API requests. Which of the following are
the main benefits in opting for a serverless architecture in this scenario? (**Select THREE**.)
    * A. No need to manage servers
    * B. No need to ensure application fault tolerance and fleet management
    * C. No charge for idle capacity
    * D. Flexible maintenance schedules
    * E. Powered for high complex processing
57. Your enterprise infrastructure has recently migrated to the AWS Cloud. You are now trying
to optimize the storage solutions. Which of the following are the appropriate storage man-
agement tools that you can use to review and analyze the storage classes and access patterns
usage to help reduce costs? (**Select TWO**.)
    * A. Amazon S3 analytics
    * B. Cost allocation Amazon S3 bucket tags
    * C. Amazon S3 Transfer Acceleration
    * D. Amazon Route 53
    * E. AWS Budgets
* [Answers]() 
* Score: /57
