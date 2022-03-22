# Prefetch

Prefetch files can be found on workstatons here:
`C:\Windows\Prefetch\x.pf`

Prefetch is totally absent on Windows SERVERS. Enable with the following
```powershell
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager\Memory Management\PrefetchParameters" /v EnablePrefetcher /t REG_DWORD /d 3 /f;
reg add "HKEY_LOCAL_MACHINE\Software\Microsoft\Windows NT\CurrentVersion\Prefetcher" /v MaxPrefetchFiles /t REG_DWORD /d 8192 /f;
Enable-MMAgent –OperationAPI;
net start sysmain
```

## Leveraging Prefetch

Install
```powershell
# Click link about to download, or use the following PowerShell
wget -usebasicparsing https://f001.backblazeb2.com/file/EricZimmermanTools/PECmd.zip -outfile PECmd.zip ; 
Expand-Archive ./PECmd.zip . ; 
ls *.exe, *.pf
```

Usage
```powershell
.\PECmd.exe -f ./*.pf -mp
```
