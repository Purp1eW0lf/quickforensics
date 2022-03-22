# Background Activity Moderator


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
