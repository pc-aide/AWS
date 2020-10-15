# Integration Types & Mappings

## Doc

## Acronym
* SQS - Simple Queue Service
* VTL - Velocity Template Language

## Integration Types
* Integration Type **MOCK**
    * API Gateway **returns a response** without sending the request to the backend
        * for DEV & TEST
* Integration type **HTTP/AWS (Lambda & AWS Services)**
    * forwarded, e.g. EC2
    * you must confiugure both the integratin request & integration response
    * Setup data mapping using **mapping templates** for the request & response
* Integration type **AWS_PROXY (Lambda Proxy)**:
    * incoming request from the client is the input to Lambda (X-Forwarded-For externe IP)
    * The function is responsible for the logic of reuest/response
    * **No mapping templae, headers, query string parameters... are passed as arguments
* Lambda function invocatin payload:
````json
{
    "resource": "Resource path",
    "path": "Path parameter",
    "httpMehtod": "Incoming request's method name",
    "headers": "String containing incoming request headers",
    "multiValueHeaders": "List of strings containing incoming",
    "queryStringParameters": "query string parameters ",
    "multiValueQueryStringParameters": "List of query string",
    "pathParameters": "path parameters",
    "stageVariables": "Applicable stage variables",
    "requestContext": "Request context, including authorizer",
    "body": "A JSON string of the request payload.",
    "isBased64Encoded": "A boolean flag"
}
````
* Lambda function expected response:
````json
{
  "isBase64Encoded": "true|false",
  "statusCode": "httpStatusCode",
  "headers": { "headerName": "headerValue", ...},
  "multiValueHeaders": { "headerName": ["headerValue", "header..."]},
  "body": "..."
}
````
* Integration Type **HTTP_PROXY**
    * No mapping template
    * The HTTP request is passed to the backend
    * The HTTP response from the backend is forwarded by API Gateway
    
### Diagram
[<img src="https://i.imgur.com/eUEbfkR.png">](https://i.imgur.com/eUEbfkR.png)
[<img src="https://i.imgur.com/4eJclLT.png">](https://i.imgur.com/4eJclLT.png)

---

## Mapping Templates (AWS & HTTP Integration)
* Mapping templates can be used to modify request/responses
* Rename/Modify **query string parameters**
* Modify **bod content**
* **add headers**
* Use VTL: for loop, if etc...
    * scripting language to modify some requests
* Filter output results (remove unnecessary data)

---

## Mapping Example: JSON to XML with SOAP
* SOAP API are XML based, whereas REST API are JSON based
* In this case, API Gateway should:
    * Extract data from the request: either path, payload or header
    * Build SOAP message based on request data (mapping template)
    * Call SOAP service & receive XML response
    * Transform XML response to desired format (like JSON), & respond to the user

### Diagram
[<img src="https://i.imgur.com/XtXHTOP.png">](https://i.imgur.com/XtXHTOP.png)

---

## Mapping Example: Query String parameters
[<img src="https://i.imgur.com/t000kHB.png">](https://i.imgur.com/t000kHB.png)
