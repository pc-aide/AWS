# SWF

## Acronym
* SWF - Simple Work Flow

## Intro
* old service
  * Step Function (substitute)
* Coordinate work amongst appliations
* Code runs on EC2 (**not serverless**)
* 1 year max runtime
* Concept of "activity step" & "decision step"
* Has built-in "human intervention" step
* Example: order fulfilment from web to warehouse to delivery
* **Step Functions is recommended to be usef for new applications, execpt:**
  * If you need external signals to intervene in the processes
  * If you need child processes that return values to parent processes
  * If you need to use **Amazon Mechanical Turk**
