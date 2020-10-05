# YAML Crash Course

## Acronym
* CF - CloudFormation

## Doc

## Intro
* YAML & json are the lanugages your can use for CloudFormation
* json is horrible for CF
* YAML is great in so mnay ways
* Key value
* Nested objects
* Support Arrays:
    * minus (sku, that means array)
* Multi line strings:
    * we have a vertial bar (|) this is called a multiline string
* Can include comments
    * # This is single line comment
* example.yml :
````yml
invoice:    34843
date   :    2001-01-23
bill-to:
    given   :   Chris
    family  :   Dumars
    address :   
        lines:  |
            458 Walkman Dr.
            Suite #292
        city    :   Royla Oak
        state   :   MI
        postal  :   48046
product:
    - sku         : BL394D
      quantity    :  4
      description : Basketball
      price       : 450.00
    - sku         : BL4438H
      quantity    : 1
      description : Super Hoop
      price       : 2392.00
````

* other example more real for yaml:
* ec2-with-sg-eip.yml
````yaml
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

* you can convert yaml -> json or reciprocity
