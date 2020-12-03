# Quiz 06 - Databases

## Questions
1) You want to index your DynamoDB objects into ElasticSearch in order to build a search index in real-time. How do you recommend doing this the most efficiently?
   * A. Create CW Event rule that is triggered every 5 minutes to start a Lambda scan over the DynamoDB table'schanged items. Insert them into ES
   * B. Enable DynamoDB Streams & subscribe a Kinesis Data Firehose ot it to send data to ES
   * C. Enable DynamoDB Streams & subscribe a Kinesis Data Streams to it. Create a Kinesis Data Firehose on the Kinesis Stream to send data to ES
   * D. Enable DynamoDB Streams & subscribe a Lambda function to it. Insert the data from the Lambda function into ES
2) You are looking for a database with auto-scaling features, minimum capacity planning, and unlimited storage. You expect your database to grow to over 200 TB of data. What do you recommend?
   * A. DynamoDB
   * B. Aurora
   * C. RDS
   * D. ES
3) Which way can NOT be directly used to check the health of your RDS database?
   * A. CW Metrics & Alarms
   * B. Application using the JDBC driver
   * C. Route 53 Health Checkers
* [Answers](https://i.imgur.com/q93ixUy.png)
* Score:
  * [03-20-2020 AM] 2/3 = 66%
