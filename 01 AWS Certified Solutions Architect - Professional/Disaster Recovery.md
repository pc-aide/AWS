# Disaster Recovery

## Acronym
* DR - Disaster Recovery
* RPO - Recovery Point Objective
* RTO - Recovery Time Objective

## Intro
* Any event that has a negative impact on a company's business continuity or finances is a disaster
* DR is about preparing for & recovering from a disaster
* What kind of DR?
  * On-premise => On-premise: traditional DR, & very expensive
  * On-premise = > AWS Cloud: hybrid recovery
  * AWS Cloud Region A => AWS Cloud Region B
* Need to define two terms:
  * RPO: Recovery Point Objective
  * RTO: Recovery Time Objective
  
---

## RPO & RTO
[<img src="https://i.imgur.com/LBoWai6.png">](https://i.imgur.com/LBoWai6.png)

---

## DR Strategies
* Backup & Restore
* Pilot Light
* Warm Standby
* Hot Site/Multi Site Approach

### Diagram
[<img src="https://i.imgur.com/HFWbhJk.png">](https://i.imgur.com/HFWbhJk.png)

---

## Backup & Restore (High RPO)
[<img src="https://i.imgur.com/P6isKon.png">](https://i.imgur.com/P6isKon.png)

---

## DR - Pilot Light
* A small version of the app is always running in the cloud
* Useful for the critical core (pilot light)
* Very similar to Backup & Restore
* Faster than Backup & Restore as critical systems are already up
