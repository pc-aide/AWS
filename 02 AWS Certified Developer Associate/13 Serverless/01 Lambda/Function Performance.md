# Function Performance

## Doc

## Acronym
* DB - Database

## Lambda Function Configuration
* RAM:
    * From 128MB to 3.008MB in 64MB increments
    * The more RAM you add, the more vCPU credits you get
    * At 1.792MB, a function has the equivalent of one full vCPU
    * After 1.792MB, you get more than one CPU, & need to use multi-threading in your code to benefit from it
* **If you application is CPU-bound (computation heavy), increase RAM**
* **Timeout**: default 3 seconds, mazimum is 900s (15 minutes)

---

## Lambda Execution Context
* The execution context is a temporary runtime environment that initializes any external dependencies of your 
  lambda code
* Great for db connections, HTTP clients, SDK clients...
* The execution contet ins maintained for some time in anticipation of another Lambda function invocation
* The next function invocation can "re-use" the context to execution time & save time in initializing connections
  objects
* The execution context includes the /tmp directory

---

## Initialize outside the handler
* Bad:
````python
import os

def get_user_handler(event, context):

   DB_URL = os.getenv("DB_URL")
   db_client = db.connect(DB_URL)
   user = db_client.get(user_id = even["user_id"])
   
   return user
````
* The DB connection is established at every function invocation

* Good:
````python
import os

DB_URL = os.getenv("DB_URL")
db_client = db.connect(DB_URL)

def get_user_handler(event, context):

   user = db_client.get(user_id = event["user_id"])
   
   return user
````
* The DB connect is established once & re-used across invocations

---

## Lambda Function /tmp space
* If your Lambda function needs to download a big file to work...
* If your Lambda function needs disk space to perform operations...
* You can use the /tmp directory
* Max sizee is 512MB
* The directory content remains the execution context is frozen, providing transient cache taht can
  be used for multiple invocations (helpful to checkpoint your work)
* For permanent persistence of object (non temporary), use S3
  
---

## Demo
* 	Lambda-Confg-Demo\Basic settings
      * Memory (MB)
            * min: 128 MB
            * max: 3008 MB
      * Timeout
            * default: 3s
            * max: 900s (15m)
            
[<img src="https://i.imgur.com/J5gjQ1v.png">](https://i.imgur.com/J5gjQ1v.png)
[<img src="https://i.imgur.com/CqIzeQQ.png">](https://i.imgur.com/CqIzeQQ.png)


* test our timeout
      * import time
      * time.sleep(2)
* the lambda code:
````python
import json
import os
import time

def lambda_handler(event, context):
    # a sleep to invoke my timeout
    time.sleep(2)
    return os.getenv("ENVIRONMENT_NAME")

````

[<img src="https://i.imgur.com/rg1sZFC.png">](https://i.imgur.com/rg1sZFC.png)
[<img src="https://i.imgur.com/qAMDi0h.png">](https://i.imgur.com/qAMDi0h.png)

* increase the time to 5s
* test again
* we'll have a fail (timeout)

[<img src="https://i.imgur.com/MlctTo5.png">](https://i.imgur.com/MlctTo5.png)
