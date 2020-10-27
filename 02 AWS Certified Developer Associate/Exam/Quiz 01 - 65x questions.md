# Quiz 01 - 65x questions

## Time
* 2h10min

## Pass
* 72%

## Questions
1. The development team at a retail organization wants to allow a Lambda function in its AWS Account A to access a DynamoDB table in another AWS Account B.<br/>As a Developer Associate, which of the following solutions would you recommend for the given use-case?
   * A. Create a clone of the Lambda function in AWS Account B so that it can access the DynamoDB table in the same account
   * B. Create an IAM role in Account B with access to DynamoDB. Modify the trust policy of the execution role in Account A to allow the execution role of Lambda to assume the IAM role in Account B. Update the Lambda function code to add the AssurmeRole API call
   * C. Create an IAM in Account B with Access to DynamoDB. Modify the trust policy of the role in Account B to allow the exeution role of Lambda to assume this role Update the Lambda function code to add the AssumeRole API call
   * D. Add a ressouce poly to the DynamoDB table in AWS Account B to give access to the Lambda function in Account A
   
2. A multi-national enterprise uses AWS Organizations to manage its users across different divisions. Even though CloudTrail is enabled on the member accounts, managers have noticed that access issues to CloudTrail logs across different divisions and AWS Regions is becoming a bottleneck in troubleshooting issues. They have decided to use the organization trail to keep things simple.<br/>
What are the important points to remember when configuring an organization trail? (**Select two**)
   * A. Member accounts will be able to see the Organization trail, but can't modify or delete it
   * B. By default, CloudTrail event log files are not encrypted
   * C. Member accounts don't have access to organization trail, neither do they have access to the Amazon S3 bucket that logs the files
   * D. By default, CloudTrail tracks only bucket-level actions. To tracks object-level action, you need to enable Amazon S3 data events
   * E. There is nothing called Organization trail. The master account can, however, enable CloudTrail logging, to keep track of all activities acroos AWS accounts
3. A cyber forensics application, running behind an ALB, wants to analyze patterns for the client IPs.<br/>Which of the following headers can be used for this requirement?
   * A. X-Forwarded-Port
   * B. X-Forwarded-For
   * C. X-Forwarded-IP
   * D. X-Forwarded-Proto
4. A developer at a university is encrypting a large XML payload transferred over the network using AWS KMS and wants to test the application before going to production.
<br/>
What is the maximum data size supported by AWS KMS?
   * A. 16KB
   * B. 10MB
   * C. 4KB
   * D. 1MB
5. A video encoding application running on an EC2 instance takes about 20 seconds on average to process each raw footage file. The application picks the new job messages from an SQS queue. The development team needs to account for the use-case when the video encoding process takes longer than usual so that the same raw footage is not processed by multiple consumers.
<br/>
As a Developer Associate, which of the following solutions would you recommend to address this use-case?
   * A. Use ChangeMessageVisibility action to extend a message's visibility timeout
   * B. Use WaitTimeSeconds action to long poll & extend a message's visibility timeout
   * C. Use WaitTimeSeconds action to hosrt poll & extend a message's visibility timeout
   * D. Use DelaySecond action to dely a message's visibility timeout
6.
* [Answer]()
7.
* [Answer]()
8.
* [Answer]()
9.
* [Answer]()
10.
* [Answer]()
11.
* [Answer]()
12.
* [Answer]()
13.
* [Answer]()
14.
* [Answer]()
15.
* [Answer]()
16.
* [Answer]()
17.
* [Answer]()
18.
* [Answer]()
19.
* [Answer]()
20.
* [Answer]()
21.
* [Answer]()
22.
* [Answer]()
23.
* [Answer]()
24.
* [Answer]()
25.
* [Answer]()
26.
* [Answer]()
27.
* [Answer]()
28.
* [Answer]()
29.
* [Answer]()
30.
* [Answer]()
31.
* [Answer]()
32.
* [Answer]()
33.
* [Answer]()
34.
* [Answer]()
35.
* [Answer]()
36.
* [Answer]()
37.
* [Answer]()
38.
* [Answer]()
39.
* [Answer]()
40.
* [Answer]()
41.
* [Answer]()
42.
* [Answer]()
43.
* [Answer]()
44.
* [Answer]()
45.
* [Answer]()
46.
* [Answer]()
47.
* [Answer]()
48.
* [Answer]()
49.
* [Answer]()
50.
* [Answer]()
51.
* [Answer]()
52.
* [Answer]()
53.
* [Answer]()
54.
* [Answer]()
55.
* [Answer]()
56.
* [Answer]()
57.
* [Answer]()
58.
* [Answer]()
59.
* [Answer]()
* [Answer]()
60.
* [Answer]()
61.
* [Answer]()
62.
* [Answer]()
63.
* [Answer]()
64.
* [Answer]()
65.
* [Answer]()
* Score: 34/75 = 52%
