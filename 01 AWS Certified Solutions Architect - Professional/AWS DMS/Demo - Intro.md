# Demo - Intro

## Acronym
* AZ - Availability Zone
* DMS - Database Migration Service
* KMS - Key Management Service
* SG - Security Group
* RDS - Relational Database Service

## Console
* Database migration serviceCreate replication instance

[<img src="https://i.imgur.com/KnXhjbg.png">](https://i.imgur.com/KnXhjbg.png)

* Replication instance configuration
  * Name:
  * Descriptive Amazon Resource Name (ARN) - optional:
  * Description:
  * Instance class
    * dms.t3.medium | 2 vCPU & 4GiB RAM
  * Engine version
  * Allocated Storage (GiB)
  * VPC
  * CheckBox
    * Multi AZ
    * Publicly accessible
  * Advanced security & network configuration
    * Replication Subnet group
    * AZ
    * VPC SG
    * KMS master key
  * Mantenance
    * Start day
    * Hour
    * Minute
    * Duration (hours)
    * RadioButon
      * Monitor version automatic upgrade
        * yes
        * no
  * Tags
    * Key
    * Value
    
[<img src="https://i.imgur.com/hlNBc3X.png">](https://i.imgur.com/hlNBc3X.png)
[<img src="https://i.imgur.com/VDgiRw5.png">](https://i.imgur.com/VDgiRw5.png)
[<img src="https://i.imgur.com/WoyxH9q.png">](https://i.imgur.com/WoyxH9q.png)
[<img src="https://i.imgur.com/1OZfHVT.png">](https://i.imgur.com/1OZfHVT.png)
[<img src="https://i.imgur.com/DD9Qz3i.png">](https://i.imgur.com/DD9Qz3i.png)

---

## Endpoint
* when done for create **Replication instances**, we need to 
  * **create Endpoint**
    * RadioButton
      * Source endpoint
      * Target endpoint
    * CheckBox
      * Select RDS instance
    * Endpoint configuration
      * Endpoint Identifier
      * Descriptive Amazon Name (ARN) - optional
      * Source engine
      * Extra connection attributes
    * KMS master key
    * Tags
    * Test endpoint connection (optional)
  
[<img src="https://i.imgur.com/13mBFS6.png">](https://i.imgur.com/13mBFS6.png)
[<img src="https://i.imgur.com/D3MhY5j.png">](https://i.imgur.com/D3MhY5j.png)
[<img src="https://i.imgur.com/IBAhe3H.png">](https://i.imgur.com/IBAhe3H.png)
[<img src="https://i.imgur.com/NBltLHx.png">](https://i.imgur.com/NBltLHx.png)

---

## Database Migration Task
* Create task
  * Task configuration
    * Task identifier
    * Descriptive Amazon Resource Name (ARN) - optional
    * Replication instance
    * Source database endpoint
    * Target database endpoint
    * List
      * Migration type
        * Migrate existing data 
        * Migrate existing data & replicate ongoing changes
        * Replicate data changes only
    * Task settings
      * RadioButton
        * Wizard
        * JSON editor
    * Premigration assessment
      * CheckBox
        * Enable premigration assessment run
    * Migration task startup configuration
      * RadioButton
        * Automatically on create
        * Manually later
    * Tags

[<img src="https://i.imgur.com/gNxfTGV.png">](https://i.imgur.com/gNxfTGV.png)
[<img src="https://i.imgur.com/1K0i4Fx.png">](https://i.imgur.com/1K0i4Fx.png)
[<img src="https://i.imgur.com/JvEYZGE.png">](https://i.imgur.com/JvEYZGE.png)
[<img src="https://i.imgur.com/WY8VSKr.png">](https://i.imgur.com/WY8VSKr.png)

---

## Notifications


[<img src="https://i.imgur.com/MEhBttm.png">](https://i.imgur.com/MEhBttm.png)
