# Quiz 07 - Service Communication

## Questions
1) Which target is NOT directly supported for AWS Step Functions?
   * A. Activity Workers
   * B. Lambda functions
   * C. ECS tasks
   * D. Amazon Mechanical Turk
2) You are looking to process tens of thousands of orders per second and you would like to make sure the orders are going to be processed in the order they were placed for each customer. What technology do you recommend using?
   * A. SQS
   * B. Kinesis Data Streams
   * C. SQS FIFO
   * D. SNS
3) You are reading from SQS with an EC2 consumer that sends emails out through a 3rd party service. In the case of application failure, it has been noted that some emails have been sent in duplicate. How would you solve that issue?
   * A. Enable long polling
   * B. Code your application to be idempotent
   * C. Migrate to Kinesis Data Streams
   * D. Create an SQS DLQ
4) You are looking for a queueing technology that supports the MQTT protocol as you are migrating an on-premise application to AWS. What technology do you recommend using?
   * A. SQS
   * B. SQS FIFO
   * C. Kinesis
   * D. Amazon MQ
* [Answers](https://i.imgur.com/mdXvOeV.png)
* Score:
  * [03-12-2020 PM] 3/4 = 75
