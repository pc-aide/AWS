# Quiz 09 - CLI & SDK

## Questions
1) I have an on-premise personal server that I'd like to use to perform AWS API calls
    * I should run `aws configure` & put my credentials there. Invalidate tehm when I'm done
    * I should ttach an EC2 IAM Role to my personal server
* [Answer](https://i.imgur.com/iB8lcQg.png)
2) My EC2 Instance does not have the permissions to perform an API call PutObject on S3. What should I do?
    * I should run `aws configure` & insert my personal credentials, because i have access to PutObject on S3
    * I should ask an administrator to attach a Policy to the IAM role on my EC2 Instance that authorises it to do the API call
    * I should export the environment variables with my credentials on the EC2 Instance
    * I should use the EC2 Metadata API call
* [Answer](https://i.imgur.com/N6Q9OGz.png)
3) I need my colleagues help to debug my code. When he runs the application on his machine, it's working fine,
   whereas I get API authorisation exceptions. What should I do?
   * Send him my AWS access key & secret key so he can replicate the issue on his machine
   * Ask him to send me his credentials o i can start working
   * Compare his IAM policy & my IAM policy in the policy simulator to understand the differences
   * Ask him to create an EC2 server & put his credentials there so I can run the application from the EC2 Instance
* [Answer](https://i.imgur.com/GKly0Lo.png)
4) To get the instance id of my EC2 machine from the EC2 machine, the best thing is to...
   * Create an IAM role & attach it to my EC2 instance so I can perform a "describe" API call
   * Query the user data at http://169.254.169.254/latest/user-data
   * Query the meta data at http://169.254.169.254/latest/meta-data
   * Query the use data at http://254.169.254.169/latest/meta-data
* [Answer](https://i.imgur.com/fZ2WJ7k.png)
5) The AWS CLI depends on which language?
   * Java
   * Golang
   * Python
   * C#
* [Answer](https://i.imgur.com/7Yrt0kC.png)
6) I'd like to deploy an application to an on-premise server. The server needs to perform API calls
   to Amazon S3. Amongst the following options, the best security I can achieve is...
   * run `aws configure` & insert my personal credentials
   * create an IAM user for hte application & insert the credentials in the application's code
   * create an IAM user for the application & put the credentials into envrionment variables. here, it's about creating a dedicated user for that
     application, as using your own personal credentials would blur the lines between actual users & applications
   * attach an IAM Role to my on-premise server
* [Answer](https://i.imgur.com/tHxqgwG.png)
7) When I run the CLI on my EC2 Instances, the CLI uses the ______ service to get _____ credentials thanks to the IAM Role that's attached. 
   * user data | temporary
   * user data | permanent
   * meta data | temporary
   * meta data | permanent
* [Answer](https://i.imgur.com/IOuHXzS.png)
8) I want to test whether my EC2 machine is able to perform the termination of EC2 instances. There is an IAM role attached to my EC2 Instance. I should
   * Use the IAM Policy Simulator OR the dry run CLI option
   * Use the IAM Policy Simulator OR metadata service
   * Use the dry run CLI option OR the metadata service
* [Answer](https://i.imgur.com/M3v9Zsu.png)
9) Can EC2 Instances retrieve the IAM Role policy JSON document that's attached to them using the CLI without any role attached?
   * No
   * Yes
* [Answer](https://i.imgur.com/VRxpec5.png)
10) I have received an authorisation exception from my EC2 instance while performing an EC2 API call.
````text
vbguZQlpz4e1h4rtSaXnEfDAFZPii8XvCNW7dLIE4Xy-zE8VcNIeh8tf4DAn1APFw__Nr55bUE0hrS02bg50EimidVBPHH1rtWmh
QOtmv5tdUY5VelEAhc5O9OC8h4fYRlegBxfUNrGSCqlH83h_HMyaqC1fQy2G7rNjmFEPcN-pue2NZc9MMZMRdfWbYszMlbkAYl
rAmSMmr4F0FE6BWOUxFOCdRnuwwb8OEM9c8RXBK8F91YqgdbW_XvxYBi2_BEI2P-8gFz4LmBkba1UdEylh-WUS95XInC3OU8i3w
ZZ-xKExGWu1HwoqS9QAqIqm6jmn7wbTK_v9EVv0jMnCzmNxuMHpqmw2Ys3Bu3WdqvAwHxmT5W_XCbGBdtstckPXkeSyNS5hLSNLBj
jRgd_I8JfPKTmB79sB_mUBSTlc28z5wjv1UBtxKBLT5GHdHQM8s2dP30cJCObRITmNvJo6Q8zaya1XYpwvCGIQrWF6-xaYQeXFCmM
gyfsosIS8bVfpNyzzz2usC1mFJMlwIciissbz10YslH-PQF7Wwvn_6ypipoQVh0z80XglLVYnfbXGFv330ZyviBQnttklCecIK56OM
cAxPJfTIWru57RoKedhJaHiKVEdLtILvVJgJ71wn-6wd4QA9aMh38jTpI_-cOPWLsvNq5NbtfqxQZ5BJOUs0rQpTmYRF_FtlY1k
````
   I want the decode the cryptic error message. How do I do it?
   * Ask AWS Support because only them can decode these messages
   * Use the EC2 decode-authorization-message API
   * Use the IAM decode-authorization-message API
   * Use the STS decode-authorization-message API
* [Answer](https://i.imgur.com/eN2mSzi.png)
11) My KMS API call just failed against AWS. It's seems I've reached the rate limit of the KMS API. I should retry
   * Every 10 ms
   * Using an linear backoff strategy
   * Using an exponential backoff strategy
* [Answer](https://i.imgur.com/5c6mfkS.png)
12) Which API call should be used to get credentials before issuing API calls against an MFA-protected API?
   * STS GetFederationToken
   * STS GetSessionToken
   * IAM GetMFAToken
* [Answer](https://i.imgur.com/aiqpfYb.png)
13) What is the priority in the CLI credentials chain?
   * Environment Variables > Command Line Options > EC2 Instance Profile
   * Command Line Options > Envrionment Variables > EC2 instance Profile
   * EC2 Instance Profile > Command-Line Options > Envrionment Variables
   * EC2 Instances > Envrionment Variables > Command-Line Options
* [Answer](https://i.imgur.com/xxSkXm8.png)
