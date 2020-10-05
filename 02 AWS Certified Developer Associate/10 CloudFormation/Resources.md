# Resources

## Acronym
* CF - CloudFormation

## Doc
* [AWS resource and property types reference](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
* [AWS::EC2::Instance](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-ec2-instance.html)

## Intro
* Resources are the core of your CloudFormatin template (MANDATORY)
* They represent the different AWS Components that will be breated & configured
* Resources are declared & can reference each other
* AWS figures out creation, updates & deletes of resources for us
* There are over **224 types* of resources
* Resource type identifiers are of the form:
    * AWS::aws-product-name::data-type-name
    * ex:
        * AWS::EC2::Instance
        * AWS::EC2::EIP
        * AWS::EC2::SecurityGroup
    
---

## FAQ 
* <ins>Can I create a dynamic amount of recources?</ins>
    * No, you can't. Everything in the CF template has to be declared. You can't perform code generattion there
* Is every AWS Service supported?
    * Almost. Only a select fe niches are not there yet
    * You can work around that using Lambda Custom Resources
