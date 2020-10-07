# Demo X-Ray

## Acronym
* EB - Elastic Beanstalk

## Doc

## Intro
* X-Ray

[<img src="https://i.imgur.com/JQdTEqK.png">](https://i.imgur.com/JQdTEqK.png)

* N. Virginia (Region)\Get started
* Select sample or ...: Launch a sample application (Node.js):

[<img src="https://i.imgur.com/HtuUTor.png">](https://i.imgur.com/HtuUTor.png)
[<img src="https://i.imgur.com/3uSh6cg.png">](https://i.imgur.com/3uSh6cg.png)

* Create Stacks
    * Note: the template uses a t3.large instance. Which is not part of the free tier (so when it's done- delete this stack)

[<img src="https://i.imgur.com/lxhDbWe.png">](https://i.imgur.com/lxhDbWe.png)

* Stack name: Demo-X-Ray
* Subnet : any one
* VPC : default


[<img src="https://i.imgur.com/qXaxsgW.png">](https://i.imgur.com/qXaxsgW.png)
[<img src="https://i.imgur.com/kOVT4Ee.png">](https://i.imgur.com/kOVT4Ee.png)

* CheckBox: I acknowlege tha AWS CloudFormation might...

[<img src="https://i.imgur.com/aWkqhWt.png">](https://i.imgur.com/aWkqhWt.png)
[<img src="https://i.imgur.com/6zhz8NU.png">](https://i.imgur.com/6zhz8NU.png)

* Template:

[<img src="https://i.imgur.com/6YHH1Wz.png">](https://i.imgur.com/6YHH1Wz.png)
[<img src="https://i.imgur.com/u9Nctvi.png">](https://i.imgur.com/u9Nctvi.png)

* Stack Info:

[<img src="https://i.imgur.com/BiXd8o2.png">](https://i.imgur.com/BiXd8o2.png)

* EB:

[<img src="https://i.imgur.com/tBxSgu4.png">](https://i.imgur.com/tBxSgu4.png)

* Browser:

[<img src="https://i.imgur.com/zin4kYH.png">](https://i.imgur.com/zin4kYH.png)

* EC2:

[<img src="https://i.imgur.com/T52lWLn.png">](https://i.imgur.com/T52lWLn.png)

* 2x Stacks complete:

[<img src="https://i.imgur.com/mm0s38H.png">](https://i.imgur.com/mm0s38H.png)

* Resources:

[<img src="https://i.imgur.com/PYie7wB.png">](https://i.imgur.com/PYie7wB.png)
[<img src="https://i.imgur.com/pwIbMgQ.png">](https://i.imgur.com/pwIbMgQ.png)

* output or URL EB\start (button):

[<img src="https://i.imgur.com/kGxrLZW.png">](https://i.imgur.com/kGxrLZW.png)
[<img src="https://i.imgur.com/iPyH7l4.png">](https://i.imgur.com/iPyH7l4.png)
[<img src="https://i.imgur.com/UjOKuvA.png">](https://i.imgur.com/UjOKuvA.png)
[<img src="https://i.imgur.com/TzNCusn.png">](https://i.imgur.com/TzNCusn.png)

* wait to get status reques #30:

[<img src="https://i.imgur.com/P53hKnr.png">](https://i.imgur.com/P53hKnr.png)
[<img src="https://i.imgur.com/LZCbnbU.png">](https://i.imgur.com/LZCbnbU.png)

* Go back to X-Ray:

[<img src="https://i.imgur.com/heFIgRE.png">](https://i.imgur.com/heFIgRE.png)

* Done

[<img src="https://i.imgur.com/pnfuWSt.png">](https://i.imgur.com/pnfuWSt.png)

* Click on demo-x-ray...

[<img src="https://i.imgur.com/C5gUzKm.png">](https://i.imgur.com/C5gUzKm.png)

* DynamoDB:

[<img src="https://i.imgur.com/Fsxbl94.png">](https://i.imgur.com/Fsxbl94.png)

* Error\View traces:

[<img src="https://i.imgur.com/vECsYMw.png">](https://i.imgur.com/vECsYMw.png)
[<img src="https://i.imgur.com/00KDCIb.png">](https://i.imgur.com/00KDCIb.png)

* singup (error) generate with buttun start:

[<img src="https://i.imgur.com/XMiokOZ.png">](https://i.imgur.com/XMiokOZ.png)
[<img src="https://i.imgur.com/VEaq31A.png">](https://i.imgur.com/VEaq31A.png)

* Click on url ...\signup:
* Method: POST
* Response: 409 (Conflict) if resource already exists

[<img src="https://i.imgur.com/UhZDb89.png">](https://i.imgur.com/UhZDb89.png)

* Click on Trace ID:

[<img src="https://i.imgur.com/9oPi2xh.png">](https://i.imgur.com/9oPi2xh.png)
[<img src="https://i.imgur.com/KBpVedh.png">](https://i.imgur.com/KBpVedh.png)
