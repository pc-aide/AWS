# Intrinsic Functions

## Doc
* [AWS resource and property types reference](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
* [AWS::EC2::Instance](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-ec2-instance.html)
    * [Return values](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-ec2-instance.html#aws-properties-ec2-instance-return-values)

## Acronym
* AZ - Availability Zone

## Intro
* Ref
* Fn::GetAtt
* Fn::FindInMap
* Fn::ImportValue
* Fn::Join
* Fn::Sub
* Condition Functions (Fn::If, Fn::Not, Fn::Equals, etc)

---

## Fn::Ref
* The **Fn::Ref** function can be leveraged to reference
    * Parameters => returns the value of the parameter
    * Resources => returns the physical ID of the underlying resource
        * ex: EC2 ID
* The shorthand for this YAML is **!Ref**
* example.yml:
````yml
DbSubnet1:
    Type: AWS::EC2::Subnet
    Properties:
        VpcId: !ref MyVPC
````

---

## Fn-GetAtt
* Attributes are attached to ny resources you create
* To know the attributes of your resources, the best place to look at is the doc
* For example: the AZ of an EC2 machine
* example.yml:
````yml
Resources:
    EC2Instance:
        Type: "AWS::EC2::Instance"
        Properties:
            ImageId: ami-1234567
            InstanceType: t2.micro
````
````yml
NewVolume:
    Type: "AWS::EC2::Volume"
    Condition: CreateProResources
    Properties:
        Size: 100
        AvailabilityZone:
            !GetAtt EC2Instance.AvailabilityZone
````

---

## Fn::FinInMap Accessing Mapping Values
* We use **Fn::FindInMap** to return a named value form a specific key
* **!FindInMap [ MapName, topLevelKey, SecondLevelKey ]**
* example.yml:
````yml
AWSTemplateFromatVersion: "2010-09-09"
Mappings:
    RegionMap:
        us-east-1:
            "32": "ami-6411e20d"
            "64": "ami-7a11e213"
        us-west-1:
            "32": "ami-c9c7978c"
            "64": "ami-7a11e213"
        eu-west-1:
            "32": "ami-37c2f643"
            "64": "ami-31c2f645"
        ap-southeast-1:
            "32": "ami-66f28c34"
            "64": "ami-60f28c32"
        ap-northeast-1:
            "32": "ami-9c3a89d"
            "64": "ami-a003a8a1"
Resources:
    myEC2Instance:
        Type: "AWS::EC2::Instance"
        Properties:
            ImageId: !FindInMap [RegionMap, !Ref "AWS::Region", 32]
            InstanceType: m1.small
````

---

## Fn::ImportValue
* Import values that are exported in other templates
* For this, we use the **Fn::ImportValue** function
* Example.yml:
````yml
Resources:
    MySecureInstance:
        Type: AWS::EC2::Instance
        Properties:
            AvailabilityZone: us-east-1a
            ImageId: ami-a4c7edb2
            InstanceType: t2.micro
            SecurityGroups:
                - !ImportValue SSHSecurityGroup
````

---

## Fn::Join
* Join values with a delimiter
* example.yml:
````yml
!Join [ delimiter, [ comma-delimited list of values] ]
````
* This create "a:b:c"
````yml
!Join [ ":", [ a, b, c] ]
````

---

## Function Fn::Sub
* ** Fn::Sub**, or **!Sub** as a shorthand, is used to substitute variables from a text. It's very handy function
   that will allow you to fully customize your templates
* For example, you can combine **Fn::Sub** with References or AWS Pseudo variables
* **String** must contain **${VariableName}** & will substitute them
* example.yml:
````yml
!Sub
    - String
    - { Var1Name: Var1Value, Var2Name, Var2Value }
````
````yml
!Sub String
````

---

## Condition Functions
example.yml:
````yaml
Conditions:
    CreateProResources: !Equals [ !Ref EnvType, prod ]
````
* The logical ID is for you to choose. It's how you name condition
* The intrisinc function (logical) can be any of the following:
      * Fn::And
      * Fn::Equals
      * Fn::If
      * Fn::Not
      * Fn:: Or
