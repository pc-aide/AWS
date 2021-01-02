# Demo - Intro

## Acronym
* SAM - Serverless Application Model

## Console
* Serverless Application Repository\Available application
  * search: uploader

[<img src="https://i.imgur.com/Qje1DqX.png">](https://i.imgur.com/Qje1DqX.png)
[<img src="https://i.imgur.com/sWpUawl.png">](https://i.imgur.com/sWpUawl.png)

* click on uploader :

[<img src="https://i.imgur.com/h4glPNl.png">](https://i.imgur.com/h4glPNl.png)

* deploy :

[<img src="https://i.imgur.com/b9SBxip.png">](https://i.imgur.com/b9SBxip.png)

* APIs Gateway
  * Name serverlessrepo-uploader
  
[<img src="https://i.imgur.com/pisE7FN.png">](https://i.imgur.com/pisE7FN.png)
[<img src="https://i.imgur.com/9Z4AEl5.png">](https://i.imgur.com/9Z4AEl5.png)

* Lambda function :

[<img src="https://i.imgur.com/W4HiwlW.png">](https://i.imgur.com/W4HiwlW.png)

* code (node.js) :


[<img src="https://i.imgur.com/NwQcZnu.png">](https://i.imgur.com/NwQcZnu.png)

* Basic settings (Lambda)
  * RAM (MB): 1536
  * Timeout: 1m
  * Description: serverless web application for uploading file to s3
  
* API Endpoint (Lambda)
  * https://re8ga1g4i3.execute-api.us-east-2.amazonaws.com/Prod
  
[<img src="https://i.imgur.com/mT7K8ti.png">](https://i.imgur.com/mT7K8ti.png)
[<img src="https://i.imgur.com/T4OFPFJ.png">](https://i.imgur.com/T4OFPFJ.png)

 * Destination: bucket
 
[<img src="https://i.imgur.com/yMEjRiK.png">](https://i.imgur.com/yMEjRiK.png)

* test, drop *.jpg in API endpoint :

[<img src="https://i.imgur.com/wavgdwS.png">](https://i.imgur.com/wavgdwS.png)


* F5 bucket

[<img src="https://i.imgur.com/Z37M3aS.png">](https://i.imgur.com/Z37M3aS.png)
