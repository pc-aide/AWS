# Rollbacks

## Acronym
* SG - Security Group

## Doc
* [Monitor and roll back stack operations](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-rollback-triggers.html?icmpid=docs_cfn_console)

## Intro
* Stack Creation Fails:
    * Default: everything rolls back (gets deleted). We can look a the log
    * Option to disable rollback & troubleshoot what happened
* Stack Update Fails:
    * The stack automatically rolls back to the previous know working state
    * Ability to see in the log what happened & error messages
    
---

## Demo
* Create stack
    * Prepare template: Template is ready
    * Template source: Upload a template file
    * ec2-with-sg-eip.yaml:
````yaml
---
---
Resources:
  MyInstance:
    Type: AWS::EC2::Instance
    Properties:
      AvailabilityZone: us-east-1a
      ImageId: ami-a4c7edb2
      InstanceType: t2.micro
````

[<img src="https://i.imgur.com/7Xhqi5T.png">](https://i.imgur.com/7Xhqi5T.png)

* Stack name: Failure-Demo
* Create stack

[<img src="https://i.imgur.com/OJ4pQsK.png">](https://i.imgur.com/OJ4pQsK.png)

* Update this stack
* Prepare template: Replace current template
* Template source: upload a template file
* trigger-failure.yml:
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
      ImageId: ami-123456
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

[<img src="https://i.imgur.com/4j3olUz.png">](https://i.imgur.com/4j3olUz.png)
[<img src="https://i.imgur.com/4eQOano.png">](https://i.imgur.com/4eQOano.png)

* update stack:

[<img src="https://i.imgur.com/FT0DqkI.png">](https://i.imgur.com/FT0DqkI.png)

* Events:

[<img src="https://i.imgur.com/UsE54JK.png">](https://i.imgur.com/UsE54JK.png)

* Logical ID\MyInstance
    * image id: "ami-123456" does not exist
    
[<img src="https://i.imgur.com/f78XAep.png">](https://i.imgur.com/f78XAep.png)

* Update_rollback_complete:
    * delete 2x SGs
    
[<img src="https://i.imgur.com/T1p85XY.png">](https://i.imgur.com/T1p85XY.png)

---

## CloudFormation
* Create new stack

[<img src="https://i.imgur.com/GMvGOZW.png">](https://i.imgur.com/GMvGOZW.png)

* Prepare template: Template is ready
* Template source: Upload a template file
* failure-trigger.yml:
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
      ImageId: ami-123456
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

* stack name: Failure-Demo-2

[<img src="https://i.imgur.com/6tHdigK.png">](https://i.imgur.com/6tHdigK.png)

* Stack creation options:

[<img src="https://i.imgur.com/5PDnXQ6.png">](https://i.imgur.com/5PDnXQ6.png)

* Events
    * everything will be delete
    
[<img src="https://i.imgur.com/CRs4W8a.png">](https://i.imgur.com/CRs4W8a.png)

* Resources

[<img src="https://i.imgur.com/gJA5zm6.png">](https://i.imgur.com/gJA5zm6.png)

* Stacks 
    * 2x stacks: rollback_complete & update_rollback_complete
    
[<img src="https://i.imgur.com/FRIiMus.png">](https://i.imgur.com/FRIiMus.png)
