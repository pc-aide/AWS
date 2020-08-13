# Curriculum

## Acronym
* S3 - Scalable Storage in the Cloud
* EIP - Elastic IP Address
* VPC - Virtual Private Cloud
* EC2 - Elastic Compute Cloud
* SW - Software
* HW - Hardware
* AMI - Amazon Machine Image

## List by introduction -> advance
1) [AWS Cloud Practitioner Essentials (Second Edition) | 6 hours](https://www.aws.training/Details/Curriculum?id=27076)

[<img src="https://i.imgur.com/vDz7SK5.png">](https://i.imgur.com/vDz7SK5.png)

## AWS Console
### Region
* Choose your region (where the EC2 instance will be hosted)

[<img src="https://i.imgur.com/zG4qXmQ.png">](https://i.imgur.com/zG4qXmQ.png)

### Services
* Services\EC2

[<img src="https://i.imgur.com/JWyMHoT.png">](https://i.imgur.com/JWyMHoT.png)
* Launch instance

[<img src="https://i.imgur.com/oQ6juLX.png">](https://i.imgur.com/oQ6juLX.png)
* Amazon Linux AMI 2018.03 (HVM), SSD Volume Type

[<img src="https://i.imgur.com/DRZShnR.png">](https://i.imgur.com/DRZShnR.png)
#### Instance Type
1) Chosse your Type, vCPUs, Memory (GiB), and sot on

[<img src="https://i.imgur.com/DpuUW3z.png">](https://i.imgur.com/DpuUW3z.png)

2) Choose : 
    * Nbr instance, 
    * Network
    * Subnet
    * and so on

[<img src="https://i.imgur.com/BoIblRp.png">](https://i.imgur.com/BoIblRp.png)

3) Add Storage

[<img src="https://i.imgur.com/g8AGUCd.png">](https://i.imgur.com/g8AGUCd.png)

4) Add Tags
* A tag consists of a case-sensitive key-value pari
      * E.g. tag with key = Name & Value = Webserver
* A copy of a tag can be applied to volumes, instances or both

[<img src="https://i.imgur.com/FNUjTTC.png">](https://i.imgur.com/FNUjTTC.png)

5) Configure Security Group (firewall)
* Create or select ... security group
      * Security group name
      * Description
* Type
   * Custom TCP Rule
   * Custom UDP Rule
   * Custom ICMP Rule - IPv4
   * Custom ICMP Rule - IPv6
   * Custom Protocol
   * All TCP
   * All UDP
   * All ICMP - IPv4
   * All ICMP - IPv6
   * All traffic
   * SSH
   * SMTP
   * DNS (UDP)
   * DNS (TCP)
   * HTTP
   * POP3
   * IMAP
   * LDAP
   * HTTPS
   * SMB
   * SMTPS
   * IMAPS
   * POP3S
   * MS SQL
   * NFS
   * MYSQL/Aurora
   * RDP
   * Redshift
   * PostgreSQL
   * Oracle-RDS
   * WinRM-HTTP
   * WinRM-HTTPS
   * Elastic Graphics
   
[<img src="https://i.imgur.com/st67M4J.png">](https://i.imgur.com/st67M4J.png)

6) Review Instance Lauch

[<img src="https://i.imgur.com/bt9Q4LK.png">](https://i.imgur.com/bt9Q4LK.png)

7) An existing key pair or create a new key pari
* Create a new key pair
      * key pair name
      * Download key pair (*.pem)
      
[<img src="https://i.imgur.com/jhmHbdV.png">](https://i.imgur.com/jhmHbdV.png)

8) Lanch Status

[<img src="https://i.imgur.com/yxiAwOa.png">](https://i.imgur.com/yxiAwOa.png)
[<img src="https://i.imgur.com/jkQMAtt.png">](https://i.imgur.com/jkQMAtt.png)

## SSH
* Default user : ec2-user
### puttygen
* Convert \*.pem -> \*.ppk

        * Open puttygen.exe\load *.pem

[<img src="https://i.imgur.com/aHW1lpQ.png">](https://i.imgur.com/aHW1lpQ.png)

[<img src="https://i.imgur.com/7k7Dy4d.png">](https://i.imgur.com/7k7Dy4d.png)

[<img src="https://i.imgur.com/BFkmXre.png">](https://i.imgur.com/BFkmXre.png)

### putty
* Connection\SSH\Auth\Browse...\*.ppk
* host name\UserName@PublicIP

[<img src="https://i.imgur.com/hkoHIYA.png">](https://i.imgur.com/hkoHIYA.png)

[<img src="https://i.imgur.com/ycxF4i9.png">](https://i.imgur.com/ycxF4i9.png)

## Elastic Block Store (EBS)
* One Storage (OS)

[<img src="https://i.imgur.com/V7f822G.png">](https://i.imgur.com/V7f822G.png)

### ASW Console
* Services\Elastic Block Store\Volumes

[<img src="https://i.imgur.com/eeTnxwQ.png">](https://i.imgur.com/eeTnxwQ.png)

* the EBS volume must be created on the same Availability Zone
* Create Volume

[<img src="https://i.imgur.com/QVcGCUG.png">](https://i.imgur.com/QVcGCUG.png)

[<img src="https://i.imgur.com/gUswbzH.png">](https://i.imgur.com/gUswbzH.png)

* Attach Volume

[<img src="https://i.imgur.com/xjtREQy.png">](https://i.imgur.com/xjtREQy.png)

[<img src="https://i.imgur.com/mUvjOnO.png">](https://i.imgur.com/mUvjOnO.png)

* New disk

[<img src="https://i.imgur.com/MvwJwFt.png">](https://i.imgur.com/MvwJwFt.png)

* Format

[<img src="https://i.imgur.com/yX69lgN.png">](https://i.imgur.com/yX69lgN.png)

* Mount

[<img src="https://i.imgur.com/RueiJsM.png">](https://i.imgur.com/RueiJsM.png)
[<img src="https://i.imgur.com/I5V84ey.png">](https://i.imgur.com/I5V84ey.png)

[<img src="https://i.imgur.com/FYPkTB7.png">](https://i.imgur.com/FYPkTB7.png)
````Bach
cd /mnt
ls
vim test.txt
ls
mkdir folder
mv test.txt folder/
````
[<img src="https://i.imgur.com/VrP1HLM.png">](https://i.imgur.com/VrP1HLM.png)

* umount
````Bash
cd
umount /mnt
````
* Detach Volume

[<img src="https://i.imgur.com/i6K2ndT.png">](https://i.imgur.com/i6K2ndT.png)
[<img src="https://i.imgur.com/V9rqgGo.png">](https://i.imgur.com/V9rqgGo.png)

## Simple Storage Service (S3)
* AWS Console\Services\S3
   * What is S3 ?
      * Managed cloud storage service
      * Store virtually unlimited number of objects
   * E.g.
      * media/welcome.mp4

[<img src="https://i.imgur.com/iIMF2sW.png">](https://i.imgur.com/iIMF2sW.png)

* Create bucket

[<img src="https://i.imgur.com/3Egndsc.png">](https://i.imgur.com/3Egndsc.png)

[<img src="https://i.imgur.com/6aZybkS.png">](https://i.imgur.com/6aZybkS.png)
