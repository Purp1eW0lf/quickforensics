# SRUM

Already examined how to leverage this artefact
https://twitter.com/Purp1eW0lf/status/1504491533487296517

# To Prepare
Pull Eric Zimmerman's parsing tool
```
wget -usebasicparsing https://f001.backblazeb2.com/file/EricZimmermanTools/SrumECmd.zip -outfile ./SrumECmd.zip; 
expand-archive ./SrumECmd.zip . ; 
ls *.exe, *.dat  
```

## To Investigate
Grab the srum file
```
C:\Windows\System32\sru\SRUDB.dat
```

Deploy the parser

```
.\SrumECmd.exe -f .\SRUDB.dat --csv .
```

## Example output
![image](https://user-images.githubusercontent.com/44196051/172158099-de9896f8-3802-4710-b9bd-afbb64fccf76.png)
![image](https://user-images.githubusercontent.com/44196051/172158106-72b675e7-99ac-420f-8ed1-85b28391bd3b.png)
![image](https://user-images.githubusercontent.com/44196051/172158120-16aad188-1c9c-4397-a597-fabc07218b9a.png)
![image](https://user-images.githubusercontent.com/44196051/172158129-96393a50-83ee-45a1-ac7f-d003b83997d6.png)
