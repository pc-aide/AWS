# Trusted Advisor

## Doc
* [limit-monitor](https://aws.amazon.com/solutions/implementations/limit-monitor/)

## URL
* [Support plans](https://console.aws.amazon.com/support/plans/home#/)

## Intro
* No need to install anything 
* High level AWS account assessment
* Analyze your AWS accounts & provides receommendation:
  1) **Cost Optimization**
     * Recommendations
  2) Performance
  3) Security
  4) Fault Tolerance
  5) **Service Limits**
* Core Checks & recommendations - all customers
* Can enable weekly email notfication from the console
* Full Trusted Advisor - Available for Business & Enterprise support plans
  * Ability to set CloudWatch alarms when reaching limits
  * **Programmatic Access using AWS Support API**
  
---

## Support Plans
|                                                | Basic Support                                                                             | Developer                                                                                                   | Business                                                                                                                                       | Enterprise                                                                                                                                            |
| ---------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
|                                                | included for all AWS<br>customer & free                                                   | Recommended if you<br>are experimenting or<br>testing in AWS                                                | Recommended if you have<br>production workloads in AWS                                                                                         | Recommended if you have business<br>& / or mission critical workloads in<br>AWS                                                                       |
| AWS Trusted<br>Advisor Best<br>Practice Checks | 7 Core Checks                                                                             | 7 Core checks                                                                                               | Full set of checks<br>\+ Programmatic Access using<br>AWS Support API                                                                          | Full set of checks<br>\+ Programmatic Access using AWS<br>Support API                                                                                 |
| Enhanced<br>Technical Support                  | 24x7 access to<br>customer service,<br>documentation,<br>whitepapers, &<br>support forums | Business hours email<br>access to Cloud<br>Support Associates<br><br>Unlimited cases / 1<br>primary contact | 24x7 phone, email, & chat<br>access to Cloud Support<br>Engineers<br><br>Unlimited cases / unlimited<br>contacts (IAM supported)               | 24x7 phone, email, & chat<br>access to Cloud Support<br>Engineers<br><br>Unlimited cases / unlimited<br>contacts (IAM supported)                      |
| Case Severity /<br>Response Times              |                                                                                           | General guidance:<br>< 24 business hours\*\*<br><br>System impaired:<br>< 12 business hours\*\*             | General guidance: < 24 hours<br>System impaired: < 12 hours<br>Production system impaired:<br>< 4 hours<br>Production system down:<br>< 1 hour | General guidance: < 24 hours<br>System impaired: < 12 hours<br>Production system impaired: < 4hours<br>Business-critical system down:<br>< 15 minutes |

---

## Good to know
* Can check if an S3 bucket is made public
  * But can't check for S3 object that are public inside of your bucket
  * Use CloudWatch Events / S3 Events instead
* Service Limits
  * **Limits can only be monitored** in Trusted Advisor (can't be changed)
  * Cases have to be created manually in **AWS Support Centre** to increase limits
  * OR use the new **AWS Service Quotas** service (new service - has an API)
  
### Diagram
[<img src="https://i.imgur.com/sZU4e9p.png">](https://i.imgur.com/sZU4e9p.png)
