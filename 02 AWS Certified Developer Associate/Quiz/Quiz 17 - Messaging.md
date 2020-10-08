# Quiz 17 - Messaging

## Questions
1) You are preparing for the biggest day of sale of the year, where your traffic will increase by 100x.
   You have already setup SQS standard queue. What should you do?
    * Open a support ticket to pre-warm the SQS queue
    * Enable auto scaling in the SQS queue
    * Increase the capacity ofthe SQS queue
    * Do nothing, SQS scale automatically
* [Answer](https://i.imgur.com/T0O0jWF.png)
2) You would like messages to be processed by SQS consumers only after 5 minutes. What should you do?
    * Increase the DalySeconds parameters
    * Change the Visibility Timeout
    * Enable Long Polling
    * Use the extended SQS client
* [Answer](https://i.imgur.com/dnw5ewZ.png)
3) Your consumers poll 10 messages at a time and finish processing them in 1 minute.
   You notice that your messages are processed twice, as other consumers also receive the messages. What should you do? 
    * Enable Long Polling
    * Add delay to the messages when being produced
    * Increase the VisibilityTimeout
    * Decrease the VisibilityTimeout
* [Answer](https://i.imgur.com/Be4blge.png)
4) One message keeps on being processed and makes your consumers crash one by one. That message has a bad format and you'd like to get rid of it automatically if that happens. How can you implement this?
    * Add a SQS filter to verify the message format
    * Implement a DLQ with a redrive policy
    * Increase the VisibilityTimeout
* [Answer](https://i.imgur.com/4CChazu.png)
5) Your SQS costs are extremely high. Upon closer look, you notice that your consumers are polling SQS
   too often and getting empty data as a result. What should you do?
    * Decrease the number of consumers
    * Enable Long Polling
    * Increase the Visibility Timeout
* [Answer](https://i.imgur.com/llsolF3.png)
6) You'd like your messages to be processed exactly once and in order. Which do you need?
    * SQS Std Queue
    * SQS DLQ
    * SQS Delay Queue
    * SQS FIFO Queue
* [Answer](https://i.imgur.com/6yx9JER.png)
7) You want to send messages of 1 MB to SQS. You need to
    * Open a support ticket with AWS to increase the limit
    * Change the SQS queue config & set the max message size to 2 MB
    * Use the SQS Extended Client library
* [Answer](https://i.imgur.com/YXg5grl.png)
8) You'd like to send a message to 3 different applications all using SQS. You should
    * Use SQS Replication Feature
    * Use SNS + SQS Fan Out pattern
    * Send messages individually to 3 SQS queues
* [Answer](https://i.imgur.com/ncCMrIE.png)
9) You have a Kinesis stream usually receiving 5MB/s of data and sending out 8 MB/s of data.
   You have provisioned 6 shards. Some days, your traffic spikes up to 2 times and you get a throughput exception. You should
    * Enable Kinesis replication
    * Add more shards
    * Use SQS as a buffer to Kinesis
* [Answer](https://i.imgur.com/2xfvdLh.png)
10) You are sending a clickstream for your users navigating your website, all the way to Kinesis.
    It seems that the users data is not ordered in Kinesis, and the data for one individual user is spread across many shards. How to fix that problem?
    * There are too shards, you should only use 1 shard
    * You should use a partition key that represents the identity of the user
    * You shouldn't use multiple consumers, only one & it should re-order data
* [Answer](https://i.imgur.com/KdGh92u.png)
11) You intermittently get a ProvisionedThroughputExceeded Exception in your producing applications. You should 
    * Use linear backoff on retries
    * Use exponential backoff on retries
    * Retry as fas as possible
* [Answer](https://i.imgur.com/JFWdcnX.png)
12) We'd like to perform real time analytics on streams of data. The most appropriate product will be
    * SQS
    * SNS
    * Kinesis
* [Answer](https://i.imgur.com/CSdisjx.png)
13) We'd like for our big data to be loaded near real time to S3 or Redshift. We'd like to convert the data along the way. What should we use?
    * SQS + Lambda
    * SNS + HTTP Endpoint
    * Kinesis Streamins + Kinesis Firehose
* [Answer](https://i.imgur.com/qx1FNmb.png)
14) You want to send email notifications to your users. You should use
    * SQS with Lambda
    * SNS
    * Kinesis
* [Answer](https://i.imgur.com/sBQzmKl.png)
15) Which SQS FIFO message attribute allows two messages to be processed in order?
    * MessageDeduplicationId
    * MessageGroupId
    * MessageHash
    * MessageOrderId
* [Answer](https://i.imgur.com/wiL4TIU.png)
16) Which SQS FIFO message attribute allows two messages to be de-duplicated ?
    * MessageDeduplicationId
    * MessageGroupId
    * MessageOrderId
    * MessageHash
* [Answer](https://i.imgur.com/B3mZpit.png)
17) One of your Kinesis Stream is experiencing increased traffic due to a sale day.
    Therefore your Kinesis Administrator has split shards and thus you went from having
    6 shards to having 10 shards in your Kinesis Stream. Your consuming application is
    running a KCL-based application on EC2 instances. What is the maximum number of EC2 instances that can be deployed to process the shards?
    * 1
    * 6
    * 10
    * 20
* [Answer](https://i.imgur.com/7KfW4vp.png)
18) If you currently have 10 active group messages (defined by GroupID) in your SQS FIFO queues, how many consumers can consume simultaneously?
    * 1
    * 10
    * 20
    * infinite
* [Answer](https://i.imgur.com/f1eN4ta.png)
