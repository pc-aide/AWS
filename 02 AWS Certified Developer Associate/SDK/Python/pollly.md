# polly
* 

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
aws polly describe-voices

---

## Available voices (O/P: text,json,table)
aws polly describe-voices \
--language en-US \
--ouput table
