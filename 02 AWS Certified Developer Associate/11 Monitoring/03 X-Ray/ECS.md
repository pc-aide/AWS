# ECS

## Acronym
* ECS - Elastic Container Service

## Doc
* [X-Ray-daemon-ecs-build](https://docs.aws.amazon.com/xray/latest/devguide/xray-daemon-ecs.html#xray-daemon-ecs-build)

## ECS + X-Ray integration options
* ECS Cluster
    * X-Ray Container as a Daemon
* ECS Cluster
      * X-Ray Container as a "Side Car"
* Fargate Cluster
      * X-Ray Container as a "Side Car"

### Diagram
[<img src="https://i.imgur.com/nEELfUg.png">](https://i.imgur.com/nEELfUg.png)

---

## ECS + X-Ray: Example Task Definition
1) block portMappings
2) block Environment 
      * AWS_XRAY_DAEMON_...
3) block links
* Example Task definition: 
````json

    {
      "name": "xray-daemon",
      "image": "123456789012.dkr.ecr.us-east-2.amazonaws.com/xray-daemon",
      "cpu": 32,
      "memoryReservation": 256,
      "portMappings" : [
          {
              "hostPort": 0,
              "containerPort": 2000,
              "protocol": "udp"
          }
       ],
    },
    {
      "name": "scorekeep-api",
      "image": "123456789012.dkr.ecr.us-east-2.amazonaws.com/scorekeep-api",
      "cpu": 192,
      "memoryReservation": 512,
      "environment": [
          { "name" : "AWS_REGION", "value" : "us-east-2" },
          { "name" : "NOTIFICATION_TOPIC", "value" : "arn:aws:sns:us-east-2:123456789012:scorekeep-notifications" },
          { "name" : "AWS_XRAY_DAEMON_ADDRESS", "value" : "xray-daemon:2000" }
      ],
      "portMappings" : [
          {
              "hostPort": 5000,
              "containerPort": 5000
          }
      ],
      "links": [
        "xray-daemon"
      ]
    }
````

### Screenshot
[<img src="https://i.imgur.com/Jemx6kX.png">](https://i.imgur.com/Jemx6kX.png)
