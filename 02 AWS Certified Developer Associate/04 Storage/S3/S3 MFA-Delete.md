# S3 MFA-Delete

## Acronym
* S3 - Simple Storage Service
* MFA - Multi-Factor Authentication

## Doc

## Intro
* MFA forces user to generate a code on a device (usually a mobile phone or hardware) before doing important operations on S3
* To use MFA-Delete, enable Versioning on the S3 bucket
* You will need MFA to
    * permanently delete an object version
    * suspen versioning on the bucket
* You won't need MFA for
    * enabling versioning
    * listing deleted versions
* Only the bucket owner (rrot account) can enabled/disable MFA-Delete
