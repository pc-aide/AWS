# Mappings

## Doc

## Acronym
* CF - CloudFormation
* AMI - Amazon Machine Image
* AZ - Availability Zone

## Intro
* Mappings are fixed variables within your CF template
* They're very handy to differentiate between different environments (dev vs prod), regions (AWS regions), AMI types, etc
* All the values are hardcoded within the template
* Example:
````yaml
Mappings:
  Mapping01:
  Key01:
    Name: Value01
  Key02:
    Name: Value02
  Key03:
    Name: Value03
````
````yml
RegionMap:
  us-east-1:
    "32": "ami-6411e20d:
    "64": "ami-7a11e213"
  us-west-1:
    "32": "ami-c9c7978c"
    "64": "ami-cfc7978a"
  eu-west-1:
    "32": "ami-37c2f643"
    "64": "ami-31c2f645"
````

---

## When would you use mappings vs parameters?
* Mappings are great when you know in advance all the values that can be taken & that they can be deduced from variables such as:
    * Region
    * AZ
    * AWS Account
    * Environment (dev vs prod)
    * Etc
* They allow safer control over the template
* Use parameters when the values are really user specific

---

## Fn::FindInMap Accessing Mapping Values
* We use **Fn::FindInMap** to return a named value from a specific key
* **!FindInMap [ Mapname, TopLevelKey, SecondLevelKey ]**
* example.yaml:
````yml
AWSTEmplateFormatVesion: "2010-09-09"
Mappings:
    RegionsMap:
        us-east-1:
            "32": "ami-6411e20d"
            "64": "ami-7a11e213"
        us-west-1:
            "32":  "ami-c9c7978c"
            "64":  "ami-31c2f645"
        ap-southeast-1:
            "32":  "ami-66f28c34"
            "64":  "ami-60f28c32"
        ap-northeast-1:
            "32":  "ami-9c03a89d"
            "64":  "ami-a003a8a1"
Resources:
    myEC2Instance:
        Type:  "AWS::EC2::Instance"
        Properties:
            ImageId: !FindInMap [RegionMap, !Ref "AWS::Region", 32]
            InstanceType: m1.small
````
