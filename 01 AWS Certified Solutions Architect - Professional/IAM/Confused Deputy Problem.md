# Confused Deputy Problem

## Intro
* Used extID to control "Bad Actor" in your organization
* e.g. policy:
````json
"Condition": {
  "StringEquals": {
    "sts:ExternalId":
      "GUID1"
  }
}
````

* Table

|n|Customer|Role ARN    |ExternalID|
|-|--------|------------|----------|
|1|You     | PerfMonitor|GUID1     |
|2|BadActor| PerfMonitor|GUID2     |

* BadActor assume role with own GUID2, refuse vs assume with your ID


[<img src="https://i.imgur.com/oNQmDg8.png">](https://i.imgur.com/oNQmDg8.png)
