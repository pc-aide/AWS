# Auto Scaling

## Acronym
* CW - CloudWatch
* ASG - Auto Scaling Group

## Scaling Policies
1) Simple/Step Scaling:
  * increase or decrease instances based on two CW alarms
2) Target Tracking:
  * select a metric & a target value, ASG will smartly adjust
    * Keep average CPU at 40%
    * Keep request count per target at 1k
* To scale based on RAM, you must use a **Custom** CloudWatch Metric

---

## Good to know
* **Spot Fleet support** (mix on Spot & On-Demand instances)
