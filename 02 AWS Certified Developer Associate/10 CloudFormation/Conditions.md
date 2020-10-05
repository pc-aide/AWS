# Conditions

## Acronym

## Doc

## Intro
* Conditions are used to control the creation of resources or outputs based on a condition
* Conditions can be whatever you want them to be, but common ones are:
    * Environment (dev, test, prod)
    * AWS Region
    * Any parameter value
* Each condition can reference another condition, parameter value or mapping

---

## How to define a condition?
* Example.yaml:
````yml
Conditions:
    CreateProdResources: !Equals [ !Ref EnvType, prod]
````
* The logical ID is for you to choose. It's how you name condition
* The intrinsic function (logical) can be any of the following:
    * Fn::And
    * Fn::Equals
    * Fn::If
    * Fn::Not
    * Fn::Or
    
---

## Using a Condition
* Conditions can be applied to resources / outputs /etc...
* example.yml:
````yml
Resources:
    MountPoint:
        Type: "AWS::EC2::VolumeAttachment"
        Condition: CreateProdResources
````
