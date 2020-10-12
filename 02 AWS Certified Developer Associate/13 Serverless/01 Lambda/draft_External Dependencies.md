# External Dependencies

## Acronym
* IAM - Identity & Access Managmenet

## Doc

## Intro
* If your Lambda function depends on external libraries:
    * example: AWS X-Ray SDK, DB clients, etc..
* <ins> You need to install the packages alongside your ocde & zip it together</ins>
    * Node.js, use **npm** & "node_modules" directory
    * Python, use **pip** --target options
    * Java, include the relevant **.jar** files
* Upload the <ins>zip</ins> straight to Lambda if less than 50MB, else to S3 first
* Native libraries work: they need to be compiled on Amazon Linux
* AWS SDK comes by default with every Lambda function

---

## Demo
* index.js:
````javaScript
// Require the X-Ray SDK (need to install it first)
const AWSRay = require('aws-xray-sdk-code')

// Require the AWS SDK (comes with every Lambda function)
const AWS = AWS.captureAWS(require('aws-sdk'))

// We'll use the S3 service, so we need a proper IAM role
const s3= new AWS.s3()

exports.handler = async function(event){
    return s3.listBuckets().promise()
}
````

* steps.sh:
````shell
#!/bin/bash

# You need to have nodejs / npm installed beforehand
# nodejs >= 10.x
````bash
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs
````

[<img src="https://i.imgur.com/1RGrD6M.png">](https://i.imgur.com/1RGrD6M.png)

npm install aws-xray-sdk

# Set proper permissions for project files
chmod a+r *

# You need to have the zip command avaialbe
zip -r functions.zip .
````
* Install np - package manager for Node.js
* npm install aws-sdk
````bash
npm install-aws-xray-sdk
````

[<img src="https://i.imgur.com/wCDBDRw.png">](https://i.imgur.com/wCDBDRw.png)
[<img src="https://i.imgur.com/V527L27.png">](https://i.imgur.com/V527L27.png)
[<img src="https://i.imgur.com/GG9sWyT.png">](https://i.imgur.com/GG9sWyT.png)
[<img src="https://i.imgur.com/DNMsPuK.png">](https://i.imgur.com/DNMsPuK.png)

* permissions

[<img src="https://i.imgur.com/JOqRNzY.png">](https://i.imgur.com/JOqRNzY.png)

* we need to zip all these files together
* sure into zip file, we have
    * index.js
    * steps.sh


[<img src="https://i.imgur.com/SJrGLOt.png">](https://i.imgur.com/SJrGLOt.png)
[<img src="https://i.imgur.com/XhF3wBI.png">](https://i.imgur.com/XhF3wBI.png)

* Create funtion
    * RadionButton: Author from scratch
    * Function name: Lambda-XRay-with-deps-demo
    * Runtime: Node.js
* Create function

[<img src="https://i.imgur.com/FxvGvuR.png">](https://i.imgur.com/FxvGvuR.png)

* Upload a .zip file

[<img src="https://i.imgur.com/zqsOZTA.png">](https://i.imgur.com/zqsOZTA.png)
[<img src="https://i.imgur.com/ef4LQVd.png">](https://i.imgur.com/ef4LQVd.png)
[<img src="https://i.imgur.com/7tqyysR.png">](https://i.imgur.com/7tqyysR.png)

* Enable X-Ray:
    * Active tracing

[<img src="https://i.imgur.com/hFlwY3v.png">](https://i.imgur.com/hFlwY3v.png)
[<img src="https://i.imgur.com/KtMtT7L.png">](https://i.imgur.com/KtMtT7L.png)

* IAM Role\Attach policies
    * filter: s3ReadOnly

[<img src="https://i.imgur.com/05Q1cdu.png">](https://i.imgur.com/05Q1cdu.png)
[<img src="https://i.imgur.com/yxpMwsH.png">](https://i.imgur.com/yxpMwsH.png)

* F5 lambda function\permissions
    * x-ray
    * s3
    
[<img src="https://i.imgur.com/b7dH2PV.png">](https://i.imgur.com/b7dH2PV.png)

* test our function
    * failed
    
[<img src="https://i.imgur.com/7ns34K2.png">](https://i.imgur.com/7ns34K2.png)

* fixed the code
* new upload zip file
* test again

[<img src="https://i.imgur.com/FHx2Cu2.png">](https://i.imgur.com/FHx2Cu2.png)
[<img src="https://i.imgur.com/FjyNxaa.png">](https://i.imgur.com/FjyNxaa.png)

* X-Ray
    * Data not found
    
[<img src="https://i.imgur.com/EsmzAvQ.png">](https://i.imgur.com/EsmzAvQ.png)
[<img src="https://i.imgur.com/wJ2jPQ5.png">](https://i.imgur.com/wJ2jPQ5.png)
