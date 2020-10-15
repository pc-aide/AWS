# add-permission

## Switch
* aws lambda add-permission help

## Examples
### 01 Resource-based policy
````bash
# change <lambdaAlias> for real alias
aws lambda add-permission \
--function-name "arn:aws:lambda:us-east-1:427263915585:function:Lambda-APIGW-Proxy:<lambdaAlias>" \
--source-arn "arn:aws:execute-api:us-east-1:427263915585:ps7zttc39h/*/GET/stagevariables"  \
--principal apigateway.amazonaws.com  \
--statement-id fa5f2af6-590d-4f62-b11b-051a0d2a9fb6 
--action lambda:InvokeFunction \
--region us-east-1
````
