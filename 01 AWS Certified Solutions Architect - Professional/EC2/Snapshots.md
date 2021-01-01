# Snapshots

## Acronym
* EBS - Elastic Block Store

## Diagram
[<img src="https://i.imgur.com/FKs4iXP.png">](https://i.imgur.com/FKs4iXP.png)

---

## Lifecycle
* Schedule
  * Every 12 or 24 hours
* Delete
  * Age-based or rolling number of snapshots
* Tags
  * Identify instances & volumes to include
  
---

## Encryption
* Snapshots of encrypted volumes are automatically encrypted
* Volumes you crate from encrypted snapshots are automatically encrypted
* Volumes your create from an **unencrypted** snapshot can be encrypted **on-the-fly**
* When you copy an **unencrypted** snapshot, you can encrypt it during the copy process
* You can **re-encrypt** an **encrypted** snapshot with a **different key**
