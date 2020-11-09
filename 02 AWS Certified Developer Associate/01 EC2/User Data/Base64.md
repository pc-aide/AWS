# base64

## Intro
* used bas64 our code for well-formated:
* Base64
````bash
IyEvYmluL2Jhc2gNCmVjaG8gInN0YXJ0aW5nIHBpenphLWx1dnJzIg0KY2QgL2hvbWUvZWMyLXVzZXIvcGl6emEtbHV2cnMNCm5wbSBzdGFydA==
````
* Decode:
````bash
#!/bin/bash
echo "starting pizza-luvrs"
cd /home/ec2-user/pizza-luvrs
npm start
````

## CloudFormation
### Before
````json
"UserData"       : { "Fn::Base64" : { "Fn::Join" : ["", [
             "#!/bin/bash -xe\n",
             "yum install -y aws-cfn-bootstrap\n",

             "# Install the files and packages from the metadata\n",
             "/opt/aws/bin/cfn-init -v ",
             "         --stack ", { "Ref" : "AWS::StackName" },
             "         --resource WebServerInstance ",
             "         --configsets Install ",
             "         --region ", { "Ref" : "AWS::Region" }, "\n"
		]]}}
````


### After
````json
"UserData": "IyEvYmluL2Jhc2gNCmVjaG8gInN0YXJ0aW5nIHBpenphLWx1dnJzIg0KY2QgL2hvbWUvZWMyLXVzZXIvcGl6emEtbHV2cnMNCm5wbSBzdGFydA=="
````
