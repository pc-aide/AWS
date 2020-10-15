# Demo Mapping Templates

## Doc

## Acronym
* APIGW - API Gateway

## Intro
* New resource
    * Resource name: mapping

[<img src="https://i.imgur.com/LmtXyME.png">](https://i.imgur.com/LmtXyME.png)
[<img src="https://i.imgur.com/ibI2tBG.png">](https://i.imgur.com/ibI2tBG.png)

* Create method
    * GET
      * Integration type: Lambda Function ([`create new function`](#New-function))
      * Lambda function: Lambda-APIGW-Mapping-GET
      
[<img src="https://i.imgur.com/l64SX6Q.png">](https://i.imgur.com/l64SX6Q.png)
[<img src="https://i.imgur.com/L6Ad0Sp.png">](https://i.imgur.com/L6Ad0Sp.png)
      
### New-function
* Function name: Lambda-APIGW-Mapping-GET
* Runtime: python
* Edit code
  * return: exmple: test:
````python
import json

def lambda_handler(event, context):
    # TODO implement
    return {
        "example": "test"
    }
````

---

## Test our new lambda function
* Test 

[<img src="https://i.imgur.com/qSd15R8.png">](https://i.imgur.com/qSd15R8.png)
[<img src="https://i.imgur.com/COtfMcO.png">](https://i.imgur.com/COtfMcO.png)

---

## Integration Response
* i want to change the name" exmple -> other string
* but keep the value: test

[<img src="https://i.imgur.com/sY7dwrO.png">](https://i.imgur.com/sY7dwrO.png)

* Integration response
    * Mapping templates\**application/json**
    * Generate template: empty
      * key: renameExample
      * value: $inputRoot.example
````json
#set($inputRoot = $input.path('$'))
{
    "renameExample" : $inputRoot.example,
    "anotherkey" : "anothervalue"
}
````
[<img src="https://i.imgur.com/nxXbyfH.png">](https://i.imgur.com/nxXbyfH.png)
[<img src="https://i.imgur.com/rhK8a2c.png">](https://i.imgur.com/rhK8a2c.png)

* Test my method:
    * renameKey but still same value
    * anotherKey & value

[<img src="https://i.imgur.com/mdgmgrq.png">](https://i.imgur.com/mdgmgrq.png)
