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
const NewKeyPair = require('./NewKeyPair')

AWS.config.update({ region: 'ca-central-1' })

// Declare local variables
const ec2 = new AWS.EC2()
const sgName = 'hamster_sg2'
const keyName = 'hamster_key2'

// Do all the things together
createSecurityGroup(sgName)
.then(() => {
  // keypair: /homme/<userName>/.ssh/<privateKey>
  return createKeyPair(keyName)
})
.then(NewKeyPair.persistKeyPair)
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
          // Inbound
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
    // bootstrap in base64 for Amazon v2 (centOS7)
    UserData: 'IyEvYmluL2Jhc2gKeXVtIC15IHVwZGF0ZQp5dW0gLXkgaW5zdGFsbCBnaXQKY3VybCAtc0wgaHR0cHM6Ly9ycG0ubm9kZXNvdXJjZS5jb20vc2V0dXBfMTAueCB8IHN1ZG8gYmFzaCAtCnl1bSBpbnN0YWxsIC15IG5vZGVqcwpnaXQgY2xvbmUgaHR0cHM6Ly9naXRodWIuY29tL3J5YW5tdXJha2FtaS9oYmZsLmdpdCAvaG9tZS9iaXRuYW1pL2hiZmwKY2hvd24gLVIgYml0bmFtaTogL2hvbWUvYml0bmFtaS9oYmZsCmNkIC9ob21lL2JpdG5hbWkvaGJmbApucG0gdXBkYXRlCm5wbSBpCm5wbSBydW4gc3RhcnQKCg=='
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
      // permissions (rw)
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

### 04 O/P
* it will take couple time (**~3min**) before to see our web page

[<img src="https://i.imgur.com/zMfBZG8.png">](https://i.imgur.com/zMfBZG8.png)
