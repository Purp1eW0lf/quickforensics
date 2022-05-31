# Background Activity Moderator

## To Prepare
Fire up calc!

```powershell
calc.exe

## To invesigate

Two options

You can query the resgistry directly. But notice you don't get timestamps or the SIDs converted to usernames


```powershell
reg query "HKLM\SYSTEM\CurrentControlSet\Services\bam\state\UserSettings" /s
```


Or, use this PowerShell Script
* I made a small correction to the existing script, as a path had changed

```powershell
# Download
wget -usebasicparsing https://raw.githubusercontent.com/mgreen27/Invoke-LiveResponse/master/Content/Other/Get-BAMParser.ps1 -outfile Get-BAMParser.ps1
#Use
./Get-BAMParser.ps1
```

## Example output
<img width="1392" alt="image" src="https://user-images.githubusercontent.com/44196051/171148654-5c4d88a1-1437-4cd5-a01b-d678e6031127.png">

<img width="1423" alt="image" src="https://user-images.githubusercontent.com/44196051/171148955-a57a0863-c3a9-4e37-8f45-f2677e3189f0.png">
