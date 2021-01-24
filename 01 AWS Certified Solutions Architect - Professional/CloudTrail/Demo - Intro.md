# Demo - Intro

## Console
* CloudTrail\Dashboard

[<img src="https://i.imgur.com/JQr87L1.png">](https://i.imgur.com/JQr87L1.png)

---

## Event history
* CloudTrail allows us to view the **last 90 days** of events within
  * if you want more 90d, so create trail (use S3 as storage)

[<img src="https://i.imgur.com/2I77HWB.png">](https://i.imgur.com/2I77HWB.png)
[<img src="https://i.imgur.com/aCZfIxP.png">](https://i.imgur.com/aCZfIxP.png)

* View event
````json
{
    "eventVersion": "1.08",
    "userIdentity": {
        "type": "IAMUser",
        "principalId": "...",
        "arn": "arn:aws:iam::...:user/CW-Agent",
        "accountId": "...",
        "accessKeyId": "...",
        "userName": "CW-Agent"
    },
    "eventTime": "2021-01-24T21:14:35Z",
    "eventSource": "logs.amazonaws.com",
    "eventName": "CreateLogGroup",
    "awsRegion": "...",
    "sourceIPAddress": "11.22.33.44",
    "userAgent": "CWAgent/1.247347.3 (go1.15.6; linux; amd64) No Build Date inputs:(diskio net cpu logfile mem socket_listener statsd swap disk) outputs:(cloudwatch cloudwatchlogs)",
    "requestParameters": {
        "logGroupName": "secure"
    },
    "responseElements": null,
    "requestID": "62e8744e-0e07-4328-8928-49a789eba36e",
    "eventID": "31f697cc-89ea-4be9-af95-27b312d65648",
    "readOnly": false,
    "eventType": "AwsApiCall",
    "apiVersion": "20140328",
    "managementEvent": true,
    "eventCategory": "Management",
    "recipientAccountId": "..."
}
````
