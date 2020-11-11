# 06 - manage-ec2

## Steps
### 01 - manage-ec2.js
````js
// Imports
// Import the aws-sdk
const AWS = require('aws-sdk')
const { resolve } = require('path')

// Configure region
AWS.config.update({ region: 'ca-central-1'})

// Declare local variables
// Create an ec2 object
const ec2 = new AWS.EC2()

function listInstances () {
  // List instances using ec2.describeInstances()
  return new Promise((resolve, reject) => {
    ec2.describeInstances({}, (err, data) => {
      if (err) reject(err)
      else resolve(data)
    })
  })
}

function termnateInstance (instanceId) {
  // TODO: terminate an instance with a given instanceId
}

listInstances()
.then(data => console.log(data))
// termnateInstance()
// .then(data => console.log(data))
````

### 02 - node
````js
node manage-ec2.js
````
[<img src="https://i.imgur.com/JOl5rmI.png">](https://i.imgur.com/JOl5rmI.png)
[<img src="https://i.imgur.com/hHEyPhr.png">](https://i.imgur.com/hHEyPhr.png)
