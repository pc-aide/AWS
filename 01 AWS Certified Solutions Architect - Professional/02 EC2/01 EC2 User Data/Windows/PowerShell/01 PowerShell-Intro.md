# 01 PowerShell-Intro

## Doc
* [user-data-powershell](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ec2-windows-user-data.html#user-data-powershell)

## Tags
## persist [bool]
* Create a text file with the instance user data. To execute user data scripts every time you reboot
  or start the instance, add **\<persist\>true\</persist\>**, as shown in the following example
### E.g:
````PowerShell
<powershell>
$file = $env:SystemRoot + "\Temp\" + (Get-Date).ToString("MM-dd-yy-hh-mm")
New-Item $file -ItemType file
</powershell>
<persist>true</persist>
````

## User data
### Demo-01
````PowerShell
<powershell>
$file = $env:SystemRoot + "\Temp\" + (Get-Date).ToString("MM-dd-yy-hh-mm")
New-Item $file -ItemType file
</powershell>
````
* User Data :

[<img src="https://i.imgur.com/O3axQSO.png">](https://i.imgur.com/O3axQSO.png)

* CheckUp on EC2:
  * $file

[<img src="https://i.imgur.com/8vuoEBY.png">](https://i.imgur.com/8vuoEBY.png)

* UserScrip.ps1:

[<img src="https://i.imgur.com/uS3fOLZ.png">](https://i.imgur.com/uS3fOLZ.png)

### Demo-02
