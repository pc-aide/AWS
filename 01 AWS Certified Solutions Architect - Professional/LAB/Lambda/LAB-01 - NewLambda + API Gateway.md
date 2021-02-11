# LAB-01 - NewLambda + APIGateway

## Time
* 40m

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

* test API endpoint
* `curl k1v15e7zk7.execute-api.us-west-2.amazonaws.com`

[<img src="https://i.imgur.com/bLR0vKp.png">](https://i.imgur.com/bLR0vKp.png)

## Cloud9
* test with Cloud9 (IDE)
* c9-dev\Open IDE

[<img src="https://i.imgur.com/nt5Tc1i.png">](https://i.imgur.com/nt5Tc1i.png)
[<img src="https://i.imgur.com/lxE4Av3.png">](https://i.imgur.com/lxE4Av3.png)

* bash:
* Switchs:
  * -d --data
  * -H --header
  * -X --request
````bash
HTTP_URL="https://k1v15e7zk7.execute-api.us-west-2.amazonaws.com"
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

## Lambda
* We want to ensure input before to put in DynamoDB !
* put this code after line 5 - add validation function...
  * validates (e.g.):
    * OderId
    * Price
    * quantity
    * payment mode
````js
function validateInputs(raw_input)

{ 
    const o_regex = /^[0-9]*$/g; 
    const valid_payment_options = ["cash", "creditcard", "paypal"] =
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

[<img src="https://i.imgur.com/2Y4OPit.png">](https://i.imgur.com/2Y4OPit.png)

---

## Test API Endpoint - input value
