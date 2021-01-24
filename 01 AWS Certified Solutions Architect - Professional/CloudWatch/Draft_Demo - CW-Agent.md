# Demo - CW-Agent.md

## Acronym
* CW - CloudWatch

## Steps
### 01 - IAM-User
* Create a user
  * Name: CW-Agent
  * Access type: Programmatic access

[<img src="https://i.imgur.com/UN1swqs.png">](https://i.imgur.com/UN1swqs.png)

* Create a policy
* Attach this policy to your user: CW-Agent
* New poilicy (code)
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "cloudwatch:PutMetricData",
        "logs:PutLogEvents",
        "logs:DescribeLogStreams",
        "logs:DescribeLogGroups",
        "logs:CreateLogStream",
        "logs:CreateLogGroup"
      ],
      "Resource": "*"
    },
    {
      "Effect": "Allow",
      "Action": [
        "ssm:GetParameter"
      ],
      "Resource": "arn:aws:ssm:*:*:parameter/AmazonCloudWatch-*"
    }
  ]
}
````

[<img src="https://i.imgur.com/VulEB9w.png">](https://i.imgur.com/VulEB9w.png)
[<img src="https://i.imgur.com/yMHcS4w.png">](https://i.imgur.com/yMHcS4w.png)

---

### 02 - VM (On-prem)
* install awscli2
* configure with Access KeyID (CW-Agent)

[<img src="https://i.imgur.com/qx61RuO.png">](https://i.imgur.com/qx61RuO.png)

* Download CW-Agent
  * `wget https://s3.amazonaws.com/amazoncloudwatch-agent/amazon_linux/amd64/latest/amazon-cloudwatch-agent.rpm`
  
[<img src="https://i.imgur.com/dlbu04F.png">](https://i.imgur.com/dlbu04F.png)
[<img src="https://i.imgur.com/awDrmJO.png'>](https://i.imgur.com/awDrmJO.png)

* Install
  * `rpm -U ./amazon-cloudwatch-agent.rpm`
  
[<img src="https://i.imgur.com/RhsF0yd.png">](https://i.imgur.com/RhsF0yd.png)

---

### 03 - Cfg CW-Agent
* Wizard:
  * `/opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-config-wizard`
  
[<img src="https://i.imgur.com/nOoQQDV.png">](https://i.imgur.com/nOoQQDV.png)
[<img src="https://i.imgur.com/Mh5wXFG.png">](https://i.imgur.com/Mh5wXFG.png)
[<img src="https://i.imgur.com/vxGMWsX.png">](https://i.imgur.com/vxGMWsX.png)
[<img src="https://i.imgur.com/1CMEl5g.png">](https://i.imgur.com/1CMEl5g.png)
[<img src="https://i.imgur.com/nioor1c.png">](https://i.imgur.com/nioor1c.png)

* Start CW-Agent
````sh
/opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a fetch-config -m onPremise -c file:/opt/aws/amazon-cloudwatch-agent/bin/config.json -s
````

[<img src="https://i.imgur.com/8eULkCq.png">](https://i.imgur.com/8eULkCq.png)

* Error :
  * Unable to determinie aws-region
  
[<img src="https://i.imgur.com/EoMY87i.png">](https://i.imgur.com/EoMY87i.png)

* `aws configure --profile AmazonCloudWatchAgent`

[<img src="https://i.imgur.com/wrnbGRh.png">](https://i.imgur.com/wrnbGRh.png)

* to test if successfully
  * `tail -f /opt/aws/amazon-cloudwatch-agent/logs/amazon-cloudwatch-agent.log`
