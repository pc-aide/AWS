# Demo

## Acronym

## Doc
* [AWS Step Functions increases payload size to 256KB](https://aws.amazon.com/about-aws/whats-new/2020/09/aws-step-functions-increases-payload-size-to-256kb/)

## Console
* Get started

[<img src="blob:https://imgur.com/66a1cda8-85bc-4f1d-9e58-1d7899e65475">](blob:https://imgur.com/66a1cda8-85bc-4f1d-9e58-1d7899e65475)

* Hello World example:
````json
{
  "Comment": "A Hello World example demonstrating various state types of the Amazon States Language",
  "StartAt": "Pass",
  "States": {
    "Pass": {
      "Comment": "A Pass state passes its input to its output, without performing work. Pass states are useful when constructing and debugging state machines.",
      "Type": "Pass",
      "Next": "Hello World example?"
    },
    "Hello World example?": {
      "Comment": "A Choice state adds branching logic to a state machine. Choice rules can implement 16 different comparison operators, and can be combined using And, Or, and Not",
      "Type": "Choice",
      "Choices": [
        {
          "Variable": "$.IsHelloWorldExample",
          "BooleanEquals": true,
          "Next": "Yes"
        },
        {
          "Variable": "$.IsHelloWorldExample",
          "BooleanEquals": false,
          "Next": "No"
        }
      ],
      "Default": "Yes"
    },
    "Yes": {
      "Type": "Pass",
      "Next": "Wait 3 sec"
    },
    "No": {
      "Type": "Fail",
      "Cause": "Not Hello World"
    },
    "Wait 3 sec": {
      "Comment": "A Wait state delays the state machine from continuing for a specified time.",
      "Type": "Wait",
      "Seconds": 3,
      "Next": "Parallel State"
    },
    "Parallel State": {
      "Comment": "A Parallel state can be used to create parallel branches of execution in your state machine.",
      "Type": "Parallel",
      "Next": "Hello World",
      "Branches": [
        {
          "StartAt": "Hello",
          "States": {
            "Hello": {
              "Type": "Pass",
              "End": true
            }
          }
        },
        {
          "StartAt": "World",
          "States": {
            "World": {
              "Type": "Pass",
              "End": true
            }
          }
        }
      ]
    },
    "Hello World": {
      "Type": "Pass",
      "End": true
    }
  }
}
````

[<img src="https://i.imgur.com/WloPyr5.png">](https://i.imgur.com/WloPyr5.png)

* Create state machine

[<img src="https://i.imgur.com/t245InT.png">](https://i.imgur.com/t245InT.png)
[<img src="https://i.imgur.com/Qx7LLRY.png">](https://i.imgur.com/Qx7LLRY.png)

* New execution
    * start execution

[<img src="https://i.imgur.com/BJXGSNY.png">](https://i.imgur.com/BJXGSNY.png)
[<img src="https://i.imgur.com/g3bJswN.png">](https://i.imgur.com/g3bJswN.png)

* New execution
    * Input
      * change true to false
      
[<img src="https://i.imgur.com/g4AYrAx.png">](https://i.imgur.com/g4AYrAx.png)
[<img src="https://i.imgur.com/2IiQbgC.png">](https://i.imgur.com/2IiQbgC.png)

* Back to HelloWorkd\
    * Executions (n)
    * Type: **Standard** (flow)

[<img src="https://i.imgur.com/USyAvq2.png">](https://i.imgur.com/USyAvq2.png)

* Go back one level (State machines)
    * create state machine
      

[<img src="https://i.imgur.com/fJZ5DO2.png">](https://i.imgur.com/fJZ5DO2.png)
[<img src="https://i.imgur.com/1OA24Dc.png">](https://i.imgur.com/1OA24Dc.png)

* Run a sample projects

[<img src="https://i.imgur.com/2ySlhFZ.png">](https://i.imgur.com/2ySlhFZ.png)
[<img src="https://i.imgur.com/8zI5aGv.png">](https://i.imgur.com/8zI5aGv.png)

* Start with template
    * Retry failure
    
[<img src="https://i.imgur.com/DrZAdia.png">](https://i.imgur.com/DrZAdia.png)
[<img src="https://i.imgur.com/NJt1RrF.png">](https://i.imgur.com/NJt1RrF.png)

* Catch Failure

[<img src="https://i.imgur.com/ERMLa8Q.png">](https://i.imgur.com/ERMLa8Q.png)
