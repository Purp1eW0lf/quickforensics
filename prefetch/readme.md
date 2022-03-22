# Prefetch
## What is Prefetch
Prefetch (also known as prefetcher) is a caching technique whereby an application is monitored and catalogued for the first few seconds it is launched, to make re-launching more efficient. 

## Where is Prefetch
`C:\Windows\Prefetch\x.pf`

## Leveraging Prefetch

Eric Zimmerman has released some amazing digital forensics tools for the community.

For our case, we are using his PECMD.exe, which will parse the prefetch file and offer us more data

```powershell
Install
# Click link about to download, or use the following PowerShell
wget -usebasicparsing https://f001.backblazeb2.com/file/EricZimmermanTools/PECmd.zip -outfile PECmd.zip ; 
Expand-Archive ./PECmd.zip . ; 
ls *.exe, *.pf
```

Usage
```powershell
.\PECmd.exe -f ./*.pf -mp
```
