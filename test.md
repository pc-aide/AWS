# SampleNodeJSWithNodeJS

## Resources
1. Cloudformation
    a. EB
    b. couple Role
    c. DynamoDB (noSQL)

### EB
1. env var: nodeJS: 

[<img src="https://i.imgur.com/or6PxUy.png">](https://i.imgur.com/or6PxUy.png)

2. Button Start
    * Generate random email (send to DynamoDB) - demo

[<img src="https://i.imgur.com/1JETi6R.png">](https://i.imgur.com/1JETi6R.png)

3. request #20 - duplicate email (still for the demo with X-Ray)
    * **duplicate@example.com**

[<img src="https://i.imgur.com/cEeISZQ.png">](https://i.imgur.com/cEeISZQ.png)

### DynamoDB
1. Before new record fake email
    * Nbr. recor: 0


[<img src="https://i.imgur.com/rC8gPlO.png">](https://i.imgur.com/rC8gPlO.png)

2. 38 items
    * Note: item = line = record with own unique partition key (email)
            we can see the orig problem for example

### X-Ray
1. Console\trace:
    * Note: traces: item generate data good or bad
    * we use that to get idea where the problem with a GUI

[<img src="https://i.imgur.com/MjZX6K3.png">](https://i.imgur.com/MjZX6K3.png)

2. Service map
    * Client: genrate email - here demo fake client with our email
    * Yellow: Error 

[<img src="https://i.imgur.com/3NR53jS.png">](https://i.imgur.com/3NR53jS.png)
[<img src="https://i.imgur.com/xoxSQX0.png">](https://i.imgur.com/xoxSQX0.png)

Trace\DynamoDB
* Duplicate value - error: 409 for Web SRV

[<img src="https://i.imgur.com/ZlDxLnM.png">](https://i.imgur.com/ZlDxLnM.png)

* EB - Segment:

[<img src="https://i.imgur.com/xX0uTPH.png">](https://i.imgur.com/xX0uTPH.png)


* DynamoDB -Segment:
    * Error 400 Bad request, we can put twice for unique partition key

[<img src="https://i.imgur.com/FlSb4wH.png">](https://i.imgur.com/FlSb4wH.png)
[<img src="https://i.imgur.com/jtWtyoJ.png">](https://i.imgur.com/jtWtyoJ.png)
