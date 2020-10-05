# OutPuts

## Acronym
* CF - CloudFormation
* VPC - Virtual Private Cloud
* SG - Security Group

## Doc

## Intro
* The Outputs section declare optional outputs values that we can import into other stacks (if you export them first)!
* You can also view the outputs in the AWS Console or in using the AWS CLI
* They're very useful for example if you define a network CF, & output the variables such as VPC ID & your Subnet IDs
* It's the best way to perform some collaboration corss stack, as you let expert handle their own part of the stack
* You can't **delete a CF Stack** if its outputs are being **referenced** by another CF stack
* Outputs Example.yml
    * Creating a SSH Security Group as part of one template
    * We create an output that references that SG
````yml
Outputs:
    StackSSHSecurityGroup:
        Description: The SSH Security Group for our Company
        Value: !Ref MyCompanyWideSSHSecurityGroup
        Export:
            Name:   SSHSecurityGroup
````

---

## Cross Stack Reference
* We then create a second template that leverages that SG
* For this, we use the **Fn::ImportValue** function
* You **can't delete** the underlying stack until all the **references** are deleted too
* secondTemplate.yml:
````yml
Resources:
    MySecureInstance:
        Type: AWS::EC2::Instance
        Properties:
            AvaialbilityZone: us-east-1a
            ImageId: ami-a4c7edb2
            InstanceType: t2.micro
            SecurityGroups:
                - !ImportValue SSHSecurityGroup
````

