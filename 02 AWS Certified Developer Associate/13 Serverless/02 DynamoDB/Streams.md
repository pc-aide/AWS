# Streams

## Acronym
* IAM - Identity & Access Management
* CW - CloudWatch

## Doc

## Intro
* Changes in DynamoDB (Create, Update, Delete) can end up in a DynamoDB Stream
* This stream can be read by Lambda & EC2 instances, & can then do:
    * React to changes in real time (welcome email to new users)
    * Analytics
    * Create derivative tables/views
    * Insert into **ElasticSearch**
* Could implement cross region replication using Streams
* Stream has 24 hours of data retention

### Architecture
[<img src="https://i.imgur.com/WQD4die.png">](https://i.imgur.com/WQD4die.png)

---

## Streams
* Choose the information that will be written to the stream whenever the data in the table is modified:
    1) KEYS_ONLY - Only the key attributes of the modified item
    2) NEW_IMAGE - The entire item, as it appears after it was modified
    3) OLD_IMAGE - The entire item, as it appeared before it was modified
    4) NEW_AND_OLD_IMAGES - Both the new & the old images of the item
* DynamoDB Streams are made of shards, just like Kinesis Data Streams
* You don't provision shards, this is automated by AWS
* **Records aren't retroactively populated in a stream after enabling it**

---

## Streams & Lambda
* You need to define an **Event source Mapping** to read from a DynamoDB Streams
* You need to ensure the Lambda function has the appropriate permissions
* **Your Lambda function is invoked synchronously**

### Diagram
[<img src="https://i.imgur.com/e6GrvX7.png">](https://i.imgur.com/e6GrvX7.png)

---

## Demo
* DynamoDB\UserGames\Overview\**Manage Stream**
    * View type: New & old images 

[<img src="https://i.imgur.com/oXnUmDz.png">](https://i.imgur.com/oXnUmDz.png)
[<img src="https://i.imgur.com/QZozgyF.png">](https://i.imgur.com/QZozgyF.png)
[<img src="https://i.imgur.com/p85Klkz.png">](https://i.imgur.com/p85Klkz.png)

* We need to read our stream
    * create trigger\New function
       * function name: Lambda-DynamoDB-Demo
       * Execution role: create a new role with basic Lambda permissions
       * DynamoDB table: UsersGame table
       * Starting postition: Trim horizon
       * CheckBox: Enable trigger
* create function

[<img src="https://i.imgur.com/mofYj4K.png">](https://i.imgur.com/mofYj4K.png)

* Error (IAM Role)

[<img src="https://i.imgur.com/mChiCm5.png">](https://i.imgur.com/mChiCm5.png)

* Permissions\<role name>
    * CW Logs

[<img src="https://i.imgur.com/FqA4dmU.png">](https://i.imgur.com/FqA4dmU.png)

* Attach policies
    * filter policies: DynamoDB
      * AWSLambdaDynamoDBExecutionRole
      
[<img src="https://i.imgur.com/YHwgoGK.png>](https://i.imgur.com/YHwgoGK.png)
