# LAB-01 - LambdaCreateOrdersId with Custom Layer

## Acronym
* CF - CloudFormation
* O/P - OutPut
* SG - Security Group

---

## New Table - DynmaoDB
* Table name: orders_table
* Primary key: orderId <String>
* UncheckBox: Use default settings
* Read/Write capacity mode: On-demand
* Create

---

## Cloud9
* Create environment
  * Name: c9-dev
  * Environment type: Create a new EC2 Insance for environement (direct access)
  * Instance type: t3.small
  * Platform: Amazon Linux
    * ami: Cloud9Default

  * NB: It'll  create automatic CF\NewStack:
    * Resources
      * Instance
      * InstanceSG

---

## New Lambda
* Name: create-order
* Runtime: Node.js 14.x
* Index.js
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

* Permissions
* Role name: iam_for_CreateOrder
  * Roles\Permissions\Attach policies
    * AmazonDynamoDBFullAccess
    * AWSLambdaBasicExecutionRole

* env var\edit\add env var
  * key: TABLE_NAME
  * Value: orders_table

---

## New API Gateway
* Create an API
  * Choose an API type: HTTP API
  * Integrations\add integration\Lambda
  * AWS Region: us-west-2
  * Lambda function: create-order
  * Version: 2.0
  * API name: orders-api

* Configure routes
  * Method: POST
  * Resource path: /
  * Integration target: create-order

* Define stages
  * Stage name: $default
  * Next

* Review & create
  * create

* copy cliboard Invoke URL for test api in cloud9

---

## cloud9
* test api endpoint
* c9-dev\Open IDE
* Switch
  * -d --data
  * -H --header
  * -X --request
````sh
HTTP_URL="<invokeURL>"
curl -d '{"orderId":"111","price":232.2, "quantity":2,"payment_mode":"creditcard"}' -H "Content-Type: application/json" -X POST $HTTP_URL
````

* O/P: LambdaDynamo for new items

---

## Add function validateInput 
* Add function validateInput
* Lambda\Functions\create-odrer\index.js\Ln5
* add this function
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

* Add this code\Ln43 - after calling validation function: `if (validateInputs(raw_input)){`
* don't forget : to beging { & and :}

## Test function validateInput
* Cloud9
````sh
curl -d '{"orderId":"222","price":232.2, "quantity":100,"payment_mode":"creditcard"}' \
-H "Content-Type: application/json" -X POST $HTTP_URL
````
* CheckOut error in Lambda\CW\Log stream\

---

## Prepare Lambda layer
* in cloud9
````sh
mkdir utils
cd utils/
mkdir nodejs
cd nodejs
````

* initialize the npm env: `npm init`
* take all default value with enter

* New file:
  * c9-dev\utils\nodejs\`utils.js`
* code js:
  * paste our function validateInput
  * enclose end brace of our function, add this: `module.exports.validateInputs = validateInputs`
* save (ctrl + s)

* zip utils + download in computer for lambda layer
* bash:
````sh
cd ~/environment/utils/
zip -r utils.zip ./*
````

* Download utils.zip in our computer

---

## Create layer
* Lambda\left pane\Layers\Create layer
  * Name: utils
  * Description: function validateInput for DynamoDB
  * Upload: utils.zip
  * Compatible runtimes: Node.js 14x

* Functions\create-order\
  * Select Layers\Add a layer
    * RAdionButon: Custom layers
    * custom layers: utils
    * Version: 1

* Add const : `const utils = require('/opt/nodejs/utils');`
* Remove function validateInputs in index.js
* Replace validateInputs(raw_input): `utils.validateInputs(raw_input)`

---

## Test API endpoint with custom layer
* cloud9\bash
````sh
curl -d '{"orderId":"444","price":10.2, "quantity":4,"payment_mode":"creditcard"}' \
-H "Content-Type: application/json" -X POST $HTTP_URL
````
* O/P DynamoDB
