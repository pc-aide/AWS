# Quiz 16 - Monitoring

## Questions
1) We'd like to have CloudWatch Metrics for EC2 at a 1 minute rate. What should we do?
    * Enable Custom Metrics
    * Enable High Resolution
    * Enable Basic Monitoring
    * Enable Detailed Monitoring
* [Answer](https://i.imgur.com/k9bMdCI.png)
2) High Resolution Custom Metrics can have a minimum resolution of
    * 1 second
    * 10 seconds
    * 30 seconds
    * 1 minute
* [Answer](https://i.imgur.com/g9n1acK.png)
3) To send a custom metric to CloudWatch, which API should we use?
    * SendMetricData
    * PutCustomMetric
    * SendCustomMetric
    * PutMetricData
* [Answer](https://i.imgur.com/1oqJetP.png)
4) Your CloudWatch alarm is triggered and controls an ASG. The alarm should trigger 1 instance being deleted from
   your ASG, but your ASG has already 2 instances running and the minimum capacity is 2. What will happen?
    * One instance will be deleted & the ASG capacity & minimum will go to 1
    * The alarm will remain in "ALARM" state but never decrease the number of instances in my ASG
    * The alarm will go in OK state
* [Answer](https://i.imgur.com/KnFvWVb.png)
5) An Alarm on a High Resolution Metric can be triggered as often as
    * 1 second
    * 10 seconds
    * 30 seconds
    * 1 minutes
* [Answer](https://i.imgur.com/EiQlFAM.png)
6) CloudWatch logs automatically expire after 7 days by default
    * False
    * True
* [Answer](https://i.imgur.com/x4Ryxmi.png)
7) CloudWatch Logs expiration policy should be defined at which level?
    * Log Groups
    * Log Streams
* [Answer](https://i.imgur.com/ZXC2GMf.png)
8) My application traces appear in X-Ray when I run the application on my local laptop. When I
   deploy my application to my Elastic Beanstalk, the traces do not appear in X-Ray. Why?
    * A config file is missing in **.ebextensions/** folder of your code
    * you need to authorize your application from the X-Ray console
    * your code is wrong
* [Answer](https://i.imgur.com/LpPZC57.png)
9) My application traces appear in X-Ray when I run the application on my local laptop. When I deploy
   my application to my EC2 instances with CodeDeploy, the traces do not appear in X-Ray. Why?
    * The CodeDeploy script breaks the X-Ray integration. It is a known bug
    * The X-Ray daemon is not running on the EC2 instance
    * The X-Ray integration needs to be enabled with CedeDeploy
* [Answer](https://i.imgur.com/aAFQbNG.png)
10) The X-Ray daemon is running on my EC2, and my application manages to send X-Ray traces from my computer,
    but it still doesn't work from my EC2 instance. What's wrong?
    * You need to enable input ports on your EC2 instance to allow UDP traffic in
    * Your IAM role for your EC2 instance doesn't have the required permissions to dend data to X-Ray
    * Your EC2 instance needs to be running in an ASG
* [Answer](https://i.imgur.com/APOj4eq.png)
11) All of a sudden, your CodePipeline breaks because it says it cannot find the target Elastic Beanstalk
    environment to deploy your application to. What should you do to find the root cause of this problem?
    * Look in CF for deletions
    * Look in CodePipeline for changes
    * Look in CloudTrail for a "delete" event in EB
* [Answer](https://i.imgur.com/gUBDKCU.png)
12) How should you configure the XRay daemon to send traces across accounts?
    * Create a user on another account, & export the access & secret keys to load them onto the agent
    * Create a role on another account, & allow a role in your account to assume that role
* [Answer](https://i.imgur.com/GOfSugb.png)
13) You would like to index your XRay traces in order to search and filter through them efficiently. What should you use?
    * Segment
    * Sampling
    * Annotations
    * Metadata
* [Answer](https://i.imgur.com/cPGjMYS.png)
14) You would like to use a service that would enable you to get cross-account tracing and visualization. Which service do you recommend?
    * VPC Flow Logs
    * AWS X-Ray
    * CloudWatch Logs
    * CloudTrail
* [Answer](https://i.imgur.com/y9qA634.png)
15) Which API is NOT used for writing to X-Ray?
    * BatchGetTraces
    * GetSamplingRules
    * PutTraceSegments
    * PutTelemetryRecords
* [Answer](https://i.imgur.com/Fx1JHM1.png)
