# Quiz 15 - CloudFormation

## Questions
1) To make your infrastructure created with CloudFormation evolve over time, you should do which of the following?
    * Change the resource manually in the AWS Console & your CF template will get automatically updated
    * Upload a new version of a CF template with the modified code & apply it in the CF Console
    * Create a new CF stack with the updated template
* [Answer](https://i.imgur.com/UpD4QQH.png)
2) Before being used by CloudFormation, your templates must be uploaded
    * Directly in CF
    * In AWS S3
    * In AWS CodeCommit
* [Answer](https://i.imgur.com/Y6VcZAJ.png)
3) You need to specify the order in which your CloudFormation template should create resources
    * True
    * False
* [Answer](https://i.imgur.com/eS9TenQ.png)
4) Which of the following is mandatory for a CloudFormation template?
    * Parameters
    * Resources 
    * Mappings
    * Outputs
* [Answer](https://i.imgur.com/oYhko7O.png)
5) Which intrinsic function should you use to retrieve the DNS name of a Load Balancer created with CloudFormation?
    * Fn::Ref
    * Fn::Sub
    * Fn::Join
    * Fn::GetAtt
* [Answer](https://i.imgur.com/OB0EOWL.png)
6) Considering these mappings:
````yml
    Mappings:
      AWSRegionArch2AMI:
        us-east-1:
          HVM64: ami-6869aa05
        us-west-2:
          HVM64: ami-7172b611
        us-west-1:
          HVM64: ami-31490d51
        eu-west-1:
          HVM64: ami-f9dd458a
     
      EnvironmentToInstanceType:
        development:
          instanceType: t2.micro
        production:
          instanceType: m4.large
````
And this Resources block:
````yml
    Resources:
      EC2Instance:
        Type: AWS::EC2::Instance
        Properties:
          InstanceType: !FindInMap [EnvironmentToInstanceType, !Ref 'EnvironmentName', instanceType]
          ImageId: !FindInMap [AWSRegionArch2AMI, !Ref 'AWS::Region', HVM64]
````
    * The parameter **AWS::Region** is missing so **!Ref 'AWS::REgion'** won't work
    * The **!FindInMap** function is using the wrong syntax. It should have 2 arguements ony
    * You cannot define two mappings in a template
    * The parameter **EnvironmentName** is missing
* [Answer](https://i.imgur.com/NcNI7n3.png)
7) The **!Ref** function can be used to reference the following except...
    * Parameters
    * Resources
    * Conditions
* [Answer](https://i.imgur.com/fdplw6S.png)
8) The following block:
````yml
Fn::Join:
    - ''
    - [IPAddress=, !Ref 'IPAddress']
````
   With the parameter IPAddress being 10.0.0.1.

   Will generate...
    * IPAddress, 10.0.0.1
    * IPAddress=10.0.0.1
    * IPAddress10.0.0.1
    * 10.0.0.1
* [Answer](https://i.imgur.com/ai6QzoU.png)
9) I'm trying to delete a stack but it seems I can't because other stacks reference its exported outputs. What should you do?
    * You're stuck
    * Delete the other stacks referencing the exported outputs first
    * Open a ticket with AWS Support
* [Answer](https://i.imgur.com/yc6B5nK.png)
10) I tried to create an exported output:
````yml
Outputs:
    StackSSHSecurityGroup:
        Description: The SSH Security Group for our Company
        Value: !Ref MyCompanyWideSSHSecurityGroup
        Export:
            Name: SSHSecurityGroup
````
   But it seems I get an error. It says "SSHSecurityGroup" output already exists. What should you do?
    * Exported output names must be unique within your region
    * The syntax is wrong
* [Answer](https://i.imgur.com/6Jc7HR8.png)
