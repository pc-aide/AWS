# LAB-01 - LambdaCreateOrdersId with Custom Layer

## Acronym
* CW - CloudWatch

## Intro
1) Create LambdaCreateOrdferId
2) Create an API Gateway who invoke lambda function for DynamoDB like input data
3) Test API endpoint into Cloud9
4) Used layer for lambda function (code externe)

## Time
* 40m

## Resources
1) Lambda
2) Role
3) CloudFormation
  * Cloud9
4) API Gateway
* CW - optional

---

## draft_Role
* Name: ima_for_freateorder
* Trust relationShips: Lambda
* Permissions policies
  * AmazonDynamoDBFullAccess
  * AWSLambdaBasicExecutionRole

[<img src="https://i.imgur.com/RbnMQoP.png">](https://i.imgur.com/RbnMQoP.png)

---

## draft_Lambda
* New function
  * Name: create-order
  * Runtime: Node.js 12x
  * index.js
````js
const dynamodb = require('aws-sdk/clients/dynamodb')
const docClient = new dynamodb.DocumentClient();

// add validation function code: TODO

exports.handler = async (event) => {
    
    console.log(event)

    const raw_input = JSON.parse(event.body)

    // calling validation function: TODO
    
    
    // preparing the paramters for DynamoDB put operation
        const params = {
            TableName : process.env.TABLE_NAME,
            Item: { 
                orderId: raw_input.orderId, 
                price: raw_input.price,
                quantity: raw_input.quantity,
                payment_mode: raw_input.payment_mode
            }
        };
    
        const result = await docClient.put(params).promise();

        return "Success"  
};
````
  
[<img src="https://i.imgur.com/YNtAhLc.png">](https://i.imgur.com/YNtAhLc.png)
[<img src="https://i.imgur.com/fk4Qkig.png">](https://i.imgur.com/fk4Qkig.png)

* Permissions
1) AWS KMS
  * Role name: iam_for_createorder
  * By resource
    * Resource: All resource
    * Action: 
      * Allow:kms:DescribeKey
      * Allow:kms:ListAlias

[<img src="https://i.imgur.com/hrXtOqx.png">](https://i.imgur.com/hrXtOqx.png)

2) 

---

## API Gateway
* New HTTP API
  * Add integration\Lambda
  * AWS Region: us-wst-2
  * Lambda function: create-order
  * Version: 2.0
  * API Name: orders-api
  
[<img src="https://i.imgur.com/IyojGtI.png">](https://i.imgur.com/IyojGtI.png)

* Configure routes
  * Method: POST
  * Resource path: /
  * Integration targer: create-order
  
[<img src="https://i.imgur.com/Ytx8gJD.png">](https://i.imgur.com/Ytx8gJD.png)

* Define stages
  * next
  
[<img src="https://i.imgur.com/TiOd3cG.png">](https://i.imgur.com/TiOd3cG.png)

* Review & create
  * Create
  
[<img src="https://i.imgur.com/T5HpBrp.png">](https://i.imgur.com/T5HpBrp.png)

* Record Invoke URL: https://k1v15e7zk7.execute-api.us-west-2.amazonaws.com

[<img src="https://i.imgur.com/Oh2LgTg.png">](https://i.imgur.com/Oh2LgTg.png)

---

## Cloud9
* test api endpoint with Cloud9 (IDE)
* c9-dev\Open IDE

[<img src="https://i.imgur.com/nt5Tc1i.png">](https://i.imgur.com/nt5Tc1i.png)
[<img src="https://i.imgur.com/lxE4Av3.png">](https://i.imgur.com/lxE4Av3.png)

* bash:
* Switchs:
  * -d --data
  * -H --header
  * -X --request
````bash
HTTP_URL="<invokeURL>"
curl -d '{"orderId":"111","price":232.2, "quantity":2,"payment_mode":"creditcard"}' -H "Content-Type: application/json" -X POST $HTTP_URL
````

[<img src="https://i.imgur.com/uJHfvUJ.png">](https://i.imgur.com/uJHfvUJ.png)

## DynamoDB
* Tables\order_table\Items
  * orderId: 111
  * payment_mode: creditcard
  * price: 232.2
  * quantity: 2

[<img src="https://i.imgur.com/hTUpTYf.png">](https://i.imgur.com/hTUpTYf.png)
[<img src="https://i.imgur.com/URpxokK.png">](https://i.imgur.com/URpxokK.png)
[<img src="https://i.imgur.com/Aq3NGoq.png">](https://i.imgur.com/Aq3NGoq.png)

---

## ValidateInputData - Lambda
* We want to ensure input before to put in DynamoDB !
* put this code after line 5 - add validation function...
  * validates (e.g.):
    * OderId
    * Price
    * quantity
    * payment mode
````js
function validateInputs(raw_input){ 

    const o_regex = /^[0-9]*$/g; 
    const valid_payment_options = ["cash", "creditcard", "paypal"] 
    const price_regex=/^[-+]?[0-9]+\.[0-9]+$/; 
    
    if (!raw_input.orderId){ 
       throw new Error("order id is missing") 
    }  

    if (!o_regex.test(raw_input.orderId)){
       throw new Error("OrderId is not in the expected format")
    }    

    if (!price_regex.test(raw_input.price)){ 
       throw new Error("Price is not in the expected format") 
    }     

    if (!Number.isInteger(raw_input.quantity)){ 
       throw new Error("Quantity is not an integer") 
    }
     
    if (raw_input.quantity < 0 || raw_input.quantity >= 10){ 
       throw new Error("Quantity is not in the expected range [1 to 10]") } 

    if (!valid_payment_options.includes(raw_input.payment_mode)){ 
      throw new Error("Invalid Payment option") 
    } 
    return true
}
````
* Deploy (save)

[<img src="https://i.imgur.com/HKf53A9.png">](https://i.imgur.com/HKf53A9.png)

* Replace the **exports.handler** function
````js
exports.handler = async (event) => {
    console.log(event)
    const raw_input = JSON.parse(event.body)
    
    // calling validation function: TODO
    if (validateInputs(raw_input)){
    
     // preparing the paramters for DynamoDB put operation
        const params = {
            TableName : process.env.TABLE_NAME,
            Item: { 
                orderId: raw_input.orderId, 
                price: raw_input.price,
                quantity: raw_input.quantity,
                payment_mode: raw_input.payment_mode
            }
        };    
        const result = await docClient.put(params).promise();
        return "Success"  
    };  
};
````
[<img src="https://i.imgur.com/ziGJ2h7.png">](https://i.imgur.com/ziGJ2h7.png)
* Deploy (save)

## Test API Endpoint with validationFunction
* test our API endpoint againt with the update Lambda
* validate input data
* Cloud9:
````sh
curl -d '{"orderId":"222","price":232.2, "quantity":100,"payment_mode":"creditcard"}' -H "Content-Type: application/json" -X POST $HTTP_URL
````
[<img src="https://i.imgur.com/R6G6ZUW.png">](https://i.imgur.com/R6G6ZUW.png)

* CW\aws\labmda\create-order\Log stream 
* take the last event time
  * error: quantity_range:1@10
* Log events

| TimeStamp                     | Message                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 2021-02-11T14:48:21.998-05:00 | START RequestId: 099f6dde-2105-4688-b4b2-cc92ad2105e4 Version: $LATEST                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| 2021-02-11T14:48:22.031-05:00 | 2021-02-11T19:48:22.002Z 099f6dde-2105-4688-b4b2-cc92ad2105e4 INFO { version: '2.0', routeKey: 'POST /', rawPath: '/', rawQueryString: '', headers: { accept: '*/*', 'content-length': '75', 'content-type': 'application/json', host: 'v92kjy7un5.execute-api.us-west-2.amazonaws.com', 'user-agent': 'curl/7.61.1', 'x-amzn-trace-id': 'Root=1-60258a05-447221af33055571288fd5f7', 'x-forwarded-for': '34.223.83.226', 'x-forwarded-port': '443', 'x-forwarded-proto': 'https' }, requestContext: { accountId: '686889259404', apiId: 'v92kjy7un5', domainName: 'v92kjy7un5.execute-api.us-west-2.amazonaws.com', domainPrefix: 'v92kjy7un5', http: { method: 'POST', path: '/', protocol: 'HTTP/1.1', sourceIp: '34.223.83.226', userAgent: 'curl/7.61.1' }, requestId: 'amKA4i18vHcES7Q=', routeKey: 'POST /', stage: '$default', time: '11/Feb/2021:19:48:21 +0000', timeEpoch: 1613072901506 }, body: '{"orderId":"222","price":232.2, "quantity":100,"payment_mode":"creditcard"}', isBase64Encoded: false } |
| 2021-02-11T14:48:22.032-05:00 | 2021-02-11T19:48:22.032Z 099f6dde-2105-4688-b4b2-cc92ad2105e4 ERROR Invoke Error {"errorType":"Error","errorMessage":"Quantity is not in the expected range [1 to 10]","stack":["Error: Quantity is not in the expected range [1 to 10]"," at validateInputs (/var/task/index.js:28:14)"," at Runtime.exports.handler (/var/task/index.js:41:9)"," at Runtime.handleOnce (/var/runtime/Runtime.js:66:25)"]}                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 2021-02-11T14:48:22.052-05:00 | END RequestId: 099f6dde-2105-4688-b4b2-cc92ad2105e4                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| 2021-02-11T14:48:22.052-05:00 | REPORT RequestId: 099f6dde-2105-4688-b4b2-cc92ad2105e4 Duration: 53.66 ms Billed Duration: 54 ms Memory Size: 128 MB Max Memory Used: 77 MB Init Duration: 320.03 ms                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

* 2021-02-11T19:48:22.032Z	099f6dde-2105-4688-b4b2-cc92ad2105e4	ERROR	Invoke Error
````json
{
    "errorType": "Error",
    "errorMessage": "Quantity is not in the expected range [1 to 10]",
    "stack": [
        "Error: Quantity is not in the expected range [1 to 10]",
        "    at validateInputs (/var/task/index.js:28:14)",
        "    at Runtime.exports.handler (/var/task/index.js:41:9)",
        "    at Runtime.handleOnce (/var/runtime/Runtime.js:66:25)"
    ]
}
````

[<img src="https://i.imgur.com/5ZGLiHL.png">](https://i.imgur.com/5ZGLiHL.png)

---

## prepare Lambda layer in Cloud9
* cloud9\c9-dev\Open IDE
* paste code:
````sh
mkdir utils
cd utils/
mkdir nodejs
cd nodejs
````
[<img src="https://i.imgur.com/YSrHiPP.png">](https://i.imgur.com/YSrHiPP.png)

* initialize the npm env
* enter for default value
* `npm init`

[<img src="https://i.imgur.com/NAhyyxp.png">](https://i.imgur.com/NAhyyxp.png)

* New file: package.json

[<img src="https://i.imgur.com/IpTGHJn.png">](https://i.imgur.com/IpTGHJn.png)

* folder: nodejs\New File
 * Name: utils.js
 
[<img src="https://i.imgur.com/5JiWGr0.png">](https://i.imgur.com/5JiWGr0.png)

* code for utils.js
````js
function validateInputs(raw_input){ 
    const o_regex = /^[0-9]*$/g; 
    const valid_payment_options = ["cash", "creditcard", "paypal"] 
    const price_regex=/^[-+]?[0-9]+\.[0-9]+$/;    

    if (!raw_input.orderId){ 
       throw new Error("order id is missing") 
    } 

    if (!o_regex.test(raw_input.orderId)){
       throw new Error("OrderId is not in the expected format")
    }

    if (!price_regex.test(raw_input.price)){ 
       throw new Error("Price is not in the expected format") 
    } 

    if (!Number.isInteger(raw_input.quantity)){ 
       throw new Error("Quantity is not an integer") 
    }     

    if (raw_input.quantity < 0 || raw_input.quantity >= 10){ 
       throw new Error("Quantity is not in the expected range [1 to 10]") } 

    if (!valid_payment_options.includes(raw_input.payment_mode)){ 
      throw new Error("Invalid Payment option") 
    } 

    return true
}

module.exports.validateInputs = validateInputs
````
* save (ctrl + s)

[<img src="https://i.imgur.com/QT0im1b.png">](https://i.imgur.com/QT0im1b.png)

* bash (cloud9):
* Switch:
  * -r --recursive
````sh
cd ~/environment/utils/
zip -r utils.zip ./*
````

[<img src="https://i.imgur.com/6cxYcUJ.png">](https://i.imgur.com/6cxYcUJ.png)

* download utils.zip - it will be used for the Lambda layer

[<img src="https://i.imgur.com/yZcmBDc.png">](https://i.imgur.com/yZcmBDc.png)

## Lambda
* left pane\Additonal resources\Layer\Create layer
  * Name: utils
  * Upload: utils.zip
  * Compatible runtimes: Node.js 12x
  
[<img src="https://i.imgur.com/NJjABeG.png">](https://i.imgur.com/NJjABeG.png)
[<img src="https://i.imgur.com/YobNTFF.png">](https://i.imgur.com/YobNTFF.png)

---

## Lambda
* Lambda layer - code for validate the incoming events
* function\create-order\Layers
* Add a layer

[<img src="https://i.imgur.com/Y3uHG3S.png">](https://i.imgur.com/Y3uHG3S.png)

* Choose a layer: Custom layers
* Custom layers: utils
* Version: 1

[<img src="https://i.imgur.com/sT4VHP7.png">](https://i.imgur.com/sT4VHP7.png)
[<img src="https://i.imgur.com/i5OHw27.png">](https://i.imgur.com/i5OHw27.png)

---

## update code function
* Remove function validate - because we have it in layer
* And add reference to the lambda layer code
* inde.js\Ln3
* add `const utils = require('/opt/nodejs/utils');`
* deploy (save)
* NB: layers are extracted to the **/opt/** directory

[<img src="https://i.imgur.com/Sh3hKrT.png">](https://i.imgur.com/Sh3hKrT.png)

* Remove function validateInputs

[<img src="https://i.imgur.com/KrjxBgH.png">](https://i.imgur.com/KrjxBgH.png)

* Replace the validateInputs(raw_input): `utils.validateInputs(raw_input)`

[<img src="https://i.imgur.com/N6pipeq.png">](https://i.imgur.com/N6pipeq.png)

---

## Test API with update code
* test our API endpoint with update code in cloud9
````sh
curl -d '{"orderId":"444","price":10.2, "quantity":4,"payment_mode":"creditcard"}' -H "Content-Type: application/json" -X POST $HTTP_URL
````
[<img src="https://i.imgur.com/TNqj5BY.png">](https://i.imgur.com/TNqj5BY.png)

* CheckOut DynamodDB\Tables\orders_table\Items

[<img src="https://i.imgur.com/J5ijQ5D.png">](https://i.imgur.com/J5ijQ5D.png)
