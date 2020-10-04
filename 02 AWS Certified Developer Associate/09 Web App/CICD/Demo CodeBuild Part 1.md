# Demo CodeBuild Part 1

## Acronym

## Doc
* [Docker images provided by CodeBuild](https://docs.aws.amazon.com/codebuild/latest/userguide/build-env-ref-available.html)

## Intro
* Test our build on application (root)
* Browser:

[<img src="https://i.imgur.com/MzEPTLq.png">](https://i.imgur.com/MzEPTLq.png)

* CodeCommit\Build\Getting started\Create project:

[<img src="https://i.imgur.com/TpuNlZT.png">](https://i.imgur.com/TpuNlZT.png)

* Create buld project
    * Project name: Build-Project-Demo
    * Source\Source provider:CodeCommit
    * Repository: nodejs-app
    
[<img src="https://i.imgur.com/xYe63jP.png">](https://i.imgur.com/xYe63jP.png)

* Environment:
    * Environment image: Managed image
    * OS: Ubuntu
    * Runtime: Standard
    Image: aws/codeBuild/stanard:3.0
    
[<img src="https://i.imgur.com/kG2amNI.png">](https://i.imgur.com/kG2amNI.png)
[<img src="https://i.imgur.com/VOFQ4sQ.png">](https://i.imgur.com/VOFQ4sQ.png)

* Buildspec:

[<img src="https://i.imgur.com/3L1K6o5.png">](https://i.imgur.com/3L1K6o5.png)

* Create build project

[<img src="https://i.imgur.com/zM9JNXi.png">](https://i.imgur.com/zM9JNXi.png)
[<img src="https://i.imgur.com/KFlmpZY.png">](https://i.imgur.com/KFlmpZY.png)


* Start build:

[<img src="https://i.imgur.com/ln2yBEG.png">](https://i.imgur.com/ln2yBEG.png)

* Start build:
* Branch: master

[<img src="https://i.imgur.com/PEZEmw9.png">](https://i.imgur.com/PEZEmw9.png)
[<img src="https://i.imgur.com/YW1qLB6.png">](https://i.imgur.com/YW1qLB6.png)

* Failed:

[<img src="https://i.imgur.com/KTVkV1v.png">](https://i.imgur.com/KTVkV1v.png)

* Phase details:
* YAML_file_ERROR:

[<img src="https://i.imgur.com/ojZsr0C.png">](https://i.imgur.com/ojZsr0C.png)

* Need to add in CodeCommit\Code\*buildspec.yaml**:

[<img src="https://i.imgur.com/rhiLy24.png">](https://i.imgur.com/rhiLy24.png)
