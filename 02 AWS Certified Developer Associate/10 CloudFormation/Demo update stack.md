# Demo update stack

## Acronym
* SG - Security Group
* EIP - Elastic IP

## Doc

## Intro
* First-Stack\Update:

[<img src="https://i.imgur.com/7YD5o2Q.png">](https://i.imgur.com/7YD5o2Q.png)

* Prepare template: Replace current template
* Template source: Upload a template file
* 1-ec2-with-sg-eip.yml
````yml
---
Parameters:
  SecurityGroupDescription:
    Description: Security Group Description
    Type: String

Resources:
  MyInstance:
    Type: AWS::EC2::Instance
    Properties:
      AvailabilityZone: us-east-1a
      ImageId: ami-a4c7edb2
      InstanceType: t2.micro
      SecurityGroups:
        - !Ref SSHSecurityGroup
        - !Ref ServerSecurityGroup

  # an elastic IP for our instance
  MyEIP:
    Type: AWS::EC2::EIP
    Properties:
      InstanceId: !Ref MyInstance

  # our EC2 security group
  SSHSecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      GroupDescription: Enable SSH access via port 22
      SecurityGroupIngress:
      - CidrIp: 0.0.0.0/0
        FromPort: 22
        IpProtocol: tcp
        ToPort: 22

  # our second EC2 security group
  ServerSecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      GroupDescription: !Ref SecurityGroupDescription
      SecurityGroupIngress:
      - IpProtocol: tcp
        FromPort: 80
        ToPort: 80
        CidrIp: 0.0.0.0/0
      - IpProtocol: tcp
        FromPort: 22
        ToPort: 22
        CidrIp: 192.168.1.1/32
````

[<img src="https://i.imgur.com/IBziy78.png">](https://i.imgur.com/IBziy78.png)

* Specify stack details
    * Parameter\ SecurityGroupDescription: SG-SSH-HTTP
* Change set preview
* upload stack

    
[<img src="https://i.imgur.com/dh8nj5O.png">](https://i.imgur.com/dh8nj5O.png)
[<img src="https://i.imgur.com/giOmEra.png">](https://i.imgur.com/giOmEra.png)
[<img src="https://i.imgur.com/Nh3HwfI.png">](https://i.imgur.com/Nh3HwfI.png)
[<img src="https://i.imgur.com/FuwCaKf.png">](https://i.imgur.com/FuwCaKf.png)

* Events:

[<img src="https://i.imgur.com/jcjGZMA.png">](https://i.imgur.com/jcjGZMA.png)
[<img src="https://i.imgur.com/CajnjdQ.png">](https://i.imgur.com/CajnjdQ.png)
[<img src="https://i.imgur.com/YQiaDF4.png">](https://i.imgur.com/YQiaDF4.png)
[<img src="https://i.imgur.com/SUqFWSB.png">](https://i.imgur.com/SUqFWSB.png)

* EC2:

[<img src="https://i.imgur.com/DCut6zv.png">](https://i.imgur.com/DCut6zv.png)
[<img src="https://i.imgur.com/Gg1uVeU.png">](https://i.imgur.com/Gg1uVeU.png)

* SGs:

[<img src="https://i.imgur.com/5qNDKkA.png">](https://i.imgur.com/5qNDKkA.png)

* First-Stack\Resources:

[<img src="https://i.imgur.com/v0ECrg6.png">](https://i.imgur.com/v0ECrg6.png)

* Delete: First-Stack:

[<img src="https://i.imgur.com/eDcS4tq.png">](https://i.imgur.com/eDcS4tq.png)
[<img src="https://i.imgur.com/49BRDE3.png">](https://i.imgur.com/49BRDE3.png)
