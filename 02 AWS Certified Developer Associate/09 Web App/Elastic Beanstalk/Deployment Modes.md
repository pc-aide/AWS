# Deployment Modes

## Acronym
* prd - production
* HA - High Availability
* LB - Load Balancer
* ASG - Auto-Scaling Group


## Doc
* [Deploying applications to Elastic Beanstalk environments](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.deploy-existing-version.html)

## Intro
*  **single Instance** - Great for **dev**
    * Beanstalk {first, second} env
* **HA with LB** - Great for **prd**

### Diagram
[<img src="https://i.imgur.com/jGLJfrO.png">](https://i.imgur.com/jGLJfrO.png)

---

## Beanstalk Deployment Options for Updates
* **All at once (deployment all in one go)** - fastest, but instances aren't available to serve traffic for a bit (**downtime*)
* **Rolling**: update a few instances at a time (bucket), & them move onto the next bucket once the first bucket is healthy
* **Rolling with additional batches**: like rolling, but spins up new instances to move the batch (so that the old app is still available)
* **Immutable**: spins up new instances in a new ASG, deploys version to these instances, & then swaps all the instances when everything is healthy 

---

## Beanstalk Deployment All at once
* Fastest deployment
* Application has downtime
* Great for quick iterations in development environment
* No additional cost

### Diagram
[<img src="https://i.imgur.com/IhTI1Jk.png">](https://i.imgur.com/IhTI1Jk.png)

---

## Beanstalk Deployment Rolling
* App is running below capacity
* Can set the bucket size
* App is running both version simultaneously
* No additional cost
* Long deployment
    * ex: ~100 apps (instances) & small bucket size

### Diagram
[<img src="https://i.imgur.com/FqC6mKP.png">](https://i.imgur.com/FqC6mKP.png)

---

## Beanstalk Deployment Rolling with additional batches
* App is running at capacity
* Can set the bucket size
* App is running both versions simultaneously
* Small additional cost
* Additonal batch is removed at the end of the deployment
* Longer deployment
* Good for prd

### Diagram
[<img src="https://i.imgur.com/4PCIJIF.png">](https://i.imgur.com/4PCIJIF.png)

---

## Beanstalk Deployment Immutable
* Zero downtime
* New Code is deployed to new instances on a temporary ASG
* High cost, double capacity
* Longest deployment
* Quick rollback in case of failures (just terminate new ASG)
* Great for prd

### Diagram
[<img src="https://i.imgur.com/inzvH7q.png">](https://i.imgur.com/inzvH7q.png)

---

## Beanstalk Deployment Blue/Green
* Not a "direct feature" of Elastic Beanstalk
* Zero downtime & release facility
* Create a new "stage" environment & deploy v2 there
* The new envrionment (green) can be balidated indepently & roll back if issues
* Route 53 can be setup using weighted policies to redirect a little bit of traffic to the stage envrionment
* Using Beanstalk, "swap URLs" when done with the envrionment test
* It's manual as steps to do

### Diagram
[<img src="https://i.imgur.com/dbowPyM.png">](https://i.imgur.com/dbowPyM.png)

---

## Summary from AWS Doc
### Deployment methods
| Method                        | Impact of Failed Deployment                                                                             | Deploy<br>Time | Zero<br>Downtime | No DNS<br>change | Rollback<br>Process        | Code<br>Deployed to        |
| ----------------------------- | ------------------------------------------------------------------------------------------------------- | -------------- | ---------------- | ---------------- | -------------------------- | -------------------------- |
| All at once                   | Downtime                                                                                                | ⏰              | ✗                | ✔                | Manual Redeploy            | Existing instances         |
| Rolling                       | Single batch out of service; any successful batches prior to failure<br>running new application version | ⏰⏰ †           | ✔                | ✔                | Manual Redeploy            | Existing instances         |
| Rolling with additional batch | Minimal if firt batch fails, otherwise, simalir to **Rolling**                                              | ⏰⏰⏰ †          | ✔                | ✔                | Manual Redeploy            | New & existing<br>instance |
| Immutable                     | Minimal                                                                                                 | ⏰⏰⏰⏰           | ✔                | ✔                | Terminate New<br>Instances | New instances              |
| Blue/green                    | Minimal                                                                                                 | ⏰⏰⏰⏰           | ✔                | ✗                | Swap URL                   | New instances              |

