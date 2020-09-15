# EC2

## Acronym
* GPU - Graphic Processing Unit

## Doc
* [instance-types](https://aws.amazon.com/ec2/instance-types/)
* [ec2instances](https://www.ec2instances.info/)
* [new-t2-unlimited-going-beyond-the-burst-with-high-performance](https://aws.amazon.com/blogs/aws/new-t2-unlimited-going-beyond-the-burst-with-high-performance/)

## Security Group
### Traffic
* Default with only RDP

* Inbound:

[<img src="https://i.imgur.com/Bnur4FJ.png">](https://i.imgur.com/Bnur4FJ.png)

* Open/filtered:

[<img src="https://i.imgur.com/XsqctjO.png">](https://i.imgur.com/XsqctjO.png)

## Instance Overview
* Instances have 5 distinct characteristics advertised on the website
    * RAM (type, amount, generation)
    * CPU (type, make, frequency, generation, number of cores)
    * I/O (disk performance, EBS optimisations)
    * Network (bandwidth, latency)
    * GPU
* **M** instance types are balanced
* T2/T3 instance types are "burstable"

### Bustable Instance
* AWS has the concept of bustable instance (T2 machines)
* Burst means that overrall, the instance has OK CPU performance
* When the machine needs to process something unexpected (a spike in load for example), it can burst, & CPU can be VERY good
* If the machine busts, it utilizes "burst credits"
* If all the credits are gone, the CPU becomes BAD
* If the machine stops bursting, credits are accumulated over time
* Burstable instances can be amazing to handle unexpected traffic & getting the insurance that it will be handled correctly
* If your instance consistently runs low on credit, you need to move to a different kind of non-bustable instance (all the ones described before)

[<img src="https://i.imgur.com/X0suClu.png">](https://i.imgur.com/X0suClu.png)

### CPU Credits
| Instance type | Launch credit | vCPUs | CPU credits<br>earned per hour | Max earned CPU<br>credit balance | vCPUs | Baseline performance<br>(% CPU utilisation) |
| ------------- | ------------- | ----- | ------------------------------ | -------------------------------- | ----- | ------------------------------------------- |
| t2.nano       | 30            | 1     | 3                              | 72                               | 1     | 5%                                          |
| t2.micro      | 30            | 1     | 6                              | 144                              | 1     | 10%                                         |
| t2.small      | 30            | 1     | 12                             | 288                              | 1     | 20%                                         |
| t2.medium     | 60            | 2     | 24                             | 576                              | 2     | 40% (of 200% max)\*                         |
| t2.large      | 60            | 2     | 36                             | 864                              | 2     | 60% (of 200% max)\*                         |
| t2.xlarge     | 120           | 4     | 54                             | 1296                             | 4     | 90% (of 400% max)\*                         |
| t2.2xlarge    | 240           | 8     | 81                             | 1944                             | 8     | 135% (of 800% max)\*                        |

## t2 Unlimited
* Now 2017: It's possible to have an "unlimited burst credit balance"
* You pay extra money if you go over your credit balance, but you don't lose in performance
* Overall, it's a new offering, so be carefull, costs could go high if you're not monitoring the health of your instances
