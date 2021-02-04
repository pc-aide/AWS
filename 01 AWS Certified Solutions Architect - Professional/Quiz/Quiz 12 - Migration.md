# Quiz 12 - Migration

## Questions
1) You are using a MongoDB NoSQL database on-premise and you would like to migrate your application to the cloud and start using DynamoDB on AWS. What kind of migration is this?
   * A. Rehost
   * B. Replatform
   * C. Repurchase
   * D. Refactor
2) You are using a MongoDB NoSQL database on-premise and you would like to migrate your application to the cloud and start using DocumentDB on AWS, which is a managed database on AWS with MongoDB API compatibility. What kind of migration is this?
   * A. Rehost
   * B. Replatform
   * C. Repurchase
   * D. Refactor
3) You would like a Network File System solution for your on-premise instances backed by Amazon S3. You would also like the ensure your EC2 instances have access to the filesystem with minimal latency so that you can easily migrate your on-premise applications to AWS in the future. What do you suggest?
   * A. Create a Storage File Gateway on Premise<br>Mount the S3 bucket as a file system on your EC2 instances
   * B. Mount the S3 bucket as a network file system on-Premise<br>Mount the S3 bucket as a file system on your EC2 instances
   * C. Create a Storage File Gateway on Premise<br>Create a Storage File Gateway on AWS
   * D. Create a Storage File Gateway on Premise<br>Create an EFS mouont in AWS backed by the same S3 bucket
4) You are using a Storage Gateway Tape Gateway for backing up your tapes to the AWS cloud. There has been a need to recover a specific file in a specific tape. How do you suggest doing it?
   * A. Use the S3 API to recover the file
   * B. Recover the entire tape & recover the file
   * C. Create a Storage Gateway File gateway & recover the file
   * D. Create a Storage Gateway Volume gateway & recover the file
5) You need to migrate a large 200TB database over to AWS and have decided to migrate from MySQL to PostgreSQL in the process. There's a 200Mbps Direct Connect connection established between your DC and AWS. What do you recommend to do this the fastest way?
   * A. Export the DB as file. Upload the file to S3 through multi-part upload & S3 transfer acceleration. Use DMS SCT to convert the file & import it into PostgreSQL
   * B. Export the DB as a file. use Snowball to migrate it to S3. Use DMS SCT to convert the file & import it into PostgreSQL
   * C. Create a DMS instance with SCT enabled. Perform a one-time extract & use Snowball to send it to S3. Perform CDC replication using DMS after the data has been imported into PostgreSQL
   * D. Create a DMS instance with SCT enabled. Perform a full extract + CDC replication using DMS to migrate the database into MySQL
6) You would like to migrate an on-premise ElasticSearch cluster into AWS. What do you recommend?
   * A. Create an ES cluster on AWS, & join it with a two-way forest trust with the ElasticSearch cluster on-premise. Let the replication happen & shut down the on-premise cluster
   * B. Create an ES cluster on AWS, & use DMS to migrate the data from on-premise to AWS
   * C. Create an ES cluster on AWS, Export the ElasticSearch index & transfer them into Amazon S3. Import the index from S3 into Amazon ES
7) Which service allows you to collect running processes and map out network traffic between your servers before starting a migration?
   * SMS
   * ADS in agentless mode
   * ADS with the agent-based discovery
   * AWS Migration Hub
* [Answers](https://i.imgur.com/pWZS5pz.png)
* Score:
  * 04-02-2021 -> 2/7 = 28.5%
