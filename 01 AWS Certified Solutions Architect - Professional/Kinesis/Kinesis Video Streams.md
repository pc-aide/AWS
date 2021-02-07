# Kinesis Video Streams

## Intro
* One video stream per steaming device (producers)
  * Security cameras, body worn camera, smartphone
  * Can use a Kinesis Video Streams Producer library
* Underlying data is stored in S3 (but we don't have access to it)
* <ins>**Can't**<ins> output the stream data to S3 (must build custom solution)
* Consumers:
  * Consumed by EC2 instances for real time analysis, or in batch
  * Can leverage the Kinesis Video Stream Parser Library 
  * Integration with AWS Rekognition for facial detection
* Stream live video from devices to AWS
* Includes real time streaming, not just storage
* Capture data from millions of sources
* Send non-video time-serialized data
* Can durably store media data for specific period
* Available SDK 

---

## Producer Libraries
* Java Producer Library
* Android Producer Library
* C++ Producer Library
* C Producer Library

---

## E.g. 
* Video stream

[<img src="https://i.imgur.com/NeTwS04.png">](https://i.imgur.com/NeTwS04.png)

---

## Video Streaming & Rekognition
[<img src="https://i.imgur.com/A2lvUEE.png">](https://i.imgur.com/A2lvUEE.png)
