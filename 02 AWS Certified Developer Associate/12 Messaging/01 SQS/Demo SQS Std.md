# Demo SQS Std

## Acronym
* SQS - Simple Queue Service
* Std - Standard
* CMK - Customer master key

## Doc

## Intro
* SQS\Create queue:


[<img src="https://i.imgur.com/UIodxa4.png">](https://i.imgur.com/UIodxa4.png)

* Details
    * Type: Std
    * name: Demo-SQS
* Encryption
    * Enabled
* create queue
    
[<img src="https://i.imgur.com/2Dl8vHh.png">](https://i.imgur.com/2Dl8vHh.png)
[<img src="https://i.imgur.com/ATLw0i2.png">](https://i.imgur.com/ATLw0i2.png)
[<img src="https://i.imgur.com/md9fpyh.png">](https://i.imgur.com/md9fpyh.png)
[<img src="https://i.imgur.com/zoJie3H.png">](https://i.imgur.com/zoJie3H.png)
[<img src="https://i.imgur.com/2x5LQic.png">](https://i.imgur.com/2x5LQic.png)

* Send & receive messages:

[<img src="https://i.imgur.com/V9O4r9S.png">](https://i.imgur.com/V9O4r9S.png)

* Message body: this is a test for my Demo-SQS
* Send message
* poll for messages

[<img src="https://i.imgur.com/fjJnfjP.png">](https://i.imgur.com/fjJnfjP.png)
[<img src="https://i.imgur.com/oqMfhEe.png">](https://i.imgur.com/oqMfhEe.png)

* Receive message:

[<img src="https://i.imgur.com/8tpg8oA.png">](https://i.imgur.com/8tpg8oA.png)
[<img src="https://i.imgur.com/rgay3u8.png">](https://i.imgur.com/rgay3u8.png)

* twice same message - the process it in enough time
* so after 30 seconds, the lowest the message went back into the queue
* & we received it again

[<img src="https://i.imgur.com/7oB6UPd.png">](https://i.imgur.com/7oB6UPd.png)

* delete this message:

[<img src="https://i.imgur.com/5GHFtDO.png">](https://i.imgur.com/5GHFtDO.png)
[<img src="https://i.imgur.com/TfKL1Ap.png">](https://i.imgur.com/TfKL1Ap.png)

* purge
    * delete all message in this queue
    
[<img src="https://i.imgur.com/cYQxiL3.png">](https://i.imgur.com/cYQxiL3.png)

* Encryption:
    * CMK alias

[<img src="https://i.imgur.com/p6eIjfy.png">](https://i.imgur.com/p6eIjfy.png)
