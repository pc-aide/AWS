# get-login-password

## Switch
* get-login-password help

## Syntax
````bash
aws ecr get-login-password \
  --region <region> \
  | docker login \
    --username AWS \
    --password-stdin <aws_account_id>.dkr.ecr.<region>.amazonaws.com
````

## Examples
### 01
