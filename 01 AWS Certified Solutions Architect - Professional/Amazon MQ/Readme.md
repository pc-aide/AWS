## Amazon MQ

## Acronym
* SQS - Simple Queue Service
* HA - High Availability
* SNS - Simple Notification Service

## Intro
* SQS, SNS are "cloud-native" services, & they're using proprietary protocols from AWS
* Trafitional applications running from on-premise may use open protocols such as:
  * MQTT
  * AMQP
  * STOMP
  * Openwire
  * WSS
* **When migrating to the cloud**, instead of re-engineeing the application to use SQS & SNS, we can use Amazon MQ
* Amazon MQ = managed Apache ActiveMQ
* Amazon MQ doesn't "scale" as much as SQS/SNS
* Amazon MQ is not serverless
* Amazon MQ runs on a dedicated machine, can run in HA with failover
* Amazon MQ has both queue feature (~SQS) & topic features (~SNS)

---

## Re-patform
* IBM MQ, TIBCO EMS, Rabiit MQ, & Apache ActiveMQ can be migrated to Amazon MQ

### Diagram
