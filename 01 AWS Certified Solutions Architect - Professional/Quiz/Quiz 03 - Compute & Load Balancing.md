# Quiz 03 - Compute & Load Balancing
1) You have software that will bill you based on the number of cores you're using. You must reboot the VM once every week to apply some critical security updates. You want to optimize pricing and make sure the instance licensing remains stable. How should you do it?
  * A. Book a rerved instance, & deploy the instance there
  * B. Book a dedicated host, & use host affinity
  * C. Book a dedicated host, & use a VM lock
  * D. Book a dedicated host, & use a placement group
2) You would like to automatically recover an instance in case of a fault on AWS' side. How should you do it?
  * A. Create a cron script on the instance to check the VM's health. Start an EC2 instance recovery from the script in case of issues
  * B. Create a CloudWatch event with a schedule to trigger a Lambda function regularly to check the VM's health using SSM Run Command. Start an EC2 instance recovery in case of issues
  * C. Create a CloudWatch Alarm checking the EC2'underlying CloudWatch Metrics. Trigger an EC2 intance recovery in case of issues
3) You have deployed an ALB + ASG and leverage DynamoDB as a DB technology. You would like to ensure the ASG terminates unhealthy EC2 instances, based on your application health. What do you recommend?
  * A. Enable EC2 instance internal status health checks & use that for the ASG
  * B. Create a route /health on the EC2 instances that check the internal health of the HTTP application
  * C. Create a route /posts-count that counts the number of posts in the DynamoDB table
  * D. Create a route /connection-db that checks if the application ca nread from DynamoDB
4) You have deployed an ALB + ASG and leverage DynamoDB as a DB technology. You would like to ensure the ASG terminates unhealthy EC2 instances, based on your application health. What do you recommend?
  * A. bridge
  * B. host
  * C. none
  * D. awsvpc
5) You plan on hosting multiple ECS services across your fleet of EC2 instances. Each service will need different permissions, to access AWS Config, AWS CloudWatch, DynamoDB and S3. Which security best practice should you follow?
  * A. Create an EC2 instance role with a policy per ECS service. Attach the role to the EC2 instance & launch your services
  * B. Create an EC2 instance role with the minimum ECS permissions. Create one IAM task role for each service & reference it in the task definition
  * C. Create one EC2 instance role per ECS service. Reference each EC2 instance role in the ECS task definitions
6) Your Lambda function is computation heavy and you need a better CPU to have better performance. What do you suggest?
  * A. Increase the vCPU for your Lambda function
  * B. Change your Lambda function instance type
  * C. Increase the Lambda function's RAM
  * D. Use a bustable Lambda function
7) From which service invocation will set up a Lambda DLQ be possible? 
  * A. API Gateway
  * B. SQS
  * C. SNS
8) Which of the following is true?
  * A. ALB has cross-zone balancing disabled by default & enabling it incurs no charge
  * B. ELB has cross-zone balancing disabled by default & enabling it incurs a charge
  * C. NLB has cross-zone balancing disabled by default & enabling it incurs a charge
9) Your API Gateway invokes a Lambda function which processes an image recursively. The lambda function's average processing time has been 25 seconds and therefore you have set a timeout limit at 1 minute. Recently, the API gateway has been returning 504 errors. What could be the source of the problem?
  * A. The Lambda function has failed
  * B. The API Gateway has a timeout
  * C. The Lambda function has a timeout
10) Which R53 record will minimize the network time between a server and a client?
  * A. Geolocation, & it has no failover capability
  * B. Geolocation, & it has failover capability
  * C. Latency, & it has no failover capability
  * D. Latency, & it has failover capability
11) How can you share a Route 53 private zone between multiple accounts?
  * A. Share it in Resource Access Manager (RAM)
  * B. Setup VPC peering & associate the VPC hosted zone
  * C. Setup Direct Connect between the VPC & associate the VPC hosted zone
  * D. Create an EC2 DNS proxy in the account with the private zone & map it to Route 53 in your other accounts
* [Answers](https://i.imgur.com/y3C86lF.png)
* Score:
  * [01-12-2020 PM] 8/11 = 72%
