# Jump Lists


Quick way
```
 strings C:\Users\Frank\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations\* |sort
 ```
 
 
 Right way
 

```powershell
#install
 wget -usebasicparsing https://f001.backblazeb2.com/file/EricZimmermanTools/JLECmd.zip -outfile JLECmd.zip; 
Expand-Archive ./JLECmd.zip . ; 
ls JLECmd.exe 

#run and export to CSV. export to HTML is also an option
.\JLECmd.exe -d .\jump\ --all --mp --withDir --csv ./

#read the csv with selective headers
Import-Csv .\20220322131011_AutomaticDestinations.csv | 
select TargetIDAbsolutePath,InteractionCount,CreationTime,LastModified,TargetCreated,Targetmodified,TargetAccessed | 
sort InteractionCount -desc
```
 
