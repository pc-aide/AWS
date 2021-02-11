# LAB-01 - New Lambda + API Gateway

## Time
* 40m

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
