# Quiz 09 - Monitoring

## Questions
1) You would like to aggregate logs from multiple AWS accounts into a central logging account, near-real-time. How can you set that up?
   * A. Create a CW Logs distination into a Kinesis Streams set up in the central account. Use Kinesis Data Firehose to send the data into S3
   * B. Create a CW Logs destination into a Kinesis Data Firehose set up in the central account. The KDF sends data to S3
   * C. Setup a CW Event to trigger a Lambda function that will export the CW logs into S3 regularly. Setup S3 Cross-Region Replication into the central logging account
2) You are trying to debug some errors your web client have been getting (503), and your architecture consists of CloudFront, API Gateway, Lambda Functions, DynamoDB tables, Fargate containers, SQS queues, and Step Functions. What can you do to efficiently understand where the root cause of the errors is coming?
   * A. Look into the CloudFront access logs
   * B. Look into the API Gateway access logs
   * C. Look into the Lambda logs
   * D. Use X-Ray
* [Answers](https://i.imgur.com/BSeJjC7.png)
* Score:
  * [05-12-2020 AM] 1/2 = 50%
