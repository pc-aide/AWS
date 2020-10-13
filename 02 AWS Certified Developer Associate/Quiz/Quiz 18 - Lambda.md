# Quiz 18 - Lambda

## Questions
1) Which is NOT supported by AWS Lambda?
    * Golang
    * Python
    * Docker
    * Node.js
    * Java
* [Answer](https://i.imgur.com/Qlidehu.png)
2) You have a Lambda function that will process data for 25 minutes before successfully completing it. The code is working fine on your machine, but in AWS Lambda it just fails with a "timeout" issue after 3 seconds. What should you do?
    * Set the timeout to 30 minutes
    * Set the memory to 3GB
    * Run your code somehwere else than Lambda - the maximum timeout is 15 minutes
    * Set the timeout to 15 minutes
* [Answer](https://i.imgur.com/WHRgnTl.png)
3) Your lambda function is invoked asynchronously and some events fail from being processed after 3 retries. You'd like to collect and analyze these events later on. What should do you?
    * Add a loggin statement for all events in your Lambda function & filter the CW logs
    * Enable synchronous processing of events from Lambda
    * Add a DLQ to send messages to SNS
    * Add a DLQ to send messages to SQS
* [Answer](https://i.imgur.com/VHWFiET.png)
4) ou have enabled a Lambda DLQ to SNS but you don't see any events there even though you can tell from CloudWatch metrics that you have failures... what is the most likely reason?
    * AWS SNS is having outages
    * Your IAM execution role for Lambda is missing permissions
    * You should use SQS instead, there's no Lambda DLQ for SNS
* [Answer](https://i.imgur.com/aqgesZX.png)
5) You have enabled the Lambda and X-Ray integration but it doesn't work. Why is that?
    * You need to tun the X-Ray daemon as a dependency in your deployment package
    * You need to check your IAM permissions
    * You need to open a ticket with AWS Support
* [Answer](https://i.imgur.com/JiwTLfN.png)
6) You get the following exception: An error occurred (InvalidParameterValueException) when calling the UpdateFunctionCode operation: Unzipped size must be smaller than 262144000 bytes
    * You have uploaded a zip file larger than 50 MB to AWS Lambda
    * The uncompressed zip file exceeds AWS Lambda limits
    * Your zip file is corrupt
* [Answer](https://i.imgur.com/J8KrznM.png)
7) You'd like to have a long string of 8 KB loaded in your Lambda code
    * Place it in the env variables
    * Place it in the code zip file
* [Answer](https://i.imgur.com/egZWE4d.png)
8) Every time you release a Lambda function version, it gets a new number and you have to manually update all the AWS components linked to your functions (event triggers etc...). What should you use?
    * AWS CF to update all the links automatically
    * Just always use $LATEST & never worry again
    * Use function aliases & update the alias pointer
* [Answer](https://i.imgur.com/r57h12H.png)
9) You want to test out a new Lambda function version and ensure it can sustain production traffic. You are risk averse and don't want to take down your whole application. You should
    * Create a new lambda function & test there
    * Use Aliases & point to the new & old versions
    * Use versions & re-wire AWS
* [Answer](https://i.imgur.com/QW2q4D1.png)
10) You have an RDS instance and realize that every-time your AWS Lambda function is called, it re-establishes a connection to your database. You tell your developers to use a long live database connection string. They tell you...
    * It's impossible, AWS Lambda containers are created & destroyed every time they are called
    * They will move the db connection object outside of the function handler
    * Use a proxy with ElastiCache
* [Answer](https://i.imgur.com/RHckt9y.png)
11) Your Lambda function must use the Node.js drivers to connect to your RDS PostgreSQL database in your VPC. As such, how do you bundle your Lambda function to add the dependencies?
    * Put the function & the depencencies in one folder & zip them together
    * Zip the fuction as is with a package .json file so that Lambda can resolve the dependencies for your
    * Zip the function & the dependencies separately & upload them in Lambda as two parts
    * Upload the code through the AWS console & upload the dependencies as a zip
* [Answer](https://i.imgur.com/hCK0Lai.png)
12) How do you declare a Lambda function with AWS CloudFormation?
    * Upload all the code to CodeCommit & refer to the codecommit Repository in AWS::Lambda::Function block
    * Upload all the code to codeDeploy & refer to the CodeDeploy application in AWS::Lambda::Function block
    * Upload all the code as a folder to S3 & refer the folder in AWS::Lambda::Function block
    * Upload all the code as a zip to S3 & refer the object in AWs::Lambda::Function block
* [Answer](https://i.imgur.com/hLfwbOq.png)
13) You would like to deploy a Lambda function globally so that requests are filtered at the AWS edge locations. Which Lambda deployment mode do you need?
    * Use a Global DynamoDB table as a Lambda source
    * Use a Lambda @ Edge
    * Deploy Lambda in a Global VPC
    * Deploy Lambda in S3
* [Answer](https://i.imgur.com/Fs0TZF8.png)
14) What is the best way to store temporary files for your Lambda functions that will be discarded when the function stops running?
    * Use the local directory /opt
    * Create a tmp/ directory in the source zip file & use it
    * Use the local directory /tmp
    * Use an S3 bucket
* [Answer](https://i.imgur.com/eEjeirY.png)
15) You are looking to invoke an AWS Lambda function every hour (similar to a cron job) in a serverless way. Which event source should you use for your AWS Lambda function?
    * S3
    * SQS
    * CW Events
    * Kinesis
* [Answer](https://i.imgur.com/EFZX2Cz.png)
16) How can a Lambda function be integrated with an ALB?
    * With an Event Source Mapping
    * With an asynchronous invocation
    * With a target group
    * With an ASG
* [Answer](https://i.imgur.com/nlV5f7K.png)
17) A Lambda function invoked by S3 Events has been doing some duplicate logging into CloudWatch Logs with the same request ID. Why?
    * The function has failed & retries have happened
    * The S3 bucket invoked your Lambda function too many times
    * The function timeout is too low
* [Answer](https://i.imgur.com/RG5JhNz.png)
18) Which of the following service does NOT require an event source mapping?
    * DynamoDB Streams
    * Kinesis Streams
    * SQS
    * SNS
* [Answer](https://i.imgur.com/G3pgbMb.png)
19) What is the best way to send the result of an asynchronous Lambda function to SQS?
    * Write it in the Lambda function code
    * Use a destination
    * Use a Lambda layer
    * Use a DLQ
* [Answer](https://i.imgur.com/9FsNvJo.png)
20) A Python dependency takes 5 minutes to natively compile for Lambda and therefore deployments have been really slow. What do you suggest?
    * Store the dependency in S3
    * Build the dependency on EC2
    * Create a Lambda layer
    * Migrate to Node.js
* [Answer](https://i.imgur.com/J1uewFs.png)
