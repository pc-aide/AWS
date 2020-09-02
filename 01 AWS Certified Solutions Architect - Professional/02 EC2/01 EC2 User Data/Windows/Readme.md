# EC2 User Data (Windows)

## Doc
* [ec2-eindows-user-data](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ec2-windows-user-data.html)

## Syntax for batch scripts
* Specify a batch script using the **script tag** (as html). Separate the commands using line breaks. For example:
### Persist
* By default, the user data scripts are executed one time when you launch the instance.
  To execute the user data scripts every time you reboot or start the instance,
  add **\<persist\>true\</persist\>** to the user data.

## Batch
* Demo-01:

````batch
<script>
echo Current date and time >> %SystemRoot%\Temp\test.log
echo %DATE% %TIME% >> %SystemRoot%\Temp\test.log
</script>
````
[<img src="https://i.imgur.com/5QdUup3.png">](https://i.imgur.com/5QdUup3.png)
[<img src="https://i.imgur.com/otG8DvD.png">](https://i.imgur.com/otG8DvD.png)
[<img src="https://i.imgur.com/9JjJN60.png">](https://i.imgur.com/9JjJN60.png)
