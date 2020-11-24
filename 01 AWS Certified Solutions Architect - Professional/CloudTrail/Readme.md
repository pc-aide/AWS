# CloudTrail

## Acronym
* SDK - Software Developement Kit
* CLI - Command Line Interface
* API - Application Program Interface
* IAM - Identity & Access Management
* S3 - Siimple Storage Service
* CW - CloudWatch

## Intro
* Provides governance, compliance & audit for your AWS Account
* CloudTrail is enabled by default
* Get an history of events/API calls made within your AWS Account by:
  * Console
  * SDK
  * CLI
  * AWS Services
* Can put logs from CloudTrail into CloudWatch Logs
* If a resource is deleted in AWS, look into CloudTrail first!
* CloudTrail console shows the **past 90 days** of activity
* The default UI only shows "**Create**", "**Modify**", or "**Delete**" events
* <ins>CloudTrail Trail:</ins>
  * Get a detailed list of all the events you choose
  * Can include events happening at the object level in S3
  * Ability to store these events in S3 for further analysis
  * Can be region specific or be global & include global events (IAM, etc)
  
---

## Architecture
### Delivery to S3
[<img src="https://i.imgur.com/KHKuscN.png">](https://i.imgur.com/KHKuscN.png)

### Multi Account, Multi Region Logging
[<img src="https://i.imgur.com/1xBlKjK.png">](https://i.imgur.com/1xBlKjK.png)

### Alert for API calls
[<img src="https://i.imgur.com/IyBlyyq.png">](https://i.imgur.com/IyBlyyq.png)

---

## How to react to events the fastest ?
* Overall, CloudTrail may take up to 15 minutes to deliver events
* **CloudWatch Events:**
  * Can be triggered for any API call in CloudTrail
  * The fastest, most reactive way
* **CloudTrail Delivery in CloudWatch Logs**:
  * Events are streamed
  * Can perform a metric filter to analyze occurrennces & detect anomalies
* **CloudTrail Delivery in S3**:
  * Events are delivered every 5 minutes
  * Possibility of analyzing logs integrity, deliver cross account,long-term storage
