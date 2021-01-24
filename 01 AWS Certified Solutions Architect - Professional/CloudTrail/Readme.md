# CloudTrail

## Acronym
* API - Application Program Interface
* CLI - Command Line Interface
* CW - CloudWatch
* IAM - Identity & Access Management
* S3 - Simple Storage Service
* SDK - Software Developement Kit


## Intro
* Provides governance, compliance & audit for your AWS Account
* Records events performed by users, roles, & AWS services
* Includes action events fro mthe console, CLI, & any SDK or API
* Enable governance, compliance, & operational & risk auditing
* Gain to view, search, download, archive, analyze, & respond to monitored actvities within your accounts
* **Trails** are regional, but can be created in all regions
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

## CloudTrail Configuration
* Management Events
* Data Events
* S3 Storage & Encryption

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
