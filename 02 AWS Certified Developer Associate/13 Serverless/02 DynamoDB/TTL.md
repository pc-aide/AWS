# TTL

## Acronym
* TTL - Time To Live
* WCU - Write Capacity Units
* RCU - Read Capacity Units
* GSI - Global Secondary Index
* LSI - Local Secondary Index

## Doc

## Intro
* TTL = automatically delete an item after expiry date/time
* TTL is provided at no extra cost, deletions don't use WCU/RCU
* TTL is a background taks operated by the DynamoDB service itself
* Helps reduce storage & manage the table size over time
* Helps adhere to regulatory norms
* TTL is enabled per row (you define a TTL column, & add a date there)
* DynamoDB typically deletes expired items within 48 hours of expiration
* Deleted items due to TTL are also deleted in GSI/LSI
* DynamoDB Streams can help recover expired items

---

## Demo
* Create table
    * Table name: DemoTTL
    * primary key: user_id
    * UncheckBox: Use default settings
    * No auto scaling
      * WCU/RCU = 1
* create

[<img src="https://i.imgur.com/PvRggJz.png">](https://i.imgur.com/PvRggJz.png)

* add item:
    * number (mandatory for TTL)
````item
user_id String: User_123
name String: Kurt
expire_on number:
````

* search google: time to epoch
    * https://www.epochconverter.com/
    * add 5 min to expire on
    * epoch timestamp: 1602684305
    
[<img src="https://i.imgur.com/4xjIpMu.png">](https://i.imgur.com/4xjIpMu.png)
[<img src="https://i.imgur.com/BgiEVFQ.png">](https://i.imgur.com/BgiEVFQ.png)
[<img src="https://i.imgur.com/LS5WGhG.png">](https://i.imgur.com/LS5WGhG.png)

* another item:
````item
user_id String: user_234
name String: Randy
expire_on Number: 1602687793 - epoch time +1h the current time
````

[<img src="https://i.imgur.com/XTHsFKl.png">](https://i.imgur.com/XTHsFKl.png)

* Overview\Manage TTL
    * TTL attribute: expire_on
    * Run preview (optional)
* Continue
    
    
[<img src="https://i.imgur.com/E4YnDMz.png">](https://i.imgur.com/E4YnDMz.png)
[<img src="https://i.imgur.com/1b7dJqQ.png">](https://i.imgur.com/1b7dJqQ.png)
[<img src="https://i.imgur.com/3kSy8YI.png">](https://i.imgur.com/3kSy8YI.png)

* after TTL expired, these items will be delete

[<img src="https://i.imgur.com/PNSy4mo.png">](https://i.imgur.com/PNSy4mo.png)
