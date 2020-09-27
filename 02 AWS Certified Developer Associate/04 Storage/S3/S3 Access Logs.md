# S3 Access Logs

## Acronym

## Doc
* [Amazon S3 Server Access Log Format](https://docs.aws.amazon.com/AmazonS3/latest/dev/LogFormat.html)
* [put-bucket-logging](https://docs.aws.amazon.com/cli/latest/reference/s3api/put-bucket-logging.html)
* [Amazon S3 server access logging](https://docs.aws.amazon.com/AmazonS3/latest/dev/ServerLogs.html)

## Intro
* For audit purpose, you may want to log all access to S3 buckets
* Any request made to S3, from any account, authorized or denied, will be logged into another S3 bucket
* That data can be analyzed using data analysis tools ...
* Or Amazon Athena
* The log format is at @Doc

### Diagram
[<img src="https://i.imgur.com/4LHv0NE.png">](https://i.imgur.com/4LHv0NE.png)

---

## S3 Access Logs: Warning
* Don't set your logging bucket to be the monitored bucket
* It will create a logging loop, & your **bucket will grow in size exponentially**
* Seperate always your application_bucket & log_bucket - not together

### Diagram
[<img src="https://i.imgur.com/dcxrQvA.png">](https://i.imgur.com/dcxrQvA.png)

---

## Demo
* Create Bucket-log
````bash
aws s3 mb s3://demo-01-access-logs
aws s3 mb s3://demo-01-monitored
````

* Server access logging: 

[<img src="https://i.imgur.com/BDYb6w0.png">](https://i.imgur.com/BDYb6w0.png)

````bash
aws s3api get-bucket-logging --bucket demo-01-monitored
````
[<img src="https://i.imgur.com/UWHr6m0.png">](https://i.imgur.com/UWHr6m0.png)

````bash
aws s3api put-bucket-versioning --bucket demo-01-monitored --versioning-configuration Status=Enabled
````

````bash
# upload a few files & delete it
aws s3 cp cat.png s3://demo-01-monitored
aws s3 cp beach.jpeg s3://demo-01-monitored
aws s3 rm s3://demo-01-monitored/cat.jpg
# encrypted 
aws s3 cp s3://demo-01-monitored/beach.jpeg s3://demo-01-monitored/beach.jped --sse AES256
````
[<img src="https://i.imgur.com/WLmDrvW.png">](https://i.imgur.com/WLmDrvW.png)

* all things should in logs (other bucket)
````bash
aws s3 ls s3://demo-01-access-logs
````
[<img src="https://i.imgur.com/596ldxY.png">](https://i.imgur.com/596ldxY.png)
[<img src="https://i.imgur.com/ldzQga2.png">](https://i.imgur.com/ldzQga2.png)
[<img src="https://i.imgur.com/3H74zIm.png">](https://i.imgur.com/3H74zIm.png)
