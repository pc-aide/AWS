# Demo - Beanstalk Deploy Modes

## Acronym
* cfg - configuration
* AZ - Availability Zone

## Doc
* [Deployment policies and settings](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.rolling-version-deploy.html?icmpid=docs_elasticbeanstalk_console)

## Intro
* Edit Beanstalk-prod\cfg\Rolling updates & deploy:

[<img src="https://i.imgur.com/n1r9LkQ.png">](https://i.imgur.com/n1r9LkQ.png)

* Deployment policy
    * new one: Traffic splitting
    
[<img src="https://i.imgur.com/ebdz5gO.png">](https://i.imgur.com/ebdz5gO.png)

* Deployment policy: Immutable
* Apply

[<img src="https://i.imgur.com/Dy6KjDo.png">](https://i.imgur.com/Dy6KjDo.png)

* Warning:
    * aws:autoscaling:asg:MinSize
    
[<img src="https://i.imgur.com/eCRcqYW.png">](https://i.imgur.com/eCRcqYW.png)

* ASG currently & AZs:

[<img src="https://i.imgur.com/q3BYIYi.png">](https://i.imgur.com/q3BYIYi.png)
[<img src="https://i.imgur.com/1Exx4Rs.png">](https://i.imgur.com/1Exx4Rs.png)

* Update our Deployment policy without nothing to change in ASG:

[<img src="https://i.imgur.com/9feq7Hm.png">](https://i.imgur.com/9feq7Hm.png)
[<img src="https://i.imgur.com/IFJYQ0n.png">](https://i.imgur.com/IFJYQ0n.png)

* we can search in google: beanstalk sample application zip\aws doc...:

[<img src="https://i.imgur.com/UjvjwCq.png">](https://i.imgur.com/UjvjwCq.png)

* [sample.node.js from aws](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/samples/nodejs.zip)

* Visual Code
    * .ebextension/logging.config
    * app.js
    * cron.yaml
    * EBSampleApp-Nodejs.iml
    * index.html
    * package.json
    
[<img src="https://i.imgur.com/sQFxDiC.png">](https://i.imgur.com/sQFxDiC.png)
[<img src="https://i.imgur.com/C8AjeVo.png">](https://i.imgur.com/C8AjeVo.png)
[<img src="https://i.imgur.com/uBQwbgD.png">](https://i.imgur.com/uBQwbgD.png)
[<img src="https://i.imgur.com/GtRyxhD.png">](https://i.imgur.com/GtRyxhD.png)
[<img src="https://i.imgur.com/iIUxsPC.png">](https://i.imgur.com/iIUxsPC.png)
[<img src="https://i.imgur.com/GNPes4D.png">](https://i.imgur.com/GNPes4D.png)
[<img src="https://i.imgur.com/N1I7JMY.png">](https://i.imgur.com/N1I7JMY.png)

* Change background color for any other that green:

[<img src="https://i.imgur.com/qHMIxeV.png">](https://i.imgur.com/qHMIxeV.png)

* zip the file & upload this file in Beanstalk:

[<img src="https://i.imgur.com/h5VZX7t.png">](https://i.imgur.com/h5VZX7t.png)
[<img src="https://i.imgur.com/kJ3d6hr.png">](https://i.imgur.com/kJ3d6hr.png)
[<img src="https://i.imgur.com/LPuBzNt.png">](https://i.imgur.com/LPuBzNt.png)

* Browswer:

[<img src="https://i.imgur.com/VYOlx2T.png">](https://i.imgur.com/VYOlx2T.png)

* events:

[<img src="https://i.imgur.com/cedwQIn.png">](https://i.imgur.com/cedwQIn.png)

* health\warining:

[<img src="https://i.imgur.com/b5Qly5c.png">](https://i.imgur.com/b5Qly5c.png)

* maybe the error hierarchy folder:
  * simple_node_aws.zip
  *  /simple_nodeaws/*
    
* should :simple_node_aws.zip
  * simple_node_aws.zip
  * /*
  
[<img src="https://i.imgur.com/Xo9XS22.png">](https://i.imgur.com/Xo9XS22.png)
  
* Try again:
  
[<img src="https://i.imgur.com/SSzU7GN.png">](https://i.imgur.com/SSzU7GN.png)

* Broswer + autoF5:

[<img src="https://i.imgur.com/E6H03yV.png">](https://i.imgur.com/E6H03yV.png)

* Events ok:

[<img src="https://i.imgur.com/iVSGhma.png">](https://i.imgur.com/iVSGhma.png)

* Browser:

[<img src="https://i.imgur.com/grtLBC1.png">](https://i.imgur.com/grtLBC1.png

* Events working stil...

[<img src="https://i.imgur.com/wW6dqDl.png">](https://i.imgur.com/wW6dqDl.png)

* EC2:

[<img src="https://i.imgur.com/0Qbv7fc.png">](https://i.imgur.com/0Qbv7fc.png)

* ASG:

[<img src="https://i.imgur.com/zLbxz3s.png">](https://i.imgur.com/zLbxz3s.png)

* healthy:

[<img src="https://i.imgur.com/aDhxXR3.png">](https://i.imgur.com/aDhxXR3.png)

* Done deploy new ver:

[<img src="https://i.imgur.com/OdUIwlv.png">](https://i.imgur.com/OdUIwlv.png)

* Swap environment URLs
  * dev -> prd
  
[<img src="https://i.imgur.com/xR1MzGD.png">](https://i.imgur.com/xR1MzGD.png)
[<img src="https://i.imgur.com/clku6UO.png">](https://i.imgur.com/clku6UO.png)
[<img src="https://i.imgur.com/4J80bFz.png">](https://i.imgur.com/4J80bFz.png)

* Swap environment URLs:

[<img src="https://i.imgur.com/to9KT4O.png">](https://i.imgur.com/to9KT4O.png)
[<img src="https://i.imgur.com/xDMPZYU.png">](https://i.imgur.com/xDMPZYU.png)

* swap ...

[<img src="https://i.imgur.com/0BERd9Q.png">](https://i.imgur.com/0BERd9Q.png)

* Events complete:

[<img src="https://i.imgur.com/WXz1wC3.png">](https://i.imgur.com/WXz1wC3.png)

* Browswer still the same !?
* if some cache - it'll take couple minutes

[<img src="https://i.imgur.com/Ftw7VRx.png">](https://i.imgur.com/Ftw7VRx.png)

* wait ~5 mint (it's long because intervention at level Route 53 & TTL):

[<img src="https://i.imgur.com/whDVFvn.png">](https://i.imgur.com/whDVFvn.png)

* test with stopwatch - same action swap:

* origin ~16:12PM:

[<img src="https://i.imgur.com/3ZietvD.png">](https://i.imgur.com/3ZietvD.png)

* after ~
    * autoF5 - 2s the interval
    * (swap it's done & ok for browswer)
    * caching can still old code event it's done
    * if i use Route 53 or other registry domain - so it will be transparent for end user !?
    
[<img src="https://i.imgur.com/Emf0gWd.png">](https://i.imgur.com/Emf0gWd.png)
[<img src="https://i.imgur.com/zKw2Df8.png">](https://i.imgur.com/zKw2Df8.png)
[<img src="https://i.imgur.com/bYQLwKD.png">](https://i.imgur.com/bYQLwKD.png)
