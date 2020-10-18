# Step Functions

## Acronym
* ECS - Elastic Container Service

## Doc

## Intro
* Build severless **visual workflow** to orchestrate your Lambda functions
* Represent flow as a json **state machine**
* Features: sequence, parallel, conditions, timeouts, error handling...
* Can also integrate with EC2, ECS, On premise servers, API Gateway
* Maximum execution time of 1 year
* Possibility to implement human approval feature
* Use cases:
    * Order fulfillment
    * Data processing
    * Web applications
    * Any workflow
    
---

## Visual workflow in Step Functions
[<img src="https://i.imgur.com/AciBL3g.png">](https://i.imgur.com/AciBL3g.png)

---

## Error Handling
* Any state can encounter runtime erros for various reasons:
    * State machine definition issues (for example, no matching rule in a Choice state)
    * Task failures (for example, an exception in la Lambda function)
    * Transient issues (for example, network partition events)
* By default, when a state reports an error, AWS Step Functions causes the execution to fail entirely
* **Retrying failures - Retry**: IntervalSeconds, MaxAttempts, BackoffRate
* **Movin on - Catch**: ErrorEquals, Next
* Best practice is to include data in the error messages

---

## Standard vs Express
|                                 | Standard Workflows                                                                                                                                                                                         | Express Workflows                                                                                |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Maximum duration                | 1 year                                                                                                                                                                                                     | 5 minutes                                                                                        |
| Supported execution start rate  | Over 2k per second                                                                                                                                                                                         | Over 100k per second                                                                             |
| Supported state transition rate | Over 4k per second per account                                                                                                                                                                             | Nearly unlimited                                                                                 |
| Pricing                         | Priced per state transition. A state transition is<br>counted each time a step in your execution is<br>completed (more expensive)                                                                          | Priced by the number of executions you run,<br>their duration, & memory consumption<br>(cheaper) |
| Execution history               | Executions can be listed & described with Step<br>Function APIs, & visually debugged through<br>the console. They can also be inspected in<br>CloudWatch Logs by enabling logging on your<br>state machine | Executions can be inspected in CloudWatch<br>Logs by enabling logging on your state<br>machine   |
| Execution semantics             | Exactly-once workflow execution                                                                                                                                                                            | At-least-once workflow execution                                                                 |

