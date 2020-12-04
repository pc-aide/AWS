# Quiz 08 - Data Engineering

## Questions
1) You would like to send data in real time for Kinesis Data Streams to ElasticSearch. How do you recommend doing so?
   * A. Use Kinesis Data Firehose
   * B. Use Lambda
   * C. Use a cron job on EC2 with KCL
2) You are looking for the most cost-efficient solution to send your EC2 instance server logs to Amazon S3 near real-time. What do you recommend?
   * A. Setup a CW agent that will send the data to Kinesis Data Firehose connected to S3
   * B. Setup a CW agent that will send the data to Kinesis Data Streams connection to Kinesis Data Firehose to S3
   * C. Setup a Kinesis agent that will send the data to Kinesis Data Firehose connected to S3
   * D. Setup a Kinesis agent that will send to data to Kinesis Data Streams connected to Kinesis Data Firehose to S3
3) You are looking for the most cost-efficient way to process CSV files in Amazon S3 using AWS Batch. The jobs can easily be retried, and the job inflows are very unpredictable. How should you set it up? 
   * A. Setup S3 Events to place a job into the batch Queue. Create a batch managed environment with Spot fleets
   * B. Setup S3 Events to invoke Lambda. Use Lambda to place a job into the Batch Queue. Create a batch managed environment with Spot fleets.
   * C. Setup S3 Events to place a job into the Batch Queue. Create a batch managed environment with On-Demand instances. Perform some capacity planning & reserve some instances to reduce costs
   * D. Setup S3 Events to invoke Lambda. Use Lambda to place a job into the Batch Queue. create a batch managed environment with On-Demand instances. Perform some capacity planning & reserve some instances to reduce costs
4) You are looking for a quick and efficient way to perform distributed processing of CSV files. The distributed job has been packaged as a Docker image and you will require 10 instances to perform distributed and coordinated processing. What do you recommend?
   * A. Use EMR
   * B. Use Fargate
   * C. Use Batch
   * D. Use Lambda
5) You would like to perform a Hive SQL job onto your DynamoDB table. What do you recommend?
   * A. Use Redshift
   * B. Use Athena
   * C. Use EMR
6) You are looking into enabling a multi-region DR strategy for Redshift that's cost-effective. What do you recommend?
   * A. Enable Redshift automated backups, & use CW Events to regularly trigger a Lambda function that will copy the snapshot into a new regin
   * B. Enable Redshift automated backups & enable auto cross-region copy
   * C. Use CW Events to regularly trigger a Lambda function that will execute a dump of the Redshift database onto S3. Setup S3 cross region replication to replicate the dump into another S3 bucket
   * D. Create a Redshift cluster in another region & setup continuous Redshift replication
* [Answers]()
* Score:
  * [04-12-2020 PM] 2/6 = 33%
