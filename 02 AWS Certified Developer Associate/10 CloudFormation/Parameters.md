# Parameters

## Acronym
* CF - CloudFormation

## Doc

## Intro
* Parameters are a way to provide **inputs** to your CloudFormatin template
* They're important to know about if:
    * You want to <ins>reuse</ins> your templates across the company
    * Som inputs can be determined ahead of time
* Parameters are extremely powerfull, controlled, & can prevent errors from happening in your templates thanks to types

---

## When should you use a parameter?
* Ask yourself this:
    * Is this CF resource configuration likely to change in the future?
    * If **yes**, make it a parameter

* example:
````yaml
Parameters:
  SecuirityGroupDescription:
    Description: Security Group Description
    (Simple parameter)
    Type: String
````

---

## Parameters Settings
* Parameters can be controlled by all these settings:
    * Type:
        * String
        * Number
        * CommaDelimitedList
        * List<Type>
        * AWS Parameter (to help catch invalid values - match against existing values in the AWS Account)
        * Description
        * Constraints
        * ConstraintDescription (String)
        * Min/MaxLength
        * Min/MaxValue
        * Defaults
        * AllowedValues (array)
        * AllowedPattern (regexp)
        * NoEcho (Boolean)
        
---

## How to Reference a Parameter
* The **Fn::Ref** function ccan be leveraged to reference parameters
* Parameters can be used anywhere in a template
* The shorthand for this YAML is **!Ref**

* Example.yaml:
````yaml
DbSubnet1:
  Type: AWS::EC2::Subnet
  Properties:
    VpcId: !Ref MyVPC
````

---

## Concept: Pseudo Parameters
* AWS offers us pseudo parameters in any CF template
* These can be used at any time & are enabled by default

| Reference Value       | Example Return Value                                                                            |
| --------------------- | ----------------------------------------------------------------------------------------------- |
| AWS::AcountId         | 1234567890                                                                                      |
| AWS::NotificationARNs | \[arn:aws:sns:us-east-1:123456789012:MyTopic\]                                                  |
| AWS::NoValue          | Does not return a value                                                                         |
| AWS::Region           | us-east-2                                                                                       |
| AWS::StackId          | arn:aws:cloudformation:us-east-1:12345678012:stack/MyStack/1c2fa630-082a-11e3-aff7-50e2416294e0 |
| AWS::StackName        | MyStack                                                                                         |

