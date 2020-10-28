# §08 - IaS

## Questions
1. Which of the AWS CloudFormation template sections is/are required?
    * A. AWSTemplateFormatVersion
    * B. Parameters
    * C. Metadata
    * D. Resources
    * E. All of the above
2. You are writing an AWS CloudFormation template and would like to create an output
value corresponding to your application’s website URL. The application is composed of
two application servers in a private subnet behind an Elastic Load Balancing load balancer.
The application servers read from the Amazon Relational Database Service (Amazon RDS)
database instance. The logical IDs of the instances are AppServerA and AppServerB. The
logical IDs of the load balancer and database are AppLB and AppDB, respectively
````json
"Outputs": {
  "AppEndpoint" : {
    "Description" : "URL to access the application",
    "Value" : "Value to return"
  }
}
````
<br/>Which code correctly completes the previous output declaration?
    * A. `{ "Fn::Join": [ "", [ https://, { "Ref": "AppLB" }, "/login.php" ] ] }`
    * B. `{ "Fn::Join": [ "", [ https://, { "Fn::GetAtt": [ "AppServerA",
          "PublicDNSName" ] }, "/login.php" ] ] }`
3.
4.
5.
6.
7.
8.
9.
10.
11.
12.
13.
14.
15.
16.
17.
18.
19.
20.
21.
22.
* [Answers]()
    * [Explications]()
* Score: /22
