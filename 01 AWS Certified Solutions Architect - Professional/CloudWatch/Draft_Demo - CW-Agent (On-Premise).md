# CW-Agent (On-Premise)

## Acronym
* SSM - System Manager

## OS ver
* CentOS7

---

## Steps
### 01 - New user
* Create this user - On-Premise (VM)
  * Name: cwagent
* Create this policy & attach it to the user: cwagent
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
* Record Access key id + secret access key for later...

---

### 02 - awscli2
````sh
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
````

---

### 03 - cwagent.rpm
* download cwagent
* rpm -U --updgrade
````sh
wget https://s3.amazonaws.com/amazoncloudwatch-agent/amazon_linux/amd64/latest/amazon-cloudwatch-agent.rpm
sudo rpm -U ./amazon-cloudwatch-agent.rpm
````

---

### 04 - aws configure --prfile
* `aws configure --profile AmazonCloudWatchAgent` -profile "AmzonCloudWatchAgent" extremely important (case sensitive)

---

### 05 - CollectD folder missing (optional)
* if dont' have this folder (collectD )
````sh
suod mkdir -p /usr/share/collectd/
sudo touch /usr/share/collectd/types.db
````

---

### 06 - common-config.toml (optional)
* Edit config file if used not root:
  * `vim /opt/aws/amazon-cloudwatch-agent/etc/common-config.toml`
* Uncomment :
  * Ln8 -> [credentials]
* Put our profile & cred:
  * `shared_credential_profile = "AmazonCloudWatchAgent"`
  * `shared_credential_file = "/home/cwagent/.aws/credentials"`

---

### 08 - UTC (Amazon Time Sync)
* UTC & not ntp
  * `sudo yum erase 'ntp*'`
  * `sudo systemctl restart chronyd`

### 07 - config-wizard
* `sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-config-wizard`
  1) On which OS are you planning to use the agent?
    * 1. linux
  2) Are you using EC2 or On-Premises hosts?
    * 2. On-Premises
  3) Which user are you planning to run the agent?
    * cwagent
  4) Do you want to turn on StatsD daemon?
    * yes
  5) Which port do you want StatsD daemon to listen to?
    * [default] 8125
  6) What is the collect interval fo StatsD daemon?
    * 10s
  7) What is the aggregation interval for metrics collected by StatsD daemon?
    * 60s
  8) Do you want to minitor metrics from collectD?
    * yes
  9) Do you to monitor any host metrics? e.g. CPU, memory, etc
    * yes
  10) Do you want to monitor cpu metric per core? Additional CloudWatch charges may apply
    * yes
  11) Would you like to collect your metrics at high resolution (sub-minute resolution)? This enables sub-minute resolution for all metrics, but yu can customize for specific metrics in the output json file
    * 60s
  12) Which default metrics config do you want?
    * Basic
  Review ... in json
  13) Do you have any existing CloudWatch Log Agent (Do you have any existing CloudWatch Log Agent (http://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/AgentReference.html) configuration file to import for migration?
    * no
  14) Do you want to monitor any log files?
    * yes
    * log file path: /var/log/secure
    * Log group name:
      * secure
    * Log stream name:
      * [{hostname}]
  15) Do you want to specify any additional log files to monitors?
    * no
  16) Do you want to store the config in the SSM parameter store?
    * no

---

### 07 - chown /var/log/secure
* permission to cwagent (user)
  * `sudo chown cwagent:cwagent /var/log/secure`
---

### 08 - Start CW-Agent
* Switchs
  * -s --start agent
  * Service:
* `sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a fetch-config -m onPremise -c file:/opt/aws/amazon-cloudwatch-agent/bin/config.json -s`


* To test our CWAgent work !?
  * `tail -f /opt/aws/amazon-cloudwatch-agent/logs/amazon-cloudwatch-agent.log `

* if not error
  * O/P:

[<img src="https://i.imgur.com/NWW57ur.png">](https://i.imgur.com/NWW57ur.png)

---

### 09 - CW\Metrics\CWAgent

[<img src="https://i.imgur.com/im7SOYv.png">](https://i.imgur.com/im7SOYv.png)
[<img src="https://i.imgur.com/nAvd7NN.png">](https://i.imgur.com/nAvd7NN.png)

* Path
 * /run/user/0
 
[<img src="https://i.imgur.com/wHSSAfJ.png">](https://i.imgur.com/wHSSAfJ.png)
