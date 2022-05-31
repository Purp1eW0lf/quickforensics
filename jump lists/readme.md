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

# run and export to HTML
.\JLECmd.exe -d C:\Users\frank\AppData\Roaming\Microsoft\Windows\Recent --all --mp --withDir --html ./

#run and export to CSV. export to HTML is also an option
.\JLECmd.exe -d C:\Users\*\AppData\Roaming\Microsoft\Windows\Recent\ --all --mp --withDir --csv ./ -q

# if you have collected the -ms files elsewhere, run .\JLECmd.exe -d .\Collected_Data\ --all --mp --withDir --csv ./

#open the HTML report
iex .\20220531113327_JLECmd_Automatic_Output_for_\index.xhtml

#or read the csv with selective headers
Import-Csv .\*.csv | 
select TargetIDAbsolutePath,InteractionCount,CreationTime,LastModified,TargetCreated,Targetmodified,TargetAccessed | 
sort InteractionCount -desc
```
 
## Example output

<img width="1422" alt="image" src="https://user-images.githubusercontent.com/44196051/171163129-3f49bded-62f5-47c5-b365-58ae9d1293e8.png">

<img width="919" alt="image" src="https://user-images.githubusercontent.com/44196051/171164116-11e5526b-a038-4134-aeae-8be5f300afea.png">
