# Tenancy

## SRC
* [Understanding AWS Tenancy](https://theithollow.com/2017/10/16/understanding-aws-tenancy/#:~:text=Shared%20tenancy%20means%20that%20multiple,piece%20of%20hardware%20as%20you.)

## Intro
* Default - Shared tenancy
  * The default tenancy model is the one most commonly used with AWS. Multiple customers will share the same pieces of hardware even though they don’t interact with each other. Remember that underneath the covers in AWS, there is a physical host with a hypervisor running on it to handle the virtualization of CPU, Memory, Storage etc. Customers will choose to deploy a new EC2 instance and AWS fits that instance onto the appropriate physical host and isolate it from other customers even if they’re sharing the same physical resources. This is generally the option that you will want to use unless you have regulatory compliance or licensing restrictions causing you to pick a dedicated model. The shared tenancy model is also the cheapest option for running your EC2 instances.

* Dedicated:
  * As mentioned previously, dedicated tenancy ensures that your EC2 instances are run on hardware specific to your account but comes at a price. AWS usually focuses on driving down costs to operate their data centers and providing you your own isolated hosts to use makes that difficult. The result is that different charges need to be added to make it worthwhile to offer to their customers. Now, you might be asking why you’d want to use a dedicated tenancy model when there are pricing complications associated with them. In some cases due to licensing restrictions some software isn’t allowed to be run on a shared tenancy model. For instance if you’re trying to use Bring Your Own License (BYOL) to AWS, some licenses are based on the Socket model where the number of hosts sockets are used for licensing. In other circumstances, regulatory compliance may dictate that you can’t use the shared model. HIPAA up until earlier this year required dedicated tenancy to ensure data confidentiality. This restriction has since been removed.

There are two different options for dedicated tenancy with AWS: Dedicated Hosts and Dedicated Instances.

### img
[<img src="https://i.imgur.com/SbSF05u.png">](https://i.imgur.com/SbSF05u.png)

### Diagram
[<img src="https://i.imgur.com/rFhmQ8S.png">](https://i.imgur.com/rFhmQ8S.png)
