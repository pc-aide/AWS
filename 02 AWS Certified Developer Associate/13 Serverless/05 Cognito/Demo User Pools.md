# Demo User Pools

## Acronym

## Doc

## Console
* Cognito

[<img src="https://i.imgur.com/7tQTJua.png">](https://i.imgur.com/7tQTJua.png)

* Cognito\**User Pools**
    * Create a user pool
    * Pool name: Demo-Pool
    * Button: Step through settings
    * Username
    * Password strenght
      * Min length
    * MFA?
    * Remember device?
      * Cookies 
    * App clients
    * Triggers (workflow)

[<img src="https://i.imgur.com/GdO4ecO.png">](https://i.imgur.com/GdO4ecO.png)
[<img src="https://i.imgur.com/nxdUyDu.png">](https://i.imgur.com/nxdUyDu.png)
[<img src="https://i.imgur.com/eGVcw9E.png">](https://i.imgur.com/eGVcw9E.png)
[<img src="https://i.imgur.com/mfcQkdI.png">](https://i.imgur.com/mfcQkdI.png)
[<img src="https://i.imgur.com/0bMeNaP.png">](https://i.imgur.com/0bMeNaP.png)
[<img src="https://i.imgur.com/UFznmMN.png">](https://i.imgur.com/UFznmMN.png)
[<img src="https://i.imgur.com/rFGOZHz.png">](https://i.imgur.com/rFGOZHz.png)
[<img src="https://i.imgur.com/bJv2AK6.png">](https://i.imgur.com/bJv2AK6.png)
[<img src="https://i.imgur.com/UfS5wqC.png">](https://i.imgur.com/UfS5wqC.png)
[<img src="https://i.imgur.com/0UcEI5t.png">](https://i.imgur.com/0UcEI5t.png)
[<img src="https://i.imgur.com/2aCu7A0.png">](https://i.imgur.com/2aCu7A0.png)
[<img src="https://i.imgur.com/jxtoYUg.png">](https://i.imgur.com/jxtoYUg.png)

* App clients\** add an app client**
    * App client name: Demo-App-Client
* Create app client

[<img src="https://i.imgur.com/Y3aitHS.png">](https://i.imgur.com/Y3aitHS.png)
[<img src="https://i.imgur.com/za9O116.png">](https://i.imgur.com/za9O116.png)
[<img src="https://i.imgur.com/BUKpTid.png">](https://i.imgur.com/BUKpTid.png)

* App client settings (how to log to our app)
    * ChecBox: Cognito User Pool
    * Callback URL:  <createALBForDemo>
      * Note: used HTTPS & not [HTTP](https://i.imgur.com/UkLqdXH.png)
    * OAuth 2.0
      * CheckBox: all of it except one: 'Client credential'
      
[<img src="https://i.imgur.com/SUftIKA.png">](https://i.imgur.com/SUftIKA.png)
[<img src="https://i.imgur.com/kYgbhBu.png">](https://i.imgur.com/kYgbhBu.png)
[<img src="https://i.imgur.com/OfSbchI.png">](https://i.imgur.com/OfSbchI.png)
[<img src="https://i.imgur.com/hLMVnNS.png">](https://i.imgur.com/hLMVnNS.png)

* Hosted UI
    * to allow our users to connect using a UI

[<img src="https://i.imgur.com/HHZpSo6.png">](https://i.imgur.com/HHZpSo6.png)

* Domain name
    * Domain prefix: demo01 (Check availability)
    
[<img src="https://i.imgur.com/sJSQCxe.png">](https://i.imgur.com/sJSQCxe.png)

* App client settins
    * Launch Hosted UI
    
[<img src="https://i.imgur.com/PVfacjL.png">](https://i.imgur.com/PVfacjL.png)
[<img src="https://i.imgur.com/mpvUODd.png">](https://i.imgur.com/mpvUODd.png)

* We can UI custom
    * Logo -> ...
    * Text
    * Banner
    * etc
    
[<img src="https://i.imgur.com/MyhDRAR.png">](https://i.imgur.com/MyhDRAR.png)
[<img src="https://i.imgur.com/4hpptx9.png">](https://i.imgur.com/4hpptx9.png)

* Sign up
    * Username
    * Email
    * Password
      * Verification code
    
[<img src="https://i.imgur.com/ZKsDQT7.png">](https://i.imgur.com/ZKsDQT7.png)
[<img src="https://i.imgur.com/0oVRWZU.png">](https://i.imgur.com/0oVRWZU.png)
[<img src="https://i.imgur.com/TiucJIs.png">](https://i.imgur.com/TiucJIs.png)

* login was successful:

[<img src="https://i.imgur.com/GrdGIZh.png">](https://i.imgur.com/GrdGIZh.png)

* Cognito\Users & groups
    * new user
    
[<img src="https://i.imgur.com/QmZ7Owd.png">](https://i.imgur.com/QmZ7Owd.png)
[<img src="https://i.imgur.com/rpNgOV9.png">](https://i.imgur.com/rpNgOV9.png)
