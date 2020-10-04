# Demo CodeBuild Part 2

## Doc

## Acronym

## Intro
* Our failed (codeBuild)
* YAML_FILE_ERRO: file does not exit

[<img src="https://i.imgur.com/3ULiTw7.png">](https://i.imgur.com/3ULiTw7.png)
[<img src="https://i.imgur.com/hEmtXeS.png">](https://i.imgur.com/hEmtXeS.png)

* CodeCommit\Code\Create file
    * File name: buildspec.yaml
    * SRC:
````yaml
version: 0.2

phases:
    install:
        runtime-versions:
            nodejs: 10
        commands:
            - echo "installing something"
    pre_build:
        commands:
            - echo "we are in the pre build phase"
    build:
        commands:
            - echo "we are in the build block"        
            - echo "we will run some tests"
            - grep -Fq "Congratulations" index.html
    post_build:
        commands:
            - echo "we are in the post build phase" 
````

[<img src="https://i.imgur.com/sAFr57i.png">](https://i.imgur.com/sAFr57i.png)
[<img src="https://i.imgur.com/UeggptD.png">](https://i.imgur.com/UeggptD.png)

* Start build:

[<img src="https://i.imgur.com/EZWLmoe.png">](https://i.imgur.com/EZWLmoe.png)
[<img src="https://i.imgur.com/fpbbV9p.png">](https://i.imgur.com/fpbbV9p.png)

* Inprogress:

[<img src="https://i.imgur.com/Tx8PFOb.png">](https://i.imgur.com/Tx8PFOb.png)

* Succeeded:

[<img src="https://i.imgur.com/GBCdzuT.png">](https://i.imgur.com/GBCdzuT.png)
[<img src="https://i.imgur.com/QXT7kbD.png">](https://i.imgur.com/QXT7kbD.png)

* build_command_test_for_succeed:

[<img src="https://i.imgur.com/IV2ZJvm.png">](https://i.imgur.com/IV2ZJvm.png)

* Phase details

[<img src="https://i.imgur.com/PXzpcA0.png">](https://i.imgur.com/PXzpcA0.png)

* Entiere logs (CloudWatch):

[<img src="https://i.imgur.com/jHnS3d2.png">](https://i.imgur.com/jHnS3d2.png)
[<img src="https://i.imgur.com/sfarAG2.png">](https://i.imgur.com/sfarAG2.png)

* Now we used this CodeBuild in our Pipeline
* Between **source** & **deploy** 
* I want to test (codeBuild)

[<img src="https://i.imgur.com/RRIsFy8.png">](https://i.imgur.com/RRIsFy8.png)

* Edit pipeline
* After source\Add stage
    * Stage name: Build-And-Test
    
[<img src="https://i.imgur.com/q5XYRMk.png">](https://i.imgur.com/q5XYRMk.png)

* Build-And-Test\Add action group
    * Action name: Test-For-Congratulations
    * Action provider: AWS codeBuild
    * Input artifacts: SourceArtifact
    * Project name: Build-Project-Demo
    * Output artifacts: Out-Put-Test
    
[<img src="https://i.imgur.com/q5XYRMk.png">](https://i.imgur.com/q5XYRMk.png)
[<img src="https://i.imgur.com/pFPs24O.png">](https://i.imgur.com/pFPs24O.png)

* Save

* Testing this new pipeline
* new codeCommit
* index.html, change congratualations => horrible:

[<img src="https://i.imgur.com/jpfraya.png">](https://i.imgur.com/jpfraya.png)
[<img src="https://i.imgur.com/KlJByRT.png">](https://i.imgur.com/KlJByRT.png)

* workflow (pipeline):

[<img src="https://i.imgur.com/HhWuwYB.png">](https://i.imgur.com/HhWuwYB.png)

* Failed (Build-And-Test):

[<img src="https://i.imgur.com/f0R977e.png">](https://i.imgur.com/f0R977e.png)

* Details:

[<img src="https://i.imgur.com/GTBjKf3.png">](https://i.imgur.com/GTBjKf3.png)

* Build logs:

[<img src="https://i.imgur.com/Ch9xKkg.png">](https://i.imgur.com/Ch9xKkg.png)

* Browser:
* h1: Congratulations

[<img src="https://i.imgur.com/h26nXl8.png">](https://i.imgur.com/h26nXl8.png)

* Fix it (index.html)

[<img src="https://i.imgur.com/SKuSx4G.png">](https://i.imgur.com/SKuSx4G.png)
[<img src="https://i.imgur.com/iEOhNxB.png">](https://i.imgur.com/iEOhNxB.png)

* Workflow (pipeline): 

[<img src="https://i.imgur.com/z9iNaWx.png">](https://i.imgur.com/z9iNaWx.png)
[<img src="https://i.imgur.com/S0GUVcc.png">](https://i.imgur.com/S0GUVcc.png)

* Succeeded (codeBuild):

[<img src="https://i.imgur.com/Qn37An6.png">](https://i.imgur.com/Qn37An6.png)

* approuved:

[<img src="https://i.imgur.com/5VXmdqP.png">](https://i.imgur.com/5VXmdqP.png)

* Browswer:

[<img src="https://i.imgur.com/pbU2EAk.png">](https://i.imgur.com/pbU2EAk.png)

* F5:

[<img src="https://i.imgur.com/kbr7sRo.png">](https://i.imgur.com/kbr7sRo.png)
