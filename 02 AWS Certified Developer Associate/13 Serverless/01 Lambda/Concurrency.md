# Concurrency

## Acronym
* DLQ - Dead Letter Queue
* VPC - Virtual Private Cloud

## Doc
* [Announcing improved VPC networking for AWS Lambda functions](https://aws.amazon.com/blogs/compute/announcing-improved-vpc-networking-for-aws-lambda-functions/)
* [Managing concurrency for a Lambda function](https://docs.aws.amazon.com/lambda/latest/dg/configuration-concurrency.html)

## Concurrency & Throttling
* Concurrency limit: up to 1k cocurrent executions
* Can set a "**reserved concurrency**" at the function level (=limit)
* Each invocation over the concurrency limit will trigger a "Throttle"
* Throttle behavior:
    * If synchronous invocation => rerturn ThrottleError - 429
    * If asynchronous invocation => retry automatically & ten go to DLQ
* If you need a higher limit, open a support ticket

### Diagram
[<img src="https://i.imgur.com/tKFgfCD.png">](https://i.imgur.com/tKFgfCD.png)

---

## Concurrency Issue
* If you don't reserve (=limit) concurrency, the following can happen:
    * 
    
### Diagram
[<img src="https://i.imgur.com/M2G4QXN.png">](https://i.imgur.com/M2G4QXN.png)
[<img src="https://i.imgur.com/nQWgfqr.png">](https://i.imgur.com/nQWgfqr.png)
[<img src="https://i.imgur.com/2BrJmDz.png">](https://i.imgur.com/2BrJmDz.png)

---

## Concurrency & Asynchronous Invocations
* If the function doesn't have enough concurrency available to process all events,
  additional requests are **throttled**
* For throttling errors (429) & system errors (500-series), Lambda returns the event to the
  queue & attempts to run the function again for up to 6 hours
* The retry interval increase exponentially from 1s after the first attempt to a maximum of 5m

### Diagram
[<img src="https://i.imgur.com/OmJU0my.png">](https://i.imgur.com/OmJU0my.png)

---

## Cold Starts & Provisioned Concurrency
* Cold Start:
    * New instance => code is oaded & code outside the handler run (init)
    * If the init is large (code, dependencies, SDK...) this process can take some time
    * First request served by new instances has higher latency than the rest
* Provissioned Concurrency:
    * Concurrency is allocated before the function is invoked (in advance)
    * So the cold start never happens & all invocations have low latency
    * Application Auto Scaling can manage concurrency (schedule or target utilization)
* Note:
    * Note: cold starts in VPC have been dramatically reduced in Oct & Now 2019
    
---

## Reserved & Provisioned Concurrency
* 

### Diagram
[<img src="https://i.imgur.com/yACuB88.png">](https://i.imgur.com/yACuB88.png)
[<img src="https://i.imgur.com/biEnaLs.png">](https://i.imgur.com/biEnaLs.png)
