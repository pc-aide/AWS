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
      
[<img src="https://i.imgur.com/YHwgoGK.png">](https://i.imgur.com/YHwgoGK.png)
[<img src="https://i.imgur.com/LJpcEaU.png">](https://i.imgur.com/LJpcEaU.png)
[<img src="https://i.imgur.com/F4DfiEb.png">](https://i.imgur.com/F4DfiEb.png)

* Lambda\add trigger
      * trigger: DynamoDB
      * DynamoDM table: UserGames
      * Starting position: trim horizon
* add

[<img src="https://i.imgur.com/UhpkLlS.png">](https://i.imgur.com/UhpkLlS.png)
[<img src="https://i.imgur.com/3rw92E6.png">](https://i.imgur.com/3rw92E6.png)

* DynamoDB\userGames\Trigger

[<img src="https://i.imgur.com/ksNlBEq.png">](https://i.imgur.com/ksNlBEq.png)

* USerGames\Duplicate our first item:
````item
game_id Number: 2345
game_ts String: 2020-05-09T03:04:05z
user_id String: sfdfsdf
````

[<img src="https://i.imgur.com/4ubxRYl.png">](https://i.imgur.com/4ubxRYl.png)

* Edit this item (game_id : 2345):
      * juste change the game_ts - next day for example
      
      
[<img src="https://i.imgur.com/uE4G3QE.png">](https://i.imgur.com/uE4G3QE.png)

* delete: game_id: 1234

[<img src="https://i.imgur.com/6Be88N1.png">](https://i.imgur.com/6Be88N1.png)

* trigger\refresh

[<img src="https://i.imgur.com/TIkdscR.png">](https://i.imgur.com/TIkdscR.png)
[<img src="https://i.imgur.com/HUEITWY.png">](https://i.imgur.com/HUEITWY.png)

* CW\Log stream\ 
      * INSERT
      * DynamoDB Record
      * Modify
      * Remove
      
[<img src="https://i.imgur.com/zfq9dC0.png">](https://i.imgur.com/zfq9dC0.png)
[<img src="https://i.imgur.com/gFXEQhq.png">](https://i.imgur.com/gFXEQhq.png)
[<img src="https://i.imgur.com/OL5zoyn.png">](https://i.imgur.com/OL5zoyn.png)

* juste disabled our trigger (lambda) for no $$$

[<img src="https://i.imgur.com/rTJwcvj.png">](https://i.imgur.com/rTJwcvj.png)
