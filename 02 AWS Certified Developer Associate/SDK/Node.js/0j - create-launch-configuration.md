# 0j - create-launch-configuration

## Demo 01 
### Steps
#### 01 - create-launch-configuration.js
````js
const AWS = require('aws-sdk')
const { resolve } = require('path')
const helpers = require('./helpers')

AWS.config.update({region: 'ca-central-1'})

// Declare local variables
const autoScaling = new AWS.AutoScaling()

const lcName = 'hamsterLC'
const roleName = 'hamsterLCRole'
// Must exist in our console
const sgName = 'hamster_sg'
// Must exist in our console:
const keyName = 'hamster_key'

helpers.createIamRole(roleName)
.then(profilArn => createLaunchConfiguration(lcName, profilArn))
.then(data => console.log(data))

// Functions
function createLaunchConfiguration (lcName, profilArn) {
  // Create a lanch configuration
  const params = {
    IamInstanceProfile: profilArn,
    // ami-id
    ImageId: 'ami-08357127fb45cdafa',
    InstanceType: 't2.micro',
    LaunchConfigurationName: lcName,
    keyName: keyName,
    SecurityGroups: [
      sgName
    ],
    UserData: 'IyEvYmluL2Jhc2gKYXB0LWdldCB1cGRhdGUKYXB0LWdldCAteSBpbnN0YWxsIGdpdApnaXQgY2xvbmUgaHR0cHM6Ly9naXRodWIuY29tL3J5YW5tdXJha2FtaS9oYmZsLmdpdApjZCBoYmZsCnN1ZG8gbnBtIGkKc3VkbyBucG0gcnVuIHN0YXJ0Cg=='
  }

  return new Promise((resolve, reject) => {
    autoScaling.createLaunchConfiguration(params, (err, data) => {
      if (err) reject(err)
      else resolve(data)
    })
  })
}
````

#### 02 - helper.js
````js
const AWS = require('aws-sdk')

function createSecurityGroup (sgName, port) {
  return new Promise((resolve, reject) => {
    const ec2 = new AWS.EC2()
    const params = {
      Description: sgName,
      GroupName: sgName
    }

    ec2.createSecurityGroup(params, (err, data) => {
      if (err) reject(err)
      else {
        const params = {
          GroupId: data.GroupId,
          IpPermissions: [
            {
              IpProtocol: 'tcp',
              FromPort: port,
              ToPort: port,
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
          else resolve(data.GroupId)
        })
      }
    })
  })
}

function createIamRole (roleName) {
  const profileName = `${roleName}_profile`
  const iam = new AWS.IAM()
  const params = {
    RoleName: roleName,
    AssumeRolePolicyDocument: '{ "Version": "2012-10-17", "Statement": [ { "Effect": "Allow", "Principal": { "Service": "ec2.amazonaws.com" }, "Action": "sts:AssumeRole" } ] }'
  }

  return new Promise((resolve, reject) => {
    iam.createRole(params, (err) => {
      if (err) reject(err)
      else {
        const params = {
          PolicyArn: 'arn:aws:iam::aws:policy/AdministratorAccess',
          RoleName: roleName
        }

        iam.attachRolePolicy(params, (err) => {
          if (err) reject(err)
          else {
            iam.createInstanceProfile({ InstanceProfileName: profileName }, (err, iData) => {
              if (err) reject(err)
              else {
                const params = {
                  InstanceProfileName: profileName,
                  RoleName: roleName
                }
                iam.addRoleToInstanceProfile(params, (err) => {
                  if (err) reject(err)
                  else {
                    // Profile creation is slow, need to wait
                    setTimeout(() => resolve(iData.InstanceProfile.Arn), 10000)
                  }
                })
              }
            })
          }
        })
      }
    })
  })
}

module.exports = {
  createIamRole,
  createSecurityGroup
}
````
[<img src="https://i.imgur.com/UfPrP4g.png">](https://i.imgur.com/UfPrP4g.png)
[<img src="https://i.imgur.com/k26KSaI.png">](https://i.imgur.com/k26KSaI.png)
[<img src="https://i.imgur.com/poc0n3k.png">](https://i.imgur.com/poc0n3k.png)
