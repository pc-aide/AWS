# Quiz 19 - DynamoDB

## Questions
1) We have to provision the instance type for our DynamoDB database
    * true
    * false
* [Answer](https://i.imgur.com/695NA4S.png)
2) We have to provision read and write capacity units for our DynamoDB tables
    * true
    * false
* [Answer](https://i.imgur.com/9f8OB8A.png)
3) DynamoDB tables scale
    * Horizontally
    * Vertically
* [Answer](https://i.imgur.com/4urnisc.png)
4) If my primary key is a combination of partition key and sort key, then
    * Partition key must be unique
    * Partition key + sort key must be unique
* [Answer](https://i.imgur.com/h0DvmnX.png)
5) You are designing a blog post table. Which column will give us the best partition key for optimal distribution?
    * author_id
    * blog_content
    * blog_id
    * blog_date
* [Answer](https://i.imgur.com/3av6bCY.png)
6) You are writing item of 8 KB in size at the rate of 12 per seconds. What WCU do you need?
    * 12
    * 24
    * 96
    * 48
* [Answer](https://i.imgur.com/sfeWyMv.png)
7) You are doing strongly consistent read of 10 KB items at the rate of 10 per second. What RCU do you need? 
    * 100
    * 30
    * 20
    * 25
* [Answer](https://i.imgur.com/KCXer0y.png)
8) You are doing 12 eventually consistent reads per second, and each item has a size of 16 KB. What RCU do you need?
    * 192
    * 48
    * 24
    * 12
* [Answer](https://i.imgur.com/japTdkT.png)
9) We are getting a ProvisionedThroughputExceededExceptions but after checking the metrics, we see we haven't exceeded the total RCU we had provisioned. What happened?
    * The metric are slow to update
    * We have a hot partition / hot key
    * There's a bug in the code
* [Answer](https://i.imgur.com/O9NvImd.png)
10) You are about to enter the Christmas sale and you know a few items in your website are very popular and will be read often. Last year you had a ProvisionedThroughputExceededException. What should you do this year?
    * Increase the RCU to a very, very high value
    * Create a DAX cluster
    * Migrate database away from DynamoDB for the time of the scale
* [Answer](https://i.imgur.com/WWgxJcn.png)
11) How can you select the attributes to retrieve in the response while using the GetItem DynamoDB CLI?
    * FilterExpression
    * ConditionalWrite
    * ProjectionExpression
* [Answer](https://i.imgur.com/ADr14Vl.png)
12) You want to delete all the data in your table. What's the best way of doing it?
    * Use a Scan & run BatchWriteItem
    * Use a Scan & run DeleteItem
    * Delete & then CreateTable
* [Answer](https://i.imgur.com/ctVc3OT.png)
13) You want to increase the performance of your scan operation. What should you do?
    * Increase the Limit Parameter
    * Use Parallel Scans
    * Use Sequential Scans
    * Increase the RCU
* [Answer](https://i.imgur.com/sxmBkIu.png)
14) You want to use Query equal operation on a non key attribute. How can you do it?
    * Query supports non key attributes
    * Create a local secondary index
    * Create a global secondary index
* [Answer](https://i.imgur.com/IhToB2v.png)
15) You would like to have query for a non key attribute for the >= predicate while keeping the same partition key. You should 
    * Use Query as is
    * Create a GSI
    * Create a LSI
* [Answer](https://i.imgur.com/kJGdLeB.png)
16) You would like to react in real-time to users de-activating their account and send them an email to try to bring them back. The best way of doing it is to...
    * Setup a trigger with SNS
    * Setup CW Events cron job that triggers a Lambda function who searches for account de-activations every 5 min
    * Enable Kinesis Streams
    * Integrate Lambda with a DynamoDB stream
* [Answer](https://i.imgur.com/BDZdQK7.png)
17) Which concurrency model can be implemented with DynamoDB?
    * Optimistic Locking
    * Pessimistic Locking
    * No Locking
* [Answer](https://i.imgur.com/CswGudu.png)
18) Which feature of DynamoDB allows it to achieve Optimistic Locking?
    * Conditional Writes
    * Conditional Reads
    * Locked Reads
    * Locked Writes
* [Answer](https://i.imgur.com/u5sgWGe.png)
19) You have created a DynamoDB table to support your application and provisioned RCU and WCU to it, so that your application has been running for over a year now without any throttling issues. Your application now requires a second type of queries over your table and as such, you have decided to use the existing LSI and created a GSI to support that use case. One month after having implemented such indexes, it seems your table is experiencing throttling. Upon looking at the table's metrics, it seems the RCU and WCU provisioned are still sufficient. What's happening?
    * The LSI is throttling so you need to provision more RCU & WCU to the LSI
    * The GSI is throttling so you need to provision more RCU & WCU to the GSI
    * Adding both an LSI & a GSI to a table is not recommended by AWS best practices as this is a known cause for creating throttles
    * Metrics are lagging in your CW dashboard & you should see the RCU & WCU peaking for the mai ntable in a few minutes
* [Answer](https://i.imgur.com/MHgK48D.png)
20) You would like to have DynamoDB automatically delete old data for you. What should you use?
    * Use TTL
    * Use DynamoDB Streams
    * Use DAX
    * Use a Lambda function
* [Answer](https://i.imgur.com/aMZchOC.png)
21) Which of the following CLI options will allow you to retrieve a subset of the attributes coming from a DynamoDB scan?
    * --filter-expresion
    * --projection-expression
    * --page-size
    * --max-items
* [Answer](https://i.imgur.com/c7TgeBS.png)
22) You would like to paginate the results of a DynamoDB scan in order to minimize the amount of RCU that you will use for that CLI command. Which CLI options should you use?
    * --page-size & --max-items
    * --page-size & --starting-token
    * --max-items & --starting-token
    * --filter-expresion 
* [Answer](https://i.imgur.com/D1HVCm3.png)
23) You are implementing a banking application in which you need to update the Exchanges DynamoDB table and the AccountBalance DynamoDB table at the same time or not at all. Which DynamoDB feature should you use?
    * DynamoDB Indexes
    * DynamoDB Streams
    * DynamoDB Transactions
    * DynamodB TTL
* [Answer](https://i.imgur.com/GwKvRJ5.png)
