# 0X - 2 files (instance + keypair)

## github
* [hbfl](https://github.com/ryanmurakami/hbfl)

## Prereq

1. aws configure
2. nodejs

## Steps
### 01 create-ec2.js
````js
// Imports
const AWS = require('aws-sdk')
const NEWKEYPAIR = require('./NewKeyPair')

AWS.config.update({ region: 'ca-central-1' })

// Declare local variables
const ec2 = new AWS.EC2()
const sgName = 'hamster_sg2'
const keyName = 'hamster_key2'

// Do all the things together
createSecurityGroup(sgName)
.then(() => {
  return createKeyPair(keyName)
})
.then(helpers.persistKeyPair)
.then(() => {
  return createInstance(sgName, keyName)
})
.then((data) => {
  console.log('Created instance with:', data)
})
.catch((err) => {
  console.error('Failed to create instance with:', err)
})

// Create functions

function createSecurityGroup (sgName) {
  const params = {
    Description: sgName,
    GroupName: sgName
  }

  return new Promise((resolve, reject) => {
    ec2.createSecurityGroup(params, (err, data) => {
      if (err) reject(err)
      else {
        const params = {
          GroupId: data.GroupId,
          IpPermissions: [
            {
              IpProtocol: 'tcp',
              FromPort: 22,
              ToPort: 22,
              IpRanges: [
                {
                  CidrIp: '0.0.0.0/0'
                }
              ]
            }, {
              IpProtocol: 'tcp',
              FromPort: 3000,
              ToPort: 3000,
              IpRanges: [
                {
                  CidrIp: '0.0.0.0/0'
                }
              ]
            }
          ]
        }
        ec2.authorizeSecurityGroupIngress(params, (err) => {
          if (err) reject(err)
          else resolve()
        })
      }
    })
  })
}

function createKeyPair (keyName) {
  const params = {
    KeyName: keyName
  }

  return new Promise((resolve, reject) => {
    ec2.createKeyPair(params, (err, data) => {
      if (err) reject(err)
      else resolve(data)
    })
  })
}

function createInstance (sgName, keyName) {
  const params = {
    ImageId: 'ami-0c2f25c1f66a1ff4d',
    InstanceType: 't2.micro',
    KeyName: keyName,
    MaxCount: 1,
    MinCount: 1,
    SecurityGroups: [
      sgName
    ],
    UserData: 'IyEvYmluL2Jhc2gNCnN1ZG8gYXB0LWdldCB1cGRhdGUNCnN1ZG8gYXB0LWdldCAteSBpbnN0YWxsIGdpdA0KZ2l0IGNsb25lIGh0dHBzOi8vZ2l0aHViLmNvbS9yeWFubXVyYWthbWkvaGJmbC5naXQgL2hvbWUvYml0bmFtaS9oYmZsDQpjaG93biAtUiBiaXRuYW1pOiAvaG9tZS9iaXRuYW1pL2hiZmwNCmNkIC9ob21lL2JpdG5hbWkvaGJmbA0Kc3VkbyBucG0gaQ0Kc3VkbyBucG0gcnVuIHN0YXJ0'
  }

  return new Promise((resolve, reject) => {
    ec2.runInstances(params, (err, data) => {
      if (err) reject(err)
      else resolve(data)
    })
  })
}

````

### 02 NewKeyPair.js
````js
const fs = require('fs')
const path = require('path')
const os = require('os')

function persistKeyPair (keyData) {
  return new Promise((resolve, reject) => {
    const keyPath = path.join(os.homedir(), '.ssh', keyData.KeyName)
    const options = {
      encoding: 'utf8',
      mode: 0o600
    }

    fs.writeFile(keyPath, keyData.KeyMaterial, options, (err) => {
      if (err) reject(err)
      else {
        console.log('Key written to', keyPath)
        resolve(keyData.KeyName)
      }
    })
  })
}

module.exports = {
  persistKeyPair
}
````

### 03 install dependencies

1. depend.:
````bash
npm install aws-sdk
````
[<img src="https://i.imgur.com/Z1dMWKS.png">](https://i.imgur.com/Z1dMWKS.png)

2. start:
````bash
node create-ec2.js
````
[<img src="https://i.imgur.com/hH3UyQR.png">](https://i.imgur.com/hH3UyQR.png)
[<img src="https://i.imgur.com/x6f36mw.png">](https://i.imgur.com/x6f36mw.png)
[<img src="https://i.imgur.com/CWh0pgp.png">](https://i.imgur.com/CWh0pgp.png)
[<img src="https://i.imgur.com/cfKTV4c.png">](https://i.imgur.com/cfKTV4c.png)
[<img src="https://i.imgur.com/plqnxap.png">](https://i.imgur.com/plqnxap.png)
