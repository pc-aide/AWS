# mon-put-instance-data.pl

## IAM Role - EC2ForCloudWatch
````json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Stmt1426849513000",
            "Effect": "Allow",
            "Action": [
                "cloudwatch:GetMetricStatistics",
                "cloudwatch:ListMetrics",
                "cloudwatch:PutMetricAlarm",
                "cloudwatch:PutMetricData",
                "cloudwatch:SetAlarmState"
            ],
            "Resource": [
                "*"
            ]
        }
    ]
}
````

## User data
````bash
#!/bin/bash
apt-get update
apt-get upgrade -y
apt-get install -y libwww-perl libdatetime-perl unzip
cd /opt/
wget http://aws-cloudwatch.s3.amazonaws.com/downloads/CloudWatchMonitoringScripts-1.2.1.zip
unzip CloudWatchMonitoringScripts-1.2.1.zip
rm CloudWatchMonitoringScripts-1.2.1.zip
cd aws-scripts-mon
cp awscreds.template awscreds.conf
echo "*/5 * * * * root /opt/aws-scripts-mon/mon-put-instance-data.pl --disk-space-used --disk-path=/ --from-cron" > /etc/cron.d/cloudwatch-monitor
chmod +x /etc/cron.d/cloudwatch-monitor
systemctl restart cron
````

## Metric (CloudWatch)
* after ~15min

[<img src="https://i.imgur.com/QkM5wEk.png">](https://i.imgur.com/QkM5wEk.png)
