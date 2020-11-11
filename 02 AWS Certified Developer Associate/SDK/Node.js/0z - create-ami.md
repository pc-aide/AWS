# 0z - create-ami

## Demo 01 - basic
### Steps
#### 01 - create-ami.js
* we have instanceId with state: running
````js
// Imports
// Import the aws-adk
const AWS = require('aws-sdk')

// Configure region
AWS.config.update({region: 'ca-central-1'})

// Declare local variables
// Create an ec2 object
const ec2 = new AWS.EC2()

createImage('i-07cd4239ee95f9bdb','hamsterImage')
.then(() => console.log('Complete'))

// functions
function createImage (seedInstanceId, imageName) {
  // Implement AMI creation
  const params = {
    InstanceId: seedInstanceId,
    Name: imageName
  }

  return new Promise((resolve, reject) => {
    ec2.createImage(params, (err, data) => {
      if (err) reject(err)
      else resolve(data)
    })
  })
}
````
[<img src="https://i.imgur.com/bEQ6ZyQ.png">](https://i.imgur.com/bEQ6ZyQ.png)
[<img src="https://i.imgur.com/6QE2i5H.png">](https://i.imgur.com/6QE2i5H.png)
