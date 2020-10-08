# Demo Lambda

## Acronym
* CW - CloudWatch

## Doc
* [Begin](https://console.aws.amazon.com/lambda/home?region=us-east-1#/begin)
* [AWS Lambda function handler in Python](https://docs.aws.amazon.com/lambda/latest/dg/python-handler.html?icmpid=docs_lambda_help)

## Intro
* Lambda\
* Begin (check the doc)

[<img src="https://i.imgur.com/gQ0Z9Pe.png">](https://i.imgur.com/gQ0Z9Pe.png)
[<img src="https://i.imgur.com/bNPginM.png">](https://i.imgur.com/bNPginM.png)
[<img src="https://i.imgur.com/EDQJ3jp.png">](https://i.imgur.com/EDQJ3jp.png)
[<img src="https://i.imgur.com/JKCfYDH.png">](https://i.imgur.com/JKCfYDH.png)

* Create a function:
    * RadioButton: Use blueprint
    * Blueprints: Hello-world-python
* configure

[<img src="https://i.imgur.com/7VOzgJZ.png">](https://i.imgur.com/7VOzgJZ.png)

* Function name: Demo-Lambda
* Execution role: Create a new role with basic Lambda permissions
* Create function

[<img src="https://i.imgur.com/XOuiL0s.png">](https://i.imgur.com/XOuiL0s.png)
[<img src="https://i.imgur.com/lAI8aps.png">](https://i.imgur.com/lAI8aps.png)

* Test
    * Event template: Hello World
    * Event name
* Create
    
[<img src="https://i.imgur.com/jtNDIfX.png">](https://i.imgur.com/jtNDIfX.png)

* Test again:

[<img src="https://i.imgur.com/xSYKBe3.png">](https://i.imgur.com/xSYKBe3.png)

* click here ... CloudWatch log group:

[<img src="https://i.imgur.com/smzFOwl.png">](https://i.imgur.com/smzFOwl.png)
[<img src="https://i.imgur.com/purXOIc.png">](https://i.imgur.com/purXOIc.png)

* log stream:

[<img src="https://i.imgur.com/r9R6sGK.png">](https://i.imgur.com/r9R6sGK.png)

* Lambda\Function code\
* comment the line 11 (return event...)
* remove the comment line 12 (raise Exception...)
* Deploy

[<img src="https://i.imgur.com/wbjB4JI.png">](https://i.imgur.com/wbjB4JI.png)

* test again:
* Execution result: failed

[<img src="https://i.imgur.com/smwotxM.png">](https://i.imgur.com/smwotxM.png)

* go back to CW\second log stream

[<img src="https://i.imgur.com/OAZyTTv.png">](https://i.imgur.com/OAZyTTv.png)

* Lambda\permissions
    * Demo-Lambda-role-...
    
[<img src="https://i.imgur.com/C3N1UOW.png">](https://i.imgur.com/C3N1UOW.png)
[<img src="https://i.imgur.com/JLizH5V.png">](https://i.imgur.com/JLizH5V.png)

* roll back for the code lambda:
````json
import json

print('Loading function')


def lambda_handler(event, context):
    #print("Received event: " + json.dumps(event, indent=2))
    print("value1 = " + event['key1'])
    print("value2 = " + event['key2'])
    print("value3 = " + event['key3'])
    return event['key1']  # Echo back the first key value
    #raise Exception('Something went wrong')
````
