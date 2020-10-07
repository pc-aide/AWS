# APIs

## Acronym
* IAM - Identity & Access Management

## Doc

## X-Ray Write APIs (used by the X-Ray daemon)
* **PutTraceSegments:** Uploads segment docuemtns to AWS X-Ray
* **PutTelemetryRecords:** used by the AWS X-Ray daemon to upload telemetry
    * SegmentsReceivedCount
    * SegmentsRejectedCounts
    * BackendConnectionErrors
* **GetSamplingRules:** Retrieve all sampling rules (to know what/when to send)
* GetSamplingTarget & GetSamplingStatisticSummaries: advanced
* The X-Ray daemon needs to have IAM policy authorizing the correct API calls to function correctly

* Example-API (IAM-Role):
````json
"Effect": "Allows",
"Action": [
  "xray:PutTraceSegments",
  "xray:PutTelemetryRecords",
  "xray:GetSamplingRules",
  "xray:GetSamplingTargets",
  "xray:GetSamplingStatisticSummaries"
],
"Resources":[
  "*"
]
````
* arn:aws:iam::aws:policy/AWSXrayWriteOnlyAccess

* **GetServiceGraph:** main graph
* **BatchGetTraces:** Retrieves a list of traces specified by ID. Each trace is a collection of segment documents 
  that originates from a single request
* **GetTraceSummaries:** Retrieves IDs & annotations for traces avaialble for a specified time frame using an
  optional filter. To get the full traces, pass the trace IDs to BatchGetTraces
* **GetTraceGRaph:** Retrieves a service graph for one or more specific trace IDs
* example.json (IAM-Role):
````json
"Effect": "Allow",
"Action": [
  "xray:GetSamplingRules",
  "xray:GetSamplingTargets",
  "xray:GetSamplingStatisticSummaries",
  "xray:BatchGetTraces",
  "xray:GetServiceGraph",
  "xray:GetTraceSummaries",
  "xray:GetGroups",
  "xray:GetGroup",
  "xray:GetTimeServicesServiceStatistics"
],
"Resources":[
  "*"
]
````
