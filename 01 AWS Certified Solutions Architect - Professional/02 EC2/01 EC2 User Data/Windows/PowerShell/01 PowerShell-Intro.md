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
* User Data :

[<img src="https://i.imgur.com/O3axQSO.png">](https://i.imgur.com/O3axQSO.png)

* CheckUp on EC2:
  * $file

[<img src="https://i.imgur.com/8vuoEBY.png">](https://i.imgur.com/8vuoEBY.png)

* UserScrip.ps1:

[<img src="https://i.imgur.com/uS3fOLZ.png">](https://i.imgur.com/uS3fOLZ.png)

### Demo-02
````Powershell
<PowerShell>
 <#
 --------------------------------
  Tested on MS Windows SRV 19 Base
 --------------------------------
 #>
 #Hostname: EC2W19-01
 Rename-computer EC2W19-01
    
 #TimeZone UTC-5
 tzutil /s "eastern standard time"
    
 #Allow-IN-Echo-Request
  Set-NetFirewallRule -Name "FPS-ICMP4-ERQ-In" -Enabled True
    
  #Reboot
  Restart-Computer
</PowerShell>
````
* User Data:

[<img src="https://i.imgur.com/IqJv08N.png">](https://i.imgur.com/IqJv08N.png)

* Pending & get password key (4min):
[<img src="https://i.imgur.com/G1dVpac.png">](https://i.imgur.com/G1dVpac.png)
[<img src="https://i.imgur.com/XdtcQHv.png">](https://i.imgur.com/XdtcQHv.png)

* Test... :

[<img src="https://i.imgur.com/V4vXu1t.png">](https://i.imgur.com/V4vXu1t.png)
