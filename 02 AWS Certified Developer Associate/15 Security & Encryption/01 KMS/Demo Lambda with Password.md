# Demo Lambda with Password

## Doc

## Acronym
* pwd - password
* CMK - Custom Master Key

## Console
* Create new Lambda function
    * name: Lambda-With-Password
    * runtime: python
    
[<img src="https://i.imgur.com/qqomvVd.png">](https://i.imgur.com/qqomvVd.png)

### Code Lambda with pwd
#### 01 - Plaintext into code (CONSTANT)
* Never do that:
* Code Lambda
````json
dbpassword = "SuperSecret"
````

#### 02 - Envrionment variables
* new env variable
    * key: DB_PASSWORD
    * value: SuperSecret
* if anyone can acces our env variable, so this still bad practice - don't do that:
    
[<img src="https://i.imgur.com/5jIX3w0.png">](https://i.imgur.com/5jIX3w0.png)

#### 03 - PWD encrypted (var env)
* Edit environment vairables
    * Encryption configuration
      * Enable helpers for encryption in transit
      * Use a CMK: Demo-KMS
      
[<img src="https://i.imgur.com/9IVt9XT.png">](https://i.imgur.com/9IVt9XT.png)

* Encryption in transit
    * ENCRYPTED secret snippet - take a copy to our clipboard
    * DECRYPTED
    
[<img src="https://i.imgur.com/kEbj2tZ.png">](https://i.imgur.com/kEbj2tZ.png)
[<img src="https://i.imgur.com/fD5U7fW.png">](https://i.imgur.com/fD5U7fW.png)

* Used our pwd encrypted in our code lambda:
    * First step ENCRYPTED to take the env var (CONSTANT)
````json
import json

import boto3
import os

from base64 import b64decode

ENCRYPTED = os.environ['DB_PASSWORD']
# Decrypt code should run once and variables stored outside of the function
# handler so that these are decrypted once per container
DECRYPTED = boto3.client('kms').decrypt(
    CiphertextBlob=b64decode(ENCRYPTED),
    EncryptionContext={'LambdaFunctionName': os.environ['AWS_LAMBDA_FUNCTION_NAME']}
)['Plaintext'].decode('utf-8')

def lambda_handler(event, context):
    #Debug
    # env var (constant)
    print(ENCRYPTED)
    # PLAINTEXT-decrypted
    print(DECRYPTED)
    # Out Put
    return DECRYPTED
````

* Change timeout default: 3s -> 10s (because take a little time for encrypted/decrypted)

* test our code
    * execution: failed
      * AccessDeniedException -> missing IAM Role (allow decrypt KMS !)
      
[<img src="https://i.imgur.com/cgvOBSl.png">](https://i.imgur.com/cgvOBSl.png)

* IAM Role\<name-lambda-function>

[<img src="https://i.imgur.com/nQVrgLg.png">](https://i.imgur.com/nQVrgLg.png)

* add inline policy for decrypt KMS
    * Service: kms
    * Action: decrypt
    * Resources: <arn:demo-kms>
* Review policy
    * name: AllowKMSDecryptForDemo-KMS
    
[<img src="https://i.imgur.com/lTDlmOQ.png">](https://i.imgur.com/lTDlmOQ.png)
[<img src="https://i.imgur.com/zBzYt8b.png">](https://i.imgur.com/zBzYt8b.png)

* Try again our test lambda function
    * working
    
[<img src="https://i.imgur.com/C0kN1ZU.png">](https://i.imgur.com/C0kN1ZU.png)
