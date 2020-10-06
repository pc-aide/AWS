# ChangeSets, Nested Stacks & StackSet

## Acronym
* LB - Load Balancer
* SG - Security Group
* CF - CloudFormation
* ALB - Application Load Balancer

## Doc
* [Updating stacks using change sets](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-changesets.html)

## ChangeSets
* When you update a stack, you need to know what chages before it happens for greater confidence
* ChangesSets won't say if the update will be successful

### Diagram
[<img src="https://i.imgur.com/ceTiNEO.png">](https://i.imgur.com/ceTiNEO.png)

---

## Nested stacks
* Nested stacks ar stacks as part of other stacks
* They allow you to isolate repeated patterns / common compnents in separate stacks & call them from other stacks
* Example:
    * LB configuration that is re-used
    * SG that is re-used
* Nested stacks are considered best practice
* To update a nested stack, always update th parent (root stack)

---

## CF - Cross vs Nested Stacks
* Cross Stacks
    * Helpful when stacks have different lifecycles
    * Use Outputs Export & Fn::ImportValue
    * When you need to pass export values to many stacks (VPC Id, etc...)
* Nested Stacks
    * Helpful when components must be re-used
    * Ex: re-use how to properly configure an ALB
    * The nested stack only is important to the higher level stack (it's not shared)
    
### Diagram
[<img src="https://i.imgur.com/jd6khR7.png">](https://i.imgur.com/jd6khR7.png)

---

## CF - StackSets
* Create, update, or delete stacks across **multiple accounts & regions** with a single operation
* Administrator account to create StackSets
* Trusted accounts to create, update, delete stack instances from StackSets
* When you update a stack set, all associated stack instances are updated throughout all accounts & regions

### Diagram
[<img src="https://i.imgur.com/XvtXmfR.png">](https://i.imgur.com/XvtXmfR.png)
