# Flow Logs

## Acronym
* CW - CloudWatch

## Intro
* Flow data from VPC, subnet, or interface
* Sent to CW Logs or S3
* Flow is IP traffic in an aggregation interval
* Default or custom format
  * Custom on S3 only
  
---

## Limitations
* Can't change configuration of existing flow log
* Primary private IPv4 addrss logged as SrcAddr or DstAddr
* Certain types of traffic are not logged
* S3 bucket restrictions on opt-in regions
