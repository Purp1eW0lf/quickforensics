# Jump Lists

## To Prepare
Open up some files like you have GUI access

```powershell
echo 'test data' >> example_file.ps1
notepad example_file.ps1
```

## To investigate

Two ways

### Quick and stupid way, my favourite
```
strings C:\Users\Frank\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations\* |sort
```
 
### Right way
 
Copy all related items
```powershell
copy-item C:\Users\*\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations\ . -recurse -verbose ```
```

Then use Eric's tool

```powershell
#install
 wget -usebasicparsing https://f001.backblazeb2.com/file/EricZimmermanTools/JLECmd.zip -outfile JLECmd.zip; 
Expand-Archive ./JLECmd.zip . ; 
ls JLECmd.exe 

#run and export to CSV. export to HTML is also an option
.\JLECmd.exe -d .\jump\ --all --mp --withDir --csv ./

#read the csv with selective headers
Import-Csv .\*.csv | 
select TargetIDAbsolutePath,InteractionCount,CreationTime,LastModified,TargetCreated,Targetmodified,TargetAccessed | 
sort InteractionCount -desc
```
 
