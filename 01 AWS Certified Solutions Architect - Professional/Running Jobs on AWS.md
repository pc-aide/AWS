# Running Jobs on AWS

## Acronym
* HA - High Availability
* CW - CloudWatch
* EMR - Elastic MapReduce

## Intro
* Strategy 1 - EC2 + cron
  * Provision EC2 instance - cron job
  * It's going to be long running
  * CRON jobs to run script at regular intervals
  * it's not HA, not full tolerance
  * it doesn't scale really well
  * it's har to monitor
  * very simple - straightforward
* Strategy 2 - CW Events + Lambda
  * serveless technologies
  * CW Events
    * different schedule + Lambda function
  * it has more visibility
  * it's more scalable
  * limited in terms of the run time
* Stragegy 3 - Reactive Workflow
  * CRON schedule
    * ex: 5 min or 1 hour or every Tuesday at 2PM
  * source events
    * CW Events
    * S3 Events
    * API Gateway -> then -> Lambda
    * SQS, SNS
    * etc
* Strategy 4 - AWS Batch
  * CW Events -> Batch
  * can use Docker 
  * can use Manage Compute Environments
  * option to use multi-node in Batch
* Strategy 5 - Fargate
  * CW Events -> Fargate jobs
* Strategy 6 - EMR
  * big data technologies
  * migrate from on-premise to the Cloud
  * EMR with a transient cluster or long learning cluster
  
### Diagram
[<img src="https://i.imgur.com/ALKOfNv.png">](https://i.imgur.com/ALKOfNv.png)
