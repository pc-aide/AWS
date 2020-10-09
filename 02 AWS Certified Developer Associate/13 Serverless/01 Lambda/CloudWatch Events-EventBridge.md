# CloudWatch Events-EventBridge

## Acronym
* CW - CloudWatch

## Doc

## Intro
[<img src="https://i.imgur.com/bhT3IpS.png">](https://i.imgur.com/bhT3IpS.png)

---

## Demo
* Lambda\Create function
    * RadioButton: Author from scratch
    * Function name: Demo-EventBridge
    * Runtime: Python
    * Permissions: Create a new role with basic Lambda templates
    * Target: Lambda function
    * Function: Demo-EventBridge

[<img src="https://i.imgur.com/vp0qeLC.png">](https://i.imgur.com/vp0qeLC.png)

* EventBridge\create rule
    * Name: Invoke-Lambda-Every-minute
    * Define pattern: Schedule
    * Fixed rate every: 1 minute
* Create
    
[<img src="https://i.imgur.com/x6niDu3.png">](https://i.imgur.com/x6niDu3.png)
[<img src="https://i.imgur.com/sf87ISM.png">](https://i.imgur.com/sf87ISM.png)
[<img src="https://i.imgur.com/XZ2hUhT.png">](https://i.imgur.com/XZ2hUhT.png)

* Edit Lambda code:
    * add print(evnet):
````python
import json

def lambda_handler(event, context):
    # TODO implement
    print(event)
    return {
        'statusCode': 200,
        'body': json.dumps('Hello from Lambda!')
    }

````

* Refresh webpage lambda\designer:
    * we can see **EventBridge (CW Events)**

[<img src="https://i.imgur.com/rRzENhF.png">](https://i.imgur.com/rRzENhF.png)

* Lambda\Permissions:

[<img src="https://i.imgur.com/xYVYtrp.png">](https://i.imgur.com/xYVYtrp.png)

* Lambda\Monitoring\View logs in CW\recent\log streams:
    * function was invoked
    * log
        * version
        * scheduled event
        * resources
````log
{'version': '0', 'id': '2c1d3dd6-b006-f459-a3ec-36b2c8bef23a', 'detail-type': 'Scheduled Event', 'source': 'aws.events',
'account': '427263915585', 'time': '2020-10-09T18:06:07Z', 'region': 'us-east-1',
'resources': ['arn:aws:events:us-east-1:427263915585:rule/Invoke-Lambda-Every-minute'], 'detail': {}}

````
    
[<img src="https://i.imgur.com/6UfYoIK.png">](https://i.imgur.com/6UfYoIK.png)

* CW\Rule
* delete or disabled this rule (no pay $$$)
* Invoke-Lambda-Every-minute


[<img src="https://i.imgur.com/bhqNnU0.png">](https://i.imgur.com/bhqNnU0.png)
