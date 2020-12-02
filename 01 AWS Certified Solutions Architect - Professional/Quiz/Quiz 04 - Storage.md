# Quiz 04 - Storage

## Questions
1) You have a 3 TB gp2 EBS volume mounted onto an m5.large EC2 instance and you would like to get an increase of 3000 IOPS in performance. What do you recommend doing?
   * A. Mount a 2nd EBS volume as RAID 0
  * B. Mount a 2nd EBS volume as RAID 1
  * C. Increase the EBS drive by 1TB
  * D. Upgrade the EC2 instance type
2) You would like to get a POSIX networking file system for your on-premise VMs. What do you recommend doing?
  * A. Create an NLB with a fleet of EC2 instances with EBS volumes. Use the NLB as a mount target
  * B. Provision EFS
  * C. Create a multi-AZ EBS volume
  * D. Use Storage Gateway Volumes
3) What is the most cost-efficient way of serving static content from AWS? 
  * A. ALB + EC2
  * B. CloudFront + S3
  * C. NLB + EC2
  * D. EC2 with EIP + EFS
4) You want to migrate an on-premise Java HTTP web application to AWS. What do you recommend as the most cost-efficient and optimized option?
  * A. Migrate the Java web application to S3
  * B. Migrate the Java web application to EB
  * C. Migrate the dynamic part of the Java web application to EC2 + ALB & the static content to S3
5) You would like to build a metadata index of Amazon S3 objects in DynamoDB, but some objects already exist in Amazon S3. The metadata information of each object is in the first 8000 bytes of the object. What do you recommend for future and past objects? 
  * A. Past Objects: fetch the object entirely from an AWS Lambda function & extract the index data Future Objects: create a CloudWatch Event to trigger a Lambda function every 5 minutes to extract the metadata
  * B. Past Objects: fetch the object partially from an AWS Lambda function using an S3 byte-range fetch & extract the index data
  * C. Past Objects: fetch the object partially from an AWS Lambda function using an S3 byte-range fetch & extract the index data
  * D. Past Objects: fetch the object entirely from an AWS Lambda function & extract the index data Future Objects: create an S3 event for new objects to trigger the previous Lambda function
* [Answers](https://i.imgur.com/lYoqoDW.png)
* Score:
  * [ 2-12-2020 AM] 3/5 = 60%
