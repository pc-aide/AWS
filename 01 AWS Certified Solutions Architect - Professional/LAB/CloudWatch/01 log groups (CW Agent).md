# 01 log groups (CW Agent).md

## Youtube
* [AWS - CloudWatch Logs](https://www.youtube.com/watch?v=F4IE69V-iuw)

## Steps
### 01 - IAM 
* New Policy: EC2ForLogGroups(CW)
  * Description EC2 For CloudWatch Agent (Log groups)
````json
{
  "Version": "2012-10-17",
  "Statement":[
    {
      "Effect": "Allow",
      "Action": [
        "logs:CreateLogGroup",
        "logs:CreateLogStream",
        "logs:PutLogEvents",
        "logs:DescribeLogStreams"
      ],
      "Resource": [
        "arn:aws:logs:*:*:*"
      ]
    }
  ]
}
````

* New IAM Role = Policy

### 02 - EC2
* User Data
````bash
#!/bin/bash
yum update -y
yum install -y awslogs
# log cfg
echo \
"[general]
state_file = /var/lib/awslogs/agent-state
[application_logs]
region = ca-central-1
datetime_format = %b %d %H:%M:%S
file = /var/log/application.log
buffer_duration = 5000
log_stream_name = {instance_id}
initial_position = start_of_file
log_group_name = application_logs" > /etc/awslogs/awslogs.conf
# update region (cfg CW Agent)
sed -i 's/.*region.*/region = ca-central-1/' /etc/awslogs/awscli.conf
# service
systemctl start awslogsd.service
systemctl enable awslogsd.service
# dump log
echo "dummy log data" > /var/log/application.log
````

## Cloudwatch
* log groups\application_logs:

[<img src="https://i.imgur.com/fGnE9v8.png">](https://i.imgur.com/fGnE9v8.png)

## Create Metric Filter
* ...
* Metric Name: AppError
