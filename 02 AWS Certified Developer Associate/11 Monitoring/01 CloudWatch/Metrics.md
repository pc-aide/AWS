# Metrics

## Acronym
* ASG - Auto-Scaling Group

## Doc
* [Container Monitoring](https://aws.amazon.com/cloudwatch/container-monitoring/?GAdoption_ContainerMonitoringLP&sc_icampaign=Adoption_Campaign_pac-edm-2020-MGAD_CWinconsolemessaging_sitemerch_ContainerMonitoring&sc_ichannel=ha&sc_icontent=awssm-5178_allusers&sc_ioutcome=Enterprise_Digital_Marketing&sc_iplace=console-cw&trk=ha_a134p000003yWZYAA2~ha_awssm-5178_allusers&trkCampaign=pac-edm-2020_management_M)
* [Amazon CloudWatch](https://aws.amazon.com/cloudwatch/)

## Intro
* CloudWatch provides **metrics** for **every services** in AWS
* **Metrics* is a variable to monitor (CPUUtilization, NetworkIn...)
* Metrics belong to **namespaces**
* **Dimension** is an attribute of a metric (instance id, envionment, etc...)
* Up to 10 dimensions per metric
* Metrics have **timestamps**
* Can create CloudWatch dashboards of metrics

---

## EC2 Detailed monitoring
* EC2 instance metrics have metrics "every 5 minutes"
* With detailed monitoring (for a cost), you get data "every 1 minute"
* Use detailed monitoring if you want to more prompt scale your ASG
* The **AWS Free Tier** allows us to have **10** detailed monitoring metrics
* Note: EC2 Memory usage is by default not pushed (must be pushed from inside the instance as a custom metric)

---

## Custom Metric
* Possibility to define & send your own custom metrics to CloudWatch
* Ability to use dimensions (attributes) to segment metrics
    * Instance.id
    * Environment.name
* Metric resolution:
    * standard: 1 minutes
    * High Resolution: up to 1 second(**StorageResolution** API parameter) - Higher cost
* Use API call **PutMetricData**
* use exponential back off in case of throttle errors

---

## Demo
* CloudWatch
* Left panel
* Center

[<img src="https://i.imgur.com/6ducHJQ.png">](https://i.imgur.com/6ducHJQ.png)
[<img src="https://i.imgur.com/ZojSwbW.png">](https://i.imgur.com/ZojSwbW.png)

* Metrics:

[<img src="https://i.imgur.com/IDiZVz2.png">](https://i.imgur.com/IDiZVz2.png)
[<img src="https://i.imgur.com/pHJu9b9.png">](https://i.imgur.com/pHJu9b9.png)

* EC2\Montiring\Enable Detailed Monitoring (each 1min with cost$$$)

[<img src="https://i.imgur.com/fSpInPT.png">](https://i.imgur.com/fSpInPT.png)
[<img src="https://i.imgur.com/8KY8a7o.png">](https://i.imgur.com/8KY8a7o.png)
