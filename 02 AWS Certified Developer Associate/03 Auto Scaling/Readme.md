# Auto Scaling

## Doc
* [Getting started with Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/GettingStartedTutorial.html?icmpid=docs_ec2as_help_panel)

## Acronym
* ASG - Auto Scaling Group
* LB - Load Balancer
* AMI - Amazon Machine Image
* EBS - Elastic Block store
* ELB - Elastic Load Balancing
* IAM - Identity & acess management

## What's an Auto Scaling Group?
* In real-like, the load on your websites & application can change
* In the cloud, you can create & get rid of servers very quickly
* The goal of an ASG is to:
    * Scale out (add EC2 instances) to match an increased load
    * Scale int (remove EC2 instances) to math a decreased load
    * Ensure we have a minimum & maximum number of machines running
    * Automatically Register new instances to a LB
    
## Topology
* We must to know, what is our min & max sizes to build our ASG

[<img src="https://i.imgur.com/HG2WwcF.png">](https://i.imgur.com/HG2WwcF.png)

## ASG with LB
[<img src="https://i.imgur.com/MXzb2K2.png">](https://i.imgur.com/MXzb2K2.png)

## ASGs attributes
* A launch configuration
    * AMI + Instance Type
    * EC2 User Data
    * EBS Volumes
    * Security Groups
    * SSH key pair (plublic & private)
* Min Size / Max Size / Initial Capacity
* Network + Subnets Information
* LB Information
* Scaling Policies
    * What is the Trigger scale in & out
    
## Auto Scaling Alarms
* It's possible to scale an ASG based on CloudWatch alarms
* An Alarm monitors a metric (such as Average CPU)
* <ins>Metric are computerd for the overall ASG instances</ins>
* Based on the alarm
    * We can create scale-out policies (increase the number of instances)
    * We can create scale-in policies (decrease the number of instances)

## Topology
[<img src="https://i.imgur.com/QGeiv37.png">](https://i.imgur.com/QGeiv37.png)

## Auto Scaling New Rules
* It's possible to define "better" auto scaling rules that are directly managed by EC2
    * Target Average CPU Usage
    * Number of requests on the ELB per instance
    * Average Network In
    * Average Network Out
* These rules are easier to set up & can make more sense

## Auto Scaling Custom Metric
* We can auto scale based on a custom metric
    * Ex.: number of connected users
1) I Send custom metric from application on EC2 to CloudWatch (PutMetric API)
2) Create CloudWatch alarm to react to low / high values
3) Use the CloudWatch alarm as the scaling policy for ASG

## Wraps up
* Scaling polices can be on CPU, Network... & can even be on custom metrics or based on a schedule (if you know your visitors patterns)
* ASGs use Launch configurations or Launch Templates (newer)
* To update an ASG, you must provide a new launch configuration / launch template
* IAM roles attached to an ASG will get assigned to EC2 instances
* ASG are freee. You pay for the underlying resources being launched
* Having instances under an ASG means that if they get terminated for whatever reason, the ASG will automatically 
  **create new ones as a replacement**. Extra safety!
* ASG can terminate instances marked as unhealthy by an LB (and hence replace them)
