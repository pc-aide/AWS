# Demo - Placement Groups

## Acronym
* AZ - Availability Zone
* gp - general purpose

## Doc
* [Rules & limitations Placement groups](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html#placement-groups-cluster)

## Rules & Limits
### Cluster 
* instance types:
  * gp: A1, M4, M5, M5a, M5ad, ...
* Compute optimized:
  * C3,C4,C5,C5d,...
* Memory optimized:
  * cr1.8xlarge, R3, R4, R5, R5a, ...
* Storage Iptimized:
  * D2, H1, hs1.8xlarge, I2, I3, ...
* Accelerated computing:
  * F1, G2, G3, G4dn, Inf1, ...

## Console
* EC2\Placement Groups\Create placement group
  * Name:
  * Placement strategy:
  * Add tag (optional):
  
[<img src="https://i.imgur.com/CqHslKO.png">](https://i.imgur.com/CqHslKO.png)

* we can too CheckBox: palcement group into launch instance:

[<img src="https://i.imgur.com/5qxaStN.png">](https://i.imgur.com/5qxaStN.png)
[<img src="https://i.imgur.com/gDVx1zK.png">](https://i.imgur.com/gDVx1zK.png)

* Fleet of EC2 Instances
  * AZ: us-east-2b
  * Instance type: c5.large

[<img src="https://i.imgur.com/xNJyKQc.png">](https://i.imgur.com/xNJyKQc.png)
[<img src="https://i.imgur.com/vQ9dWTf.png">](https://i.imgur.com/vQ9dWTf.png)

---

## Partition Strategy
* Create Placement group
  * Name: PartitionGroupOne
  * Placement strategy: Partition
  * Number of partions: 3
  
[<img src="https://i.imgur.com/1wOTxCF.png">](https://i.imgur.com/1wOTxCF.png)

* Launch instance\Configure Instance
  * CheckBox: Add instance to placement group
  * Target partion: 1
  * AZ: us-east-2c
  
[<img src="https://i.imgur.com/Ac1qEFr.png">](https://i.imgur.com/Ac1qEFr.png)
[<img src="https://i.imgur.com/zQkHYAM.png">](https://i.imgur.com/zQkHYAM.png)

* launch instance again
  * RadioButton: Add to existing placement group
  * FieldBox: PartitionGroupOne (partition)
  * Subnet (AZ): us-east-2b
  * Target partion: 1
  
[<img src="https://i.imgur.com/RcKWkkA.png">](https://i.imgur.com/RcKWkkA.png)
[<img src="https://i.imgur.com/NPPYLxV.png">](https://i.imgur.com/NPPYLxV.png)

---

## AWS CLI
* List :
````sh
aws ec2 describe-instances \
--filters "Name = placement-group-name, Values = MyComputerCluster"
````

* filter:
````sh
aws ec2 describe-instances \
--filters "Name = placement-group-name, Value = PartitionGroupOne" "name = placement-partition-number, Values = 1"
````
