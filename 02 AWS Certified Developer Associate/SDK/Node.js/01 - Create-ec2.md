# Create-ec2

## Prereq

1. nodejs
2. aws configure

## Steps
### 01 - create-ec2.js

````js
// Load the AWS SDK for Node.js
var AWS = require('aws-sdk');
// Load credentials and set region from JSON file
AWS.config.update({region: '<REGION>'});

// Create EC2 service object
var ec2 = new AWS.EC2({apiVersion: '2016-11-15'});

// AMI is amzn-ami-2011.09.1.x86_64-ebs
var instanceParams = {
   ImageId: '<AMI_ID>', 
   InstanceType: 't2.micro',
   KeyName: '<KEY_PAIR_NAME>',
   MinCount: 1,
   MaxCount: 1
};

// Create a promise on an EC2 service object
var instancePromise = new AWS.EC2({apiVersion: '2016-11-15'}).runInstances(instanceParams).promise();

// Handle promise's fulfilled/rejected states
instancePromise.then(
  function(data) {
    console.log(data);
    var instanceId = data.Instances[0].InstanceId;
    console.log("Created instance", instanceId);

    // Handle promise's fulfilled/rejected states
  }).catch(
    function(err) {
    console.error(err, err.stack);
  });
````

### 02 - install dependence

* Nodejs:
````bash
npm install aws-sdk
````
[<img src="https://i.imgur.com/12Cmklh.png">](https://i.imgur.com/12Cmklh.png)

* launch 'create-ec2':
````bash
node create-ec2.js
````
[<img src="https://i.imgur.com/QL8a28s.png">](https://i.imgur.com/QL8a28s.png)
[<img src="https://i.imgur.com/PaldO0H.png"](https://i.imgur.com/PaldO0H.png)
