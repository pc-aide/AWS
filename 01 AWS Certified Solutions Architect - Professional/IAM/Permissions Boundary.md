# Permissions Boundary

## Acronym
* IAM - Identity & Access Management

## Intro
* Maximum allowed access
* Allow **developers** to create roles for **Lambda**, EC2
* Limits effective permissions of roles or users no matter what the policy grants
* Does not grant any permissions

## Diagram
[<img src="https://i.imgur.com/IbyKY9C.png">](https://i.imgur.com/IbyKY9C.png)

---

## Demo
* IAM admin
  1) Create permissions boundary policy
  2) Allow IAM user to create roles with permissions boundary
* IAM User (dev)
  * Create new role
  * Must set permissions boundary
  * Demonstrate effective allowed actions due to permissions boundary
  
* policy name : DevBoundary
* Description: Allow EC2 and S3 actions
* deny policy for dev
* prevent the user from changing the permissions
  * `iam:CreatePolicyVersion`
  * `iam:DeletePolicy`
  * ...
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:*",
        "s3:*"
      ],
      "Resource": "*",
      "Condition": {
        "StringEquals": {
          "aws:RequestedRegion": "us-west-2"
        }
      }
    }
  ]
}
````
* After that, we need **ARN**
* e.g. `arn:aws:iam::018116317022:policy/DevBoundary`
* policy:
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "CreateOrChangeOnlyWithBoundary",
      "Effect": "Allow",
      "Action": [
        "iam:CreateRole",
        "iam:AttachRolePolicy"
      ],
      "Resource": "*",
      "Condition": {
        "StringEquals": {
          "iam:PermissionsBoudnary": "arn:aws:iam::018116317022:policy/DevBoundary"
        }
      }
    },
    {
      "Sid": "IAMActions",
      "Effect": "Allow",
      "Action": [
        "iam:ListGroups",
        "iam:ListGroupsForUser",
        "iam:CreateGroup",
        "iam:GetGroup",
        "iam:DeleteGroup",
        "iam:UpdateGroup",
        "iam:CreatePolicy",
        "iam:DeletePolicy",
        "iam:DeletePolicyVersion",
        "iam:GetPolicy",
        "iam:GetPolicyVersion",
        "iam:GetUserPolicy",
        "iam:GetRolePolicy",
        "iam:ListPolicies",
        "iam:ListPoilicyVersions",
        "iam:ListEntitiesForPolicy",
        "iam:ListUserPolicies",
        "iam:ListAttachedUserPolicies",
        "iam:ListRolePolicies",
        "iam:ListRoles",
        "iam:ListAttachedRolePolicies",
        "iam:SetDefaultPoilicyVersion",
        "iam:SimulatePrincipalPolicy",
        "iam:SimulateCustomPolicy"
      ],
      "NotResource": "arn:aws:iam::018116317022:user/dev1"
    },
    {
      "Sid": "NoBoundaryPolicyEdit",
      "Effect": "Deny",
      "Action": [
        "iam:CreatePolicyVersion",
        "iam:DeletePolicy",
        "iam:DeletePolicyVersion",
        "iam:SetDefaultPoilicyVersion"
      ],
      "Resource": [
        "arn:aws:iam:018116317022:policy/DevBoundary"
      ]
    },
    {
      "Sid": "NoBoundaryUserDelete",
      "Effect": "Deny",
      "Action": "iam:DeleteUserPermissionsBoundary",
      "Resource": "*"
    }
  ]
}
````
