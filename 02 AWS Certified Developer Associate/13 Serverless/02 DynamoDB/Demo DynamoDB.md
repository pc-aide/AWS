# Demo DynamoDB

## Acronym
* R - Read
* W - Write

## Doc

## Terminology


## Intro
* DynamoDB

[<img src="https://i.imgur.com/7btik2o.png">](https://i.imgur.com/7btik2o.png)

* Create table (N. Virginia)
    * Table name: Users
    * Primary Key: user_id | String
    * UncheckBox: Use default settings
    * Provisioned capacity (Table)
        * Read: 2
        * Wwrie: 2
    * Auto Scaling
        * UncheckBox: Read capacity
        * UncheckBox: Write capacity
* Create

[<img src="https://i.imgur.com/JdDxQ37.png">](https://i.imgur.com/JdDxQ37.png)
[<img src="https://i.imgur.com/3n4pHXD.png">](https://i.imgur.com/3n4pHXD.png)

* Items
* Create item
    * user_id String: random
    * 2x: append\string
        * first_name: Kevin
        * last_name: Fault
* Save

[<img src="https://i.imgur.com/wqhu7La.png">](https://i.imgur.com/wqhu7La.png)
[<img src="https://i.imgur.com/0Vxiw5a.png">](https://i.imgur.com/0Vxiw5a.png)
[<img src="https://i.imgur.com/NIV1wHY.png">](https://i.imgur.com/NIV1wHY.png)
[<img src="https://i.imgur.com/MHBCEje.png">](https://i.imgur.com/MHBCEje.png)

* create 2<sup>nd</sup> item:
````item
User_id String: 234fdsfds4
first_name String: Marshal
age Number: 21
````
* we can have many items with null(empty for field) in some column
* This is a big difference vs SQL db (classic)

[<img src="https://i.imgur.com/iQIjGkN.png">](https://i.imgur.com/iQIjGkN.png)

* Global Tables (feature)

[<img src="https://i.imgur.com/jY3o73n.png">](https://i.imgur.com/jY3o73n.png)

* Create a 2<sup>nd</sup> table
    * Table name: UserPosts
    * Primary key: user_id
    * CheckBox: Add sort key
    * filedText: post_ts -ts for timestamp
    * UncheckBox: Use default settings
    * Provisioned capacity: 2 for RW
    * remove: {Read,Write} capacity
* create

[<img src="https://i.imgur.com/OKqg7xJ.png">](https://i.imgur.com/OKqg7xJ.png)
[<img src="https://i.imgur.com/iJ0hTCE.png">](https://i.imgur.com/iJ0hTCE.png)

* create item:
````item
user_id String: 2452usersoi3
post_ts String: 2018-10-11T12:30:40z
````

[<img src="https://i.imgur.com/ly0vbcs.png">](https://i.imgur.com/ly0vbcs.png)
[<img src="https://i.imgur.com/U4b9ktQ.png">](https://i.imgur.com/U4b9ktQ.png)

* append (item):
````item
content String: Demo !
````

[<img src="https://i.imgur.com/0RO3ROH.png">](https://i.imgur.com/0RO3ROH.png)

* other item:
    * same user_id
````item
user_id String: 2452usersoi3
post_ts String: 2018-10-02T03:04:12
content String: new post
````

* same user_id
* sort key is different

[<img src="https://i.imgur.com/TZkf2mH.png">](https://i.imgur.com/TZkf2mH.png) 
