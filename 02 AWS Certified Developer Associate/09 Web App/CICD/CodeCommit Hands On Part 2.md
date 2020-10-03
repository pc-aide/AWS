# CodeCommit Hands On Part 2

## Doc
* [Use SSH keys and SSH with CodeCommit](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_ssh-keys.html?icmpid=docs_iam_console#ssh-keys-code-commit)
* [Using IAM with Amazon Keyspaces (for Apache Cassandra)](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_keyspaces.html?icmpid=docs_iam_console)

## Acronym
* IAM - Identity & Access Management

## Intro
* IAM\Users\Security Credentials:
    * SSH Keys for AWS CodeCommit:
    * HTTPS Git credentials for AWS CodeCommit

[<img src="https://i.imgur.com/1bmlrjj.png">](https://i.imgur.com/1bmlrjj.png)
[<img src="https://i.imgur.com/TXF0NHn.png">](https://i.imgur.com/TXF0NHn.png)

* Generate credentials (HTTPS Git...):

[<img src="https://i.imgur.com/iPbDlUj.png">](https://i.imgur.com/iPbDlUj.png)
[<img src="https://i.imgur.com/tI4WYIc.png">](https://i.imgur.com/tI4WYIc.png)

* CodeCommit\Code\Clone HTTPS:

[<img src="https://i.imgur.com/4Z49LMD.png">](https://i.imgur.com/4Z49LMD.png)

* install Git:

[<img src="https://i.imgur.com/qBPWWvk.png">](https://i.imgur.com/qBPWWvk.png)

* Prereq:
      1) IAM: AWSCodeCommitFullAccess 
      2) .gitconfig:
      3)  git config --global user.name "Your Name"
      4) git config --global user.email "you@example.com"
````bash
cat .gitconfig
[credential]
   helper = !aws --profile default codecommit credential-helper $@
	UseHttpPath = true
````

* optional: 
````bash
git config -l --global
````

* terminal:
````bash
git clone <Clone HTTPS>
````

[<img src="https://i.imgur.com/M9zgfqn.png">](https://i.imgur.com/M9zgfqn.png)

* New file:

[<img src="https://i.imgur.com/oApTiqC.png">](https://i.imgur.com/oApTiqC.png)

* We'll copy from nodejs-v2-blue/ to nodejs-ap/
````bash
cp ../nodejs-v2/blue* .
````

[<img src="https://i.imgur.com/jJIYLVy.png">](https://i.imgur.com/jJIYLVy.png)
[<img src="https://i.imgur.com/lF1weNV.png">](https://i.imgur.com/lF1weNV.png)

* git status
````bash
git status
````

[<img src="https://i.imgur.com/OGSl5nb.png">](https://i.imgur.com/OGSl5nb.png)

* git add
````bash
git add .
````

[<img src="https://i.imgur.com/mDtrQXT.png">](https://i.imgur.com/mDtrQXT.png)

* status again
````bash
git status
````

[<img src="https://i.imgur.com/7MavdVQ.png">](https://i.imgur.com/7MavdVQ.png)

* commit with message:
````bash
git commit -m "added new files to repository"
````

[<img src="https://i.imgur.com/vwCkKtE.png">](https://i.imgur.com/vwCkKtE.png)

* push
````bash
git push
````

[<img src="https://i.imgur.com/MtWvaOB.png">](https://i.imgur.com/MtWvaOB.png)

* CodeCommit\Code :

[<img src="https://i.imgur.com/obiYt2x.png">](https://i.imgur.com/obiYt2x.png)

* Commits:

[<img src="https://i.imgur.com/jFuyP2M.png">](https://i.imgur.com/jFuyP2M.png)
