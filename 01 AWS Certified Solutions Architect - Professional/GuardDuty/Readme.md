# GuardDuty

## Acronym
* DNS - Domain Name Server
* SNS - Simple Notification Service
* VPC - Virtual Private Cloud

## Intro
* Intellignet Threat discovery to Protect AWS Account
* Uses Machine Learning algorithms, anomaly detection, 3<sup>rd</sup> party data
* One click to enable (30 days trial), no need to install software
* Input data includes:
  * CloudTrails Logs: unusual API calls, unauthorized deployments
  * VPC Flow Logs: unusual internal traffic, unusual IP address
  * DNS Logs: comprosed EC2 instances sending encoded data within DNS queries
* Can setup **CloudWatch Event rules** to be notified in case of findings
* CloudWatch Events rules can target Lambda or SNS

## Diagram
[<img src="https://i.imgur.com/tjqV3VI.png">](https://i.imgur.com/tjqV3VI.png)
