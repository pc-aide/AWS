# Quiz 02 - 65x questions

## Questions
1) While troubleshooting, a developer realized that the Amazon EC2 instance is unable to connect to the Internet using the Internet Gateway.<br/>Which conditions should be met for Internet connectivity to be established? (**Select two**)
      * A. The instance's subnet is associated with multiple route tables with conflicting configurations
      * B. The instance's subnet is not associated with any route table
      * C. The route table in the instance's subnet should have a route to an Internet Gateway
      * D. The subnet has been configured to be Public & has no access to the internet
      * E. The network ACLs assocaited with the subnet must have rules to allow inbound & outbound traffic
2) Other than the Resources section, which of the following sections in a SAM Template is mandatory?
      * A. Globals
      * B. Mappings
      * C. Transform
      * D. Parameters
3) You are a cloud architect in Silicon Valley. Many companies in this area have mobile apps that capture and send data to Amazon Kinesis Data Streams. They have been getting a ProvisionedThroughputExceededException exception. You have been contacted to help and upon careful analysis, you are seeing that messages are being sent one by one while being sent at a high rate.<br/>Which of the following options will help with the exception while keeping costs at a minimum?
      * A. Batch messages
      * B. Decrease the Stream retention duration
      * C. Increase the number of shards
      * D. Use Exponential Backoff
4) A business has their test environment built on Amazon EC2 configured on General purpose SSD volume.<br/>At which gp2 volume size will their test environment hit the max IOPS?
      * A. 16 TiB
      * B. 2.7 TiB
      * C. 5.3 TiB
      * D. 10.6 TiB
5) A media publishing company is using Amazon EC2 instances for running their business-critical applications. Their IT team is looking at reserving capacity apart from savings plans for the critical instances.<br/>As a Developer Associate, which of the following reserved instance types you would select to provide capacity reservations?
      * A. Zonal Reserved Instances
      * B. Regional Reserved Instances
      * C. Neither Regional Reserved Instances nor Zonal Reserved Instances
      * D. Both Regional Reserved Instances & Zonal Reserved Instances
6) A Developer is configuring Amazon EC2 Auto Scaling group to scale dynamically.<br/>Which metric below is NOT part of Target Tracking Scaling Policy?
      * A. ASGAverageCPUUtilization
      * B. ApproximateNumberOfMessagesVisible
      * C. ASGAverageNetworkOUt
      * D. ALBRequestContPerTarget
7) The development team at a retail company is gearing up for the upcoming Thanksgiving sale and wants to make sure that the application's serverless backend running via Lambda functions do not hit concurrency limits as a result of the surge in traffic.<br/>As a Developer Associate, which of the following solutions would you recommend to address this use-case?
      * A. Add an ALB in front of the Lambda functions
      * B. Configure Application Auto Scaling to manage Lambda provisioned concurrency on a schedule
      * C. No need to make any special provisions as Lambda is automatically scalable because of its serverless nature
      * D. Configure Application Auto Scaling to manage Lambda reserved concurency on a schedule
8) You are an administrator for a video-on-demand web application where content creators upload videos directly into S3. Recent support requests from customers state that uploading video files near 500GB size causes the website to break. After doing some investigation you find the following error: 'Your proposed upload exceeds the maximum allowed size'.<br/>What must you do to solve this error?
      * A. You need to place a service limit request increase with AWS
      * B. The maximum file size is 5 GB
      * C. You need to use multi-part upload for large files
      * D. Your IAM permissions are incorrect
9) The development team at a multi-national retail company wants to support trusted third-party authenticated users from the supplier organizations to create and update records in specific DynamoDB tables in the company's AWS account.<br/>As a Developer Associate, which of the following solutions would you suggest for the given use-case?
      * A. Use Cognito Identity pools to enable trusted third-party authenticated users to access DynamoDB
      * B. Create a new IAM group in the company's AWS account for each of the third-party authenticated users from the supplier organizations. The users can then use the IAM group credentials to access DynamoDB
      * C. Create a new IAM user in the company's AWS account for each of the third-party authenticated users from the supplier organizations. The users can then use the IAM user credentials to access DynamoDB
      * D. Use Cognito User pools to enable trusted third-party authenticated users to access DynamoDB
10) An Auto Scaling group has a maximum capacity of 3, a current capacity of 2, and a scaling policy that adds 3 instances.<br/>When executing this scaling policy, what is the expected outcome?
      * A. Amazon EC2 Auto Scaling does not add any instances to the group, but suggests changing the scaling the scaling policy to add one instance
      * B. Amazon EC2 Auto Scaling adds 3 instances to the group
      * C. Amazon EC2 Auto Scaling adds only 1 instance to the group
      * D. Amazon EC2 Auto Scaling adds 3 instances to the group & scales down 2 of those instances eventually
11) A developer is looking at establishing access control for an API that connects to a Lambda function downstream.<br/>Which of the following represents a mechanism that CANNOT be used for authenticating with the API Gateway?
      * A. Cognito User Pools
      * B. AWS Security Token Service (STS)
      * C. Lambda Authorizer
      * D. Standard AWS IAM roles & policies
12) You create an Auto Scaling group to work with an Application Load Balancer. The scaling group is configured with a minimum size value of 5, a maximum value of 20, and the desired capacity value of 10. One of the 10 EC2 instances has been reported as unhealthy.<br/>Which of the following actions will take place?
      * A. The ASG will keep the instance running & re-start the application
      * B. The ASG will detach the EC2 instance from the group, & leave it running
      * C. The ASG will format the root EBS drive on the EC2 instance & run the User Data again
      * D. The ASG will termnate the EC2 Instance
13) You have launched several AWS Lambda functions written in Java. A new requirement was given that over 1MB of data should be passed to the functions and should be encrypted and decrypted at runtime.<br/>Which of the following methods is suitable to address the given use-case?
      * A. Use Envelope Encryption & reference the data as file within the code
      * B. Use KMS Encryption & store as environment variable
      * C. Use Envelope Encryption & store as environment variable
      * D. Use KMS direct encryption & store as file
14) A development team has configured their Amazon EC2 instances for Auto Scaling. A Developer during routine checks has realized that only basic monitoring is active, as opposed to detailed monitoring.<br/>Which of the following represents the best root-cause behind the issue?
      * A. The default configuration was Auto Scaling was not set
      * B. SDK was used to create the launch configuration
      * C. AWS Management Console might have been used to create the launch configuration
      * D. AWS CLI used to create the launch configuration
15) A company that specializes in cloud communications platform as a service allows software developers to programmatically use their services to send and receive text messages. The initial platform did not have a scalable architecture as all components were hosted on one server and should be redesigned for high availability and scalability.<br/>Which of the following options can be used to implement the new architecture? (**select two**)
      * A. SES + S3
      * B. CloudWatch + CloudFront
      * C. ALB + ECS
      * D. EBS + RDS
      * E. API Gateway + Lambda
16) A cyber forensics application, running behind an ALB, wants to analyze patterns for the client IPs.<br/>Which of the following headers can be used for this requirement?
      * A. X-Forwarded-IP
      * B. X-Forwarded-For
      * C. X-Forwarded-Proto
      * D. X-Forwarded-Port
17) A diagnostic lab stores its data on DynamoDB. The lab wants to backup a particular DynamoDB table data on Amazon S3, so it can download the S3 backup locally for some operational use.<br/>Which of the following options is not feasible?
      * A. Use the DynamoDB on-demand backup capability to write to Amazon S3 & download locally
      * B. Use Hive with Amazon EMR to export your data to an S3 bucket & download locally
      * C. Use AWS Data Pipeline to export your table to an S3 bucket in the account of your choice & download locally
      * D. Use AWS Glue to copy your table to Amazon S3 & download locally
18) As an AWS certified developer associate, you are working on an AWS CloudFormation template that will create resources for a company's cloud infrastructure. Your template is composed of three stacks which are Stack-A, Stack-B, and Stack-C. Stack-A will provision a VPC, a security group, and subnets for public web applications that will be referenced in Stack-B and Stack-C.<br/>After running the stacks you decide to delete them, in which order should you do it?
      * A. Stack A, then Stack B, then Stack C
      * B. Stack C then Stack A then Stack B
      * C. Stack B, then Stack C, then Stack A
      * D. Stack A, Stack C then Stack B
19) A company runs its flagship application on a fleet of Amazon EC2 instances. After misplacing a couple of private keys from the SSH key pairs, they have decided to re-use their SSH key pairs for the different instances across AWS Regions.<br/>As a Developer Associate, which of the following would you recommend to address this use-case?
      * A. Encrypt the private SSH key & store it in the S3 bucket to be accessed from any AWS Region
      * B. Generate a plublic SSH key from a private SSH key. Then, import the key into each of your AWS Regions
      * C. Store the public & private SSH key pari in AWS Trusted Advisor & access it across AWS Regions
      * D. It is not possible to reuse SSH key pairs across AWS Regions
20) A new recruit is trying to configure what an Amazon EC2 should do when it interrupts a Spot Instance.<br/>Which of the below CANNOT be configured as an interruption behavior?
      * A. Hibernate the Sport Instance
      * B. Terminate the Sport Instance
      * C. Reboot the Spot Instance
      * D. Stop the Spot Instance
21) As an AWS Certified Developer Associate, you are writing a CloudFormation template in YAML. The template consists of an EC2 instance creation and one RDS resource. Once your resources are created you would like to output the connection endpoint for the RDS database.<br/>Which intrinsic function returns the value needed?
      * A. `!Sub`
      * B. `!Ref`
      * C. `!GetAtt`
      * D. `!FindInMap`
22) You are a developer handling a deployment service that automates application deployments to Amazon EC2 instances. Most of the deployments consist of code, but sometimes web and configuration files. One of your deployments failed and was rolled back by AWS CodeDeploy to the last known good application revision.<br/>During rollback which of the following instances did AWS CodeDeploy deploy first to?
      * A. You can't rollback a CodeDeploy deployment
      * B. To the new instances
      * C. To the non-failed instances
      * D. To the failed instances
23) Your team lead has asked you to learn AWS CloudFormation to create a collection of related AWS resources and provision them in an orderly fashion. You decide to provide AWS-specific parameter types to catch invalid values.<br/>When specifying parameters which of the following is not a valid Parameter type?
      * A. CommaDelimitedList
      * B. AWS::EC2::KeyPair::KeyName
      * C. String
      * D. DependentParameter
24) As an AWS Certified Developer Associate, you have been hired to consult with a company that uses the NoSQL database for mobile applications. The developers are using DynamoDB to perform operations such as GetItem but are limited in knowledge. They would like to be more efficient with retrieving some attributes rather than all.<br/>Which of the following recommendations would you provide?
      * A. Use the `--query` parameter
      * B. Use a `Scan`
      * C. Specify a `ProjectionExpression`
      * D. Use a `FilterExpression
25) The technology team at an investment bank uses DynamoDB to facilitate high-frequency trading where multiple trades can try and update an item at the same time.<br/>Which of the following actions would make sure that only the last updated value of any item is used in the application?
      * A. Use ConsistentRead = false while doing PutItem operation for any item
      * B. Use ConsistentRead = true while doing GetItem operation for any item
      * C. Use ConsistentRead = true while doing PutItem operation for any item
      * D. Use ConsistentRead = true while doing UpdateItem operation for any item
26) A team lead has asked you to create an AWS CloudFormation template that creates EC2 instances and RDS databases. The template should be reusable by allowing the user to input a parameter value for an Amazon EC2 AMI ID.<br/>Which of the following intrinsic function should you choose to reference the parameter?
      * A. `!Param`
      * B. `!Ref`
      * C. `!GetAtt`
      * D. `!Join`
27) A developer needs to automate software package deployment to both Amazon EC2 instances and virtual servers running on-premises, as part of continuous integration and delivery that the business has adopted.<br/>Which AWS service should he use to accomplish this task?
      * A. AWS CodeDeploy
      * B. AWS EB
      * C. AWS CodePipeline
      * D. AWS CodeBuild
28) You are a development team lead setting permissions for other IAM users with limited permissions. On the AWS Management Console, you created a dev group where new developers will be added, and on your workstation, you configured a developer profile. You would like to test that this user cannot terminate instances.<br/>Which of the following options would you execute?
      * A. Using the CLI, create a dummy EC2 & delete it using another CLI call
      * B. Use the AWS CLI --dry-run option
      * C. Use the AWS CLI --test option 
      * D. Retrieve the plicy using the EC2 metadata service & use the IAM policy simulator
29) A company has AWS Lambda functions where each is invoked by other AWS services such as Amazon Kinesis Data Firehose, Amazon API Gateway, Amazon Simple Storage Service, or Amazon CloudWatch Events. What these Lambda functions have in common is that they process heavy workloads such as big data analysis, large file processing, and statistical computations.<br/>What should you do to improve the performance of your AWS Lambda functions without changing your code?
      * A. Increase the Lambda function timeout
      * B. Increase the RAM assigned to your Lambda function 
      * C. Change your Lambda function runtime to use Golang
      * D. Change the instance type for your Lambda function
30) The development team at an e-commerce company completed the last deployment for their application at a reduced capacity because of the deployment policy. The application took a performance hit because of the traffic spike due to an on-going sale.<br/>Which of the following represents the BEST deployment option for the upcoming application version such that it maintains at least the FULL capacity of the application and MINIMAL impact of failed deployment?
      * A. Deploy the new application version using 'Immutable' deployment policy
      * B. Deploy the new application version using 'Rolling' deployment policy
      * C. Deploy the new application version using 'Rolling wiht additional batch' deployment policy
      * D. Deploy the new application version using 'All at once' deployment policy
31) An application running on EC2 instances processes messages from an SQS queue. However, sometimes the messages are not processed and they end up in errors. These messages need to be isolated for further processing and troubleshooting.<br/>Which of the following options will help achieve this?
      * A. Reduce the VisibilityTimeout
      * B. Implement a DLQ
      * C. Increase the VisibilityTimeout
      * D. Use DeleteMessage
32) A developer while working on Amazon EC2 instances, realized that an instance was not needed and had shut it down. But another instance of the same type automatically got launched in the account.<br/>Which of the following options can attribute the given sequence of actions?
      * A. The user did not have the right permissions to shutdown the instance. User needs root permissions to terminate an instance
      * B. The instance could have been a part of NLB & hence was automatically started
      * C. Instance might be part of ASG & hence re-launched similar instance
      * D. The instance could have been a part of ALB & hence was automatically started
33) You are a developer working on a web application written in Java and would like to use AWS Elastic Beanstalk for deployment because it would handle deployment, capacity provisioning, load balancing, auto-scaling, and application health monitoring. In the past, you connected to your provisioned instances through SSH to issue configuration commands. Now, you would like a configuration mechanism that automatically applies settings for you.<br/>Which of the following options would help do this?
      * A. Deploy a CloudFormatin wrapper
      * B. Use an AWS Lambda hook
      * C. Include config files in .ebextensions/ at the root of your source code
      * D. Use SSM parameter store as an input to your EB Configurations
34) You have created a continuous delivery service model with automated steps using AWS CodePipeline. Your pipeline uses your code, maintained in a CodeCommit repository, AWS CodeBuild, and AWS Elastic Beanstalk to automatically deploy your code every time there is a code change. However, the deployment part to Elastic Beanstalk is taking a very long time due to resolving dependencies on all of your 100 target EC2 instances.<br/>Which of the following actions should you take to improve performance with limited code changes?
      * A. Bundle the dependencies in the source code during the last stage of CodeBuild
      * B. Store the dependencies in S3
      * C. Create a custom platform for EB
      * D. Bundle the dependencies in the source code in CodeCommit
35) A startup has been experimenting with DynamoDB in its new test environment. The development team has discovered that some of the write operations have been overwriting existing items that have the specified primary key. This has messed up their data, leading to data discrepancies.<br/>Which DynamoDB write option should be selected to prevent this kind of overwriting?
      * A. Batch write
      * B. Use Scan operation
      * C. Atomic Counters
      * D. Conditional writes
36) As a senior architect, you are responsible for the development, support, maintenance, and implementation of all database applications written using NoSQL technology. A new project demands a throughput requirement of 10 strongly consistent reads per second of 6KB in size each.<br/>How many read capacity units will you need when configuring your DynamoDB table?
      * A. 60
      * B. 10
      * C. 20
      * D. 30
37) As a Developer Associate, you are responsible for the data management of the AWS Kinesis streams at your company. The security team has mandated stricter security requirements by leveraging mechanisms available with the Kinesis Data Streams service that won't require code changes on your end.<br/>Which of the following features meet the given requirements? (**Select two**)
      * A. SSE-C encryption
      * B. Client-Side Encryption
      * C. KMS encryption for data at rest
      * D. Envelope Encryption
      * E. Encryption in flight with HTTPS endpoint
38) A developer at a university is encrypting a large XML payload transferred over the network using AWS KMS and wants to test the application before going to production.<br/>What is the maximum data size supported by AWS KMS?
      * A. 16KB
      * B. 4KB
      * C. 10MB
      * D. 1MB
39) A social gaming application supports the transfer of gift vouchers between users. When a user hits a certain milestone on the leaderboard, they earn a gift voucher that can be redeemed or transferred to another user. The development team wants to ensure that this transfer is captured in the database such that the records for both users are either written successfully with the new gift vouchers or the status quo is maintained.<br/>Which of the following solutions represent the best-fit options to meet the requirements for the given use-case? (**Select two**)
      * A. Use the Amazon Athena transactional read & write APIs on the table items as a single, all-or-nothing operation
      * B. Complete both operations on Amazon RedShift in a single transaction block
      * C. Use the DynamoDB transactional read & write APIs on the table items as a  single, all-or-nothing operation
      * D. Complete both operations on RDS MySQL in a single transaction block
      * E. Perform DynamoDB read & write operations with ConsistentRead parameter set to true
40) A new recruit is trying to understand the nuances of EC2 Auto Scaling. As an AWS Certified Developer Associate, you have been asked to mentor the new recruit.<br/>Can you identify and explain the correct statements about Auto Scaling to the new recruit? (**Select two**).
      * A. You can't use Amazon EC2 Auto Scaling for health checks (to replace unhealthy instances) if you are not using ELB
      * B. Amazon EC2 Auto Scaling can't add a volume to an existing instance if the existing volume is approaching capacity
      * C. EC2 Auto Scaling groups are regional constructs. They span across AZs & AWS regions
      * D. Every time you create an Auto Scaling group from an existing instance, it creates a new AMI
      * E. Amazon EC2 Auto Scaling works with both ALB & NLB
41) A company uses AWS CodeDeploy to deploy applications from GitHub to EC2 instances running Amazon Linux. The deployment process uses a file called appspec.yml for specifying deployment hooks. A final lifecycle event should be specified to verify the deployment success.<br/>Which of the following hook events should be used to verify the success of the deployment?
      * A. AllowTraffic
      * B. AfterInstall
      * C. ApplicationStart
      * D. ValideService
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
    * [01-11-2020] 46/65 = 70%
````text
1) C & E
2) C
3) A
4) C
5) A
6) B
7) B 
8) C
9) A
10) C
11) B
12) D
13) A
14) C
15) C & E
16) B
17) A
18) C
19) B
20) C
21) C
22) D
23) D
24) C
25) B
26) B
27) A
28) B
29) B
30) A
31) B
32) C
33) C
34) A
35) D
36) C
37) C & E
38) B
39) C & D
40) B & E
41) D
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
````
