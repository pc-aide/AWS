# Demo - CPUUtilization

## Acronym
* CW - CloudWatch

## Stress
* Download this tool for benchmark cpu
````sh
wget ftp://fr2.rpmfind.net/linux/dag/redhat/el7/en/x86_64/dag/RPMS/stress-1.0.2-1.el7.rf.x86_64.rpm
yum localinstall stress-1.0.2-1.el7.rf.x86_64.rpm
````
### Test 
* Test cpu & check out in CW\Metric\graphed metrics
  * `stress -c 30 --timeout 90`
  
[<img src="https://i.imgur.com/TXOBkws.png">](https://i.imgur.com/TXOBkws.png)
[<img src="https://i.imgur.com/dGdcG7A.png">](https://i.imgur.com/dGdcG7A.png)

* Statistic
  * Maximum
  
[<img src="https://i.imgur.com/1IUolKG.png">](https://i.imgur.com/1IUolKG.png)
