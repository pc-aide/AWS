# Quiz 02 - Security

## Questions
1) Your application log is streaming from your EC2 instances to CloudWatch logs using the CloudWatch Unified Agent. You would like to set up alerts in case the words "REFUSED TRANSACTION" appear too many times in the log. How should you do it?
    * A. Setup a filter on the CloudWatch Unified agent to remove any logs lines that don't contain the words. Setup a CloudWatch Event to trigger an Alarm when a logline is sent to CloudWatch Logs
    * B. Setup a CloudWatch Logs Filter Metrics to filter the loglines & create a CloudWatch Alarm based on the defined threshold
    * C. Setup a CloudWatch Logs Filter Metrics to filter the loglines & create a CloudWatch Alarm based on any occurrence
    * D. Setup a filter on the CloudWatch Unided agent to pupulate a CloudWatch custom metric & create a Cloudwatch alarm based on that metric
2) You are trying to protect yourself the best way you can from Man In The Middle Attacks. What do you recommend doing?
    * A. Setup HTTP traffic & Route 53 DNS
    * B. Setup HTTPS & Route 53 DNS
    * C. Setup HTTP & third party DNS on EC2
    * D. Setup HTTPS & third party DNS on EC2
3) You are deploying a global application in 5 AWS regions using CloudFormation. Each region will be leveraging a classic Elastic Beanstalk architecture with an ALB and an ASG. You would like to deploy SSL certificates to each ALB to ensure your application is secure. How should you do it?
    * A. Create a certificate in ACM in us-east-1 & import it into each ALB
    * B. Create a certificate in ACM in each region & import them into their respective ALB
    * C. Import the certificate in SSM Parameter Store & use CloudFront & use CloudFormation to deploy the certificate to each ALB the use of Global Exports
4) You would like to ensure an IAM user only has access to specific keys in a CloudHSM cluster. How should you achieve this?
    * A. Create an IAM policy restricting access to a CloudHSM key & attach the policy to the IAM user
    * B. Create an SSM parameter with username/password for a user in CloudHSM that has access to the specific keys. Create an IAM policy restricting access to that SSM parameter & attach the policy to the IAM user
5) An EC2 instance in a public subnet is trying to access an Amazon S3 bucket. This EC2 instance often starts and stops. You would like to restrict access to that EC2 instance only. How can you do it?
    * A. Create an S3 bucket policy with a condition limiting access to the EC2 instance role
    * B. Create an S3 bucket policy with a condition limiting access to the EC2 public IP
    * C. Attach an EIP to the EC2 instance & create an S3 bucket policy with a condition limiting access to the EC2 EIP
    * D. Create an S3 bucket policy with a condition limiting access to the EC2 private IP
6) Your infrastructure is going under a DDoS attack and you have identified a patterned set of HTTP requests that are slowing down your servers. What should you use to mitigate the attack?
    * A. CloudFront
    * B. WAF
    * C. Shield
    * D. NACL
* [Answers](https://i.ibb.co/GP2TSbj/image.png)
* Score:
  * [27-10-2020 PM] 4/6 = 67%
