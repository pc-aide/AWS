# Usage Plans & API Keys

## Acronym

## Doc

## Intro
* If you want to make an API available as an offering (**$$$**) to your customers
* **Usage Plan**:
    * Who can access one or more deployed API stages & methods
    * how much & how fast they can access them
    * uses API keys to identify API clients & meter access
    * configure throttling limits & quota limits that are enforced on individual client
* **API Keys**:
    * alphanumeric string values to distribute to your customers
    * Ex: WBjHxNtoAb4WPKBc7cGm64Cbib1b24b4jt8jJHo9
    * Can use with usage plans to control access
    * Throttling limits are applied to the API keys
    * Quotas limits is the overall number of maximum requests
    
---

## Correct Order for API keys
* **To configure a usage plan**
1. Create one or more APIs, configure the methods to require an API key, & deploy the APIs to stages
2. Generate or import API keys to distribute to application developers (your customers) who will be using your API
3. Create the usage plan with the desired throttle & quota limits
4. <ins>Associate API stages & API keys with the usage plan</ins>
* Callers of the API must supply an assigned API key in the x-api-key header in requests to the API

---

## Demo
* Resource\Actions\**New resource**
      * Resource name: apikey
* create method
      * GET
      * Integration type: MOCK -no need back-end
      
[<img src="https://i.imgur.com/nOpH32T.png">](https://i.imgur.com/nOpH32T.png)
[<img src="https://i.imgur.com/szfUa8Q.png">](https://i.imgur.com/szfUa8Q.png)
[<img src="https://i.imgur.com/oSHo48t.png">](https://i.imgur.com/oSHo48t.png)

* test\MOCK
      * Status: 200
      * Response body: no data

[<img src="https://i.imgur.com/qn2k6po.png">](https://i.imgur.com/qn2k6po.png)

* Method Request
      * API key requireds: true
      
[<img src="https://i.imgur.com/EyM8hGf.png">](https://i.imgur.com/EyM8hGf.png)


### Usage Plans
* create
      * name: DemoPlan
      * Throttling:
         * Rate: 10
         * Bust: 5
            * how much my customer can few more busting request
      * Quota: 10k request month

[<img src="https://i.imgur.com/Fj9yom5.png">](https://i.imgur.com/Fj9yom5.png)
[<img src="https://i.imgur.com/aWf7A1w.png">](https://i.imgur.com/aWf7A1w.png)
[<img src="https://i.imgur.com/Nn3jwIt.png">](https://i.imgur.com/Nn3jwIt.png)

* Add API Stage:
      * API: Demo-API
      * Stage: Prod
         * Warning : not active because no deploy our new resource- so this is not going to be active
      
[<img src="https://i.imgur.com/Mr7ZmuI.png">](https://i.imgur.com/Mr7ZmuI.png)
[<img src="https://i.imgur.com/VwPhu2T.png">](https://i.imgur.com/VwPhu2T.png)

* Usage Plan API Keys\Create API key & add to usageplan
      * Name: PayCustomer
      * API key: Auto Generate
      
[<img src="https://i.imgur.com/4wfBX8j.png">](https://i.imgur.com/4wfBX8j.png)
[<img src="https://i.imgur.com/I82a7TF.png">](https://i.imgur.com/I82a7TF.png)
[<img src="https://i.imgur.com/kS1ZyXr.png">](https://i.imgur.com/kS1ZyXr.png)
[<img src="https://i.imgur.com/wJjMmIg.png">](https://i.imgur.com/wJjMmIg.png)
[<img src="https://i.imgur.com/JTjwRpc.png">](https://i.imgur.com/JTjwRpc.png)
[<img src="https://i.imgur.com/6WjMbCk.png">](https://i.imgur.com/6WjMbCk.png)

* API keys
      * usage
      * extension
      
[<img src="https://i.imgur.com/KveM23j.png">](https://i.imgur.com/KveM23j.png)
[<img src="https://i.imgur.com/rR67zQf.png">](https://i.imgur.com/rR67zQf.png)
[<img src="https://i.imgur.com/ahSifRZ.png">](https://i.imgur.com/ahSifRZ.png)

* Click on PayCustomer
      * API key show - this is the info to send to my customer for my plan stage ($) to use my API
       
[<img src="https://i.imgur.com/hXuviRo.png">](https://i.imgur.com/hXuviRo.png)

* Demo-API\deploy API
      * Deployment stage: PROD - disabled canary if on
      
[<img src="https://i.imgur.com/Ymxv3Vj.png">](https://i.imgur.com/Ymxv3Vj.png)

* PROD\**apikey**
      * API key: required
      
[<img src="https://i.imgur.com/1SHUv0T.png">](https://i.imgur.com/1SHUv0T.png)

* Usage Plans\DemoPlan\Configure Method Throttling\**Add Ressource/Method**
      * Resource: /apikey
      * Method: GET
      * Rate: 5
      * Bust: 2
      
[<img src="https://i.imgur.com/md2OvUs.png">](https://i.imgur.com/md2OvUs.png)
[<img src="https://i.imgur.com/7LHeOVs.png">](https://i.imgur.com/7LHeOVs.png)

* Stages\PROD
      * /apikey
      * GET
      * Invoke URL
         * message : Forbidden - my API key has not been passed
      
[<img src="https://i.imgur.com/Fb7QMol.png">](https://i.imgur.com/Fb7QMol.png)
[<img src="https://i.imgur.com/90y7XAl.png">](https://i.imgur.com/90y7XAl.png)

* [Insomnia.rest](https://insomnia.rest/)
      * Insomnia Core (client to download)
      
[<img src="https://i.imgur.com/rlu5SAj.png">](https://i.imgur.com/rlu5SAj.png)

### Insomnia
* New Request
      * name: API Key example
* GET: <Invoke URL>
   * Send - still Forbidden

[<img src="https://i.imgur.com/PNNsW51.png">](https://i.imgur.com/PNNsW51.png)

* Used the **API key** for my header
* API keys\
      * show
      
[<img src="https://i.imgur.com/8hjhje1.png">](https://i.imgur.com/8hjhje1.png)

* Insomnia\Header
      * X-API-Key
      * send again
         * Response: 200
      
[<img src="https://i.imgur.com/JvpVTRU.png">](https://i.imgur.com/JvpVTRU.png)
[<img src="https://i.imgur.com/aige3Mz.png">](https://i.imgur.com/aige3Mz.png)

* Usage Plan\API keys
      * Usage - it'll take some time before to see any **number requests**
      
[<img src="https://i.imgur.com/z4rKhNY.png">](https://i.imgur.com/z4rKhNY.png)

* After couple hours:
      * **16** request make between Oct1, 2020 & Oct 15, 2020 (UTC):

[<img src="https://i.imgur.com/Tm9BV3V.png">](https://i.imgur.com/Tm9BV3V.png)
