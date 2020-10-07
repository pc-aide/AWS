# Logs

## Acronym
* EB - Elastic Beanstalk
* ECS - Elastic Container Service
* VPC - Virtual Private Cloud
* IAM - Identity & Access Management
* KMS - Key Management Service

## Doc

## Intro
* Applications can send logs to CloudWatch using the SDK
* CloudWatch can collect log from:
    * EB: collection of logs from application
    * ECS: collection from containers
    * Lambda: Collection from functions logs
    * VPC Flow Logs: VPC specific logs
    * API Gateway
    * CloudTrail based on filter
    * CloudWatch log agents: for example on EC2 machines
    * Route 53: Log DNS queries
* CloudWatch Logs can go to:
    * Batch exporter to S3 for archival
    * Steam to ElasticSearch cluster for forther analytics
* CloudWatch Logs can use filter expressions
* Logs storage architecture:
    * Log groups: arbitrary name, usually representing an application
    * Log stream: instances within application/ log files/ containers
* Can define log expiration polcies (never expire, 30 days, etc...)
* Using the AWS CLI we can tail CloudWatch logs
* To send logs to CloudWatch, make sure IAM permissions ar correct
* Security: encryption of logs using KMS at the Group Level

---

## Demo
* CloudWatch\Logs

[<img src="https://i.imgur.com/9Z9ecvm.png">](https://i.imgur.com/9Z9ecvm.png)

* View log groups:
     * /aws/codebuild/Build-Project-Demo:

[<img src="https://i.imgur.com/o2oDbDl.png">](https://i.imgur.com/o2oDbDl.png)
[<img src="https://i.imgur.com/nEajchA.png">](https://i.imgur.com/nEajchA.png)

* Log stream:

[<img src="https://i.imgur.com/coAZwM5.png">](https://i.imgur.com/coAZwM5.png)

* log event\filter
     * echo
      
[<img src="https://i.imgur.com/Pt5fOWG.png">](https://i.imgur.com/Pt5fOWG.png) 
[<img src="https://i.imgur.com/aMwsmL5.png">](https://i.imgur.com/aMwsmL5.png)
[<img src="https://i.imgur.com/c84twIP.png">](https://i.imgur.com/c84twIP.png)

* log group\action: retention setting:

[<img src="https://i.imgur.com/a2jQ1ni.png">](https://i.imgur.com/a2jQ1ni.png)

* Export data to Amazon S3:

[<img src="https://i.imgur.com/NDtNWKL.png">](https://i.imgur.com/NDtNWKL.png)

* Subscription (ElasticSearch):

[<img src="https://i.imgur.com/CAVbT3f.png">](https://i.imgur.com/CAVbT3f.png)

* EB\cfg\software edit
      * Enable log streaming (CloudWatch logs)
      
[<img src="https://i.imgur.com/FV4CYTz.png">](https://i.imgur.com/FV4CYTz.png)
[<img src="https://i.imgur.com/454swtk.png">](https://i.imgur.com/454swtk.png)

* EB\cfg\monitoring edit\**Health event streaming to CloudWatch Logs
      * Enabled
      
[<img src="https://i.imgur.com/dcl2sKM.png">](https://i.imgur.com/dcl2sKM.png)
[<img src="https://i.imgur.com/aMiJRrX.png">](https://i.imgur.com/aMiJRrX.png)

* CloudWatch\Log groups\**refresh**:

[<img src="https://i.imgur.com/oVh3j4S.png">](https://i.imgur.com/oVh3j4S.png)

* log groups\...\nginx/access.log:

[<img src="https://i.imgur.com/DT7LSz1.png">](https://i.imgur.com/DT7LSz1.png)

* log stream:

[<img src="https://i.imgur.com/ZSm72As.png">](https://i.imgur.com/ZSm72As.png)
