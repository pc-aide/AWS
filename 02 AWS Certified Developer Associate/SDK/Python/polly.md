# polly
* to synthesize speech from text

## Prereq
1. pip install boto3 --upgrade --user

## PollyDemo.py
````json
import boto3

# Explicit Client Configuration
polly = boto3.client('polly',
    region_name='ca-central-1',
    aws_access_key_id='<value>',
    aws_secret_access_key='<value>'
)

result = polly.synthesize_speech(Text='this is a test 20-10-2020!',
    OutputFormat='mp3',
    VoiceId='Aditi')

# Save the audio from the response
audio = result['AudioStream'].read()
with open("helloworld.mp3","wb") as file:
    file.write(audio)
````

---

## Steps
1. Create PollyDemo.py
2. test with vlc

[<img src="https://i.imgur.com/B6yVz7A.png">](https://i.imgur.com/B6yVz7A.png)

---

## list 
````bash
aws polly describe-voices \
--output table
````
[img src="https://i.imgur.com/KjtYtTi.png">](https://i.imgur.com/KjtYtTi.png)

---

## Available voices (O/P: text,json,table)
````bash
aws polly describe-voices \
--language en-US \
--output table
````
[<img src="https://i.imgur.com/Qd8TUO8.png">](https://i.imgur.com/Qd8TUO8.png)

---

##
### 01 -aws-lexicon.xml
````xml
<?xml version="1.0" encoding="UTF-8"?>
<lexicon version="1.0"
    xmlns="http://www.w3.org/2005/01/pronunciation-lexicon"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.w3.org/2005/01/pronunciation-lexicon
    http://www.w3.org/TR/2007/CR-pronunciation-lexicon-20071212/pls.xsd"
    alphabet="ipa"
    xml:lang="en-US">
    <lexeme>
        <grapheme>aws</grapheme>
        <alias>Amazon Web Service</alias>
    </lexeme>
</lexicon>
````

### 02 - add lexicon
````bash
aws polly put-lexicon \
--name awsLexicon \
--content file://aws-lexicon.xml \
--region ca-central-1
````

### 03 - generate text
````bash
aws polly synthesize-speech --text 'Hello AWS World!' \
--voice-id Joanna \
--output-format mp3 hello.mp3 \
--lexicon-names="awsLexicon" \
--region ca-central-1
````

### 04 - test
````bash
#cvlc - console no UI
cvlc hello.mp3
````
[<img src="https://i.imgur.com/4b0HXl2.png">](https://i.imgur.com/4b0HXl2.png)
