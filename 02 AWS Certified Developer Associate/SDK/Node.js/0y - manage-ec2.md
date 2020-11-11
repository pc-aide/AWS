# 06 - manage-ec2

## Demo-01 Basic
### Steps
#### 01 - manage-ec2.js
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

#### 02 - node
````js
node manage-ec2.js
````
[<img src="https://i.imgur.com/JOl5rmI.png">](https://i.imgur.com/JOl5rmI.png)
[<img src="https://i.imgur.com/hHEyPhr.png">](https://i.imgur.com/hHEyPhr.png)

---

## Demo-02 more O/P attirubes
### Steps
#### 01 - manage-ec2.js
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
      else {
        // new array
        resolve(data.Reservations.reduce((i,r) => {
          return i.concat(r.Instances)
        }, []))

      } 
    })
  })
}

listInstances()
.then(data => console.log(data))
````
[<img src="https://i.imgur.com/PNBDQpF.png">](https://i.imgur.com/PNBDQpF.png)

---

## Demo-03 Terminate
### Steps
#### 01 - manage-ec2.js
````js
// Imports
const AWS = require('aws-sdk')

AWS.config.update({ region: 'ca-central-1' })

// Declare local variables
const ec2 = new AWS.EC2()

// Functions
function terminateInstance (instanceId) {
  const params = {
    InstanceIds: [
      instanceId
    ]
  }

  return new Promise((resolve, reject) => {
    ec2.terminateInstances(params, (err, data) => {
      if (err) reject(err)
      else resolve(data)
    })
  })
}

terminateInstance('i-0ec62451e254b9b4b')
.then(data => console.log(data))
````
[<img src="https://i.imgur.com/gGaW7xb.png">](https://i.imgur.com/gGaW7xb.png)
