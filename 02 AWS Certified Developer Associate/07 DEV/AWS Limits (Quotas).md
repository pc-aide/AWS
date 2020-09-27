# AWS Limits (Quotas)

## Acronym

## Doc

## Intro
* <ins>API Rate Limits</ins>
    * **DescribeInstances** API for EC2 has a limit of 100 calls per seconds
    * **GetObject** on S3 has a limit of 5500 GET per second per prefix
    * For Intermittent Errors: implement Exponential Backoff
    * For Consistent Errors: request an API throttling limit increase
* <ins>Service Quotas (Service Limits)</ins>
    * Running On-Demand Standard Instances: 1 152 vCPU
    * You can request a service limit increase by **opening a ticket**
    * You can request a service quota increase by susing the **Service Quotas API** 

---

## Exponential Backoff (any AWS service)
* If you get **THrottlingException** intermittently, use exponential backoff
* Rery mechanism included in SDK API calls
* Must implement yourself if using the API as is or in specific cases

### Diagram
[<img src="https://i.imgur.com/tSvuPIi.png">](https://i.imgur.com/tSvuPIi.png)
