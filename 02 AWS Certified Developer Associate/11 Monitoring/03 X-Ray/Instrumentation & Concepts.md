# Instrumentation & Concepts

## Acronym
* IAM - Identity & Access Management
* ARN - Amazon Resource Name

## Doc

## X-Ray Instrumentation in your code
* **Instrumentation** means the measure of product's performance, diagnose errors, & to write trace information
* To instrument your application code, your use **X-Ray SDK**
* Example for Node.js & Express
````bash
var app = express();

var AWSXRay = require('aws-xray-sdk');
app.use(AWSXRay.express.openSegment('MyApp'));

app.get('/', function (req, res) {
  res.render('index');
});

app.use(AWSXRay.express.closeSegment());
````

* Many SDK require only configuration changes
* You can modifiy your application code to customize & annotation the data that the SDK sends to X-Ray, using 
  **interceptors, filters, handlers, middleware..**
  
---

## X-Ray Concepts
* <ins>Segments:</ins> each application/ service will send them
* <ins>Subsegments:</ins> if your need more details in your segment
* <ins>Trace:</ins> segments collected together to form an end-to-end trace
* <ins>Sampling:</ins> decrease the amount of requests sent to X-Ray, reduce cost
* <ins>Annotations:</ins> Key Value pairs used to **index** traces & use wih **filters**
* <ins>Metada:</ins> Key Valu pairs, <ins>not</ins> **indexed**, not used for searching
* The X-Ray daemon/ agent has a config to send traces cross account:
    * make sure the IAM permissions ar e correct - the agent will assume the role
    * This allows to have a central account for all your application tracing
    
---

## X-Ray Sampling Rules
* With sampling rules, you control the amount of data that your record
* You can modify sampling rules without changing your code
* By default, the X-Ray SDK records the first request **each second**, & **five percent** of any additional requests
* **One request per second is the reservoir**, which ensures that at least one trace is recorded each second as long the 
  service is serving requests
* **Five perceint is the rate** at which additional requests beyond the reservoir size are sampled

---

## X-Ray Custom Sampling Rules
* You can create your own rules with the **reservoir** & **rate**
* example:
````text
Example Higher minimum rate for POSTs
  * Rule name - POST minimum
  * Priority - 100
  * Reservoir - 10
  * Rate - 0.10
  * Service name - *
  * Service type - *
  * Host - *
  * HTTP method - POST
  * URL path - *
  * Resource ARN - *
````
* debug:
````text
Example Debugging rule tor trace all request for a problematic route
A high-priority rule applied temporarily for debugging
  * Rule name - DEBUG - history updates
  * Priority - 1
  * Reservoir - 1
  * Rate - 1
  * Service name - Scorekeep
  * Service type - *
  * Host - *
  * HTTP method - PUT
  * URL path - /hitory/*
  * Resource ARN - *
````
