# Demo Env Variables

## Acronym
* Env: Environment
* KMS - Key Management Service
* CMK - Customer Master Key

## Doc
* [Using AWS Lambda environment variables](https://docs.aws.amazon.com/lambda/latest/dg/configuration-envvars.html)

## Intro
* Env variable = key/value pair in "String" form
* Adjust the function behavior without updating code
* The Env variables are available to your code
* Lambda Service adds its own system env variables as well
* Helpful to store secrets (encrypted by KMS)
* Secrets can be encrypted by the Lambda service key, or your own CMK

---

## Demo
* Create function
    * RadioButton: Author from scratch
    * Function name: Lambda-Confg-Demo
    * Runtime: Python
* Create function

[<img src="https://i.imgur.com/X7SWdIz.png">](https://i.imgur.com/X7SWdIz.png)

* How we can pass an env variable to the Lambda function
* Now no encrypted
* Edit your code Lambda:
    * import os
````python
import json
import os

def lambda_handler(event, context):
    # TODO implement
    return {
        'statusCode': 200,
        'body': json.dumps('Hello from Lambda!')
    }
````

* Env vairable :

[<img src="https://i.imgur.com/qTFpSRF.png">](https://i.imgur.com/qTFpSRF.png)

* Manage env variable:
    * Add env variable
        * key: ENVIRONMENT_NAME
        * value: dev
* Save

[<img src="https://i.imgur.com/oeAX9Au.png">](https://i.imgur.com/oeAX9Au.png)
[<img src="https://i.imgur.com/BQbHzHL.png">](https://i.imgur.com/BQbHzHL.png)

* Edit code Lambda:
    * return os.getenv("dev"):
````python
import json
import os

def lambda_handler(event, context):
    # TODO implement
    return os.getenv("ENVIRONMENT_NAME")
````

* test new code

[<img src="https://i.imgur.com/aRkoduw.png">](https://i.imgur.com/aRkoduw.png)

* 
