# Demo Parameter Store (Lambda)

## Acronym
* SSM - Simple System Manager
* IAM - Identity & Access Management
* CMK - Custom Master Key

## Doc

## Console
* Create function
    * name: Lambda-SSM
    * runtime: python
* Edit code:
    * get_parameter = parameter store (SSM) for url & pwd
````json
import json
import boto3

ssm = boto3.client('ssm', region_name="ca-central-1")

def lambda_handler(event, context):
    db_url = ssm.get_parameters(Names=["/my-app/dev/db-url"])
    print(db_url)
    db_password = ssm.get_parameters(Names=["/my-app/dev/db-password"])
    print(db_password)
    return "work"
````

* we need used API
* test our lambda function
    * failed : "AccessDeniedException ...
      * missing IAM Policy
    
[<img src="https://i.imgur.com/qkCfdnr.png">](https://i.imgur.com/qkCfdnr.png)

* IAM Role\:
    * add Inline policy
      * Service: System manager
      * Action: GetParameters + GetParametersByPath
      * Resource:
        * Region: *
        * Account: * (for demo - no best practice)
        * Full qualified parameter name: my-app/*
* Review policy
    * name: SSMGetParameterAndPathForMyApp
    
[<img src="https://i.imgur.com/Fzl8WdL.png">](https://i.imgur.com/Fzl8WdL.png)
[<img src="https://i.imgur.com/LZCSTzK.png">](https://i.imgur.com/LZCSTzK.png)
[<img src="https://i.imgur.com/JAlBSPQ.png">](https://i.imgur.com/JAlBSPQ.png)

* test again our code lambda
    * still an error: 
    * some time need to **wait 5min** to refect our new iam role inline for test code lambda
    
[<img src="https://i.imgur.com/uOw6MkX.png">](https://i.imgur.com/uOw6MkX.png)

* work

[<img src="https://i.imgur.com/ElzQE03.png">](https://i.imgur.com/ElzQE03.png)
[<img src="https://i.imgur.com/X2yjMPP.png">](https://i.imgur.com/X2yjMPP.png)

* flag decrypt for code :
* add WithDecryption=True
````json
import json
import boto3

ssm = boto3.client('ssm', region_name="ca-central-1")

def lambda_handler(event, context):
    db_url = ssm.get_parameters(Names=["/my-app/dev/db-url"])
    print(db_url)
    db_password = ssm.get_parameters(Names=["/my-app/dev/db-password"], WithDecryption=True)
    print(db_password)
    return "work"
````

* test
    * failed: AccessDeniedException
    * Raison: we not allow CMS
    
[<img src="https://i.imgur.com/6sCKIDz.png">](https://i.imgur.com/6sCKIDz.png)
[<img src="https://i.imgur.com/YqFjTQV.png">](https://i.imgur.com/YqFjTQV.png)

* IAM Role\ad inline policies:
    * Service: KMS
    * Action: Decrypt
    * Resource: 
       * Region: *
       * Account: * (for demo, not best practice)
       * Key id: ...
* Review policy
    * name: KMSAllowDecryptForMyApp
    
[<img src="https://i.imgur.com/GTPJrJ0.png">](https://i.imgur.com/GTPJrJ0.png)
[<img src="https://i.imgur.com/U7aNYsB.png">](https://i.imgur.com/U7aNYsB.png)

* test again code lambda
    * work
    
[<img src="https://i.imgur.com/CIZbYM3.png">](https://i.imgur.com/CIZbYM3.png)
[<img src="https://i.imgur.com/S5JKOdW.png">](https://i.imgur.com/S5JKOdW.png)

* Environment variables
    * key: DEV_OR_PROD
    * value: Dev

[<img src="https://i.imgur.com/QW9CweL.png">](https://i.imgur.com/QW9CweL.png)

* Edit code for used this env var:
````json
import json
import boto3
import os

ssm = boto3.client('ssm', region_name="ca-central-1")
dev_or_prod = os.environ['DEV_OR_PROD']

def lambda_handler(event, context):
    db_url = ssm.get_parameters(Names=["/my-app/" + dev_or_prod + "/db-url"])
    print(db_url)
    db_password = ssm.get_parameters(Names=["/my-app/" + dev_or_prod + "/db-password"], WithDecryption=True)
    print(db_password)
    return "work"
````

* test
    * idem for env var: prod

[<img src="https://i.imgur.com/ksvrVEJ.png">](https://i.imgur.com/ksvrVEJ.png)
[<img src="https://i.imgur.com/V8UC4hN.png">](https://i.imgur.com/V8UC4hN.png)
[<img src="https://i.imgur.com/YpzU1v0.png">](https://i.imgur.com/YpzU1v0.png)
