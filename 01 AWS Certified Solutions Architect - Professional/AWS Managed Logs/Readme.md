# AWS Managed Logs

## Acronym
* ALB - Application Load Balancer
* NLB - Network Load Balancer
* CLB - Classic Load Balancer
* LB - Load Balancer

## Intro
* LB Access Logs (ALB,NLB,CLB) => S3
  * Access logs for your LBs
* CloudTrail Logs -> S3 & CloudWatch Logs
  * Logs for API calls made within your account
* VPC Flow Logs -> S3 & CloudWatch Logs
  * Information about IP traffic going to & from network interfaces in your VPC
* Route 53 Access Logs -> CloudWatch Logs
  * Log information about the queries that Route 53 receives
* S3 Access Logs -> to another S3 (not on same bucket)
  * Server access logging provides detailed records for the requests that are made to a bucket
* CloudFront Access Logs -> S3
  * Detailed information about every usre request that CloudFront receives
* AWS Config -> s3
