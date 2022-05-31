# Certutil cache

## To prepare

```powershell
certutil.exe -urlcache -split -f https://github.com/BloodHoundAD/SharpHound/releases/download/v1.0.3/SharpHound-v1.0.3.zip sharphound.zip
certutil.exe -urlcache -split -f https://raw.githubusercontent.com/PowerShellMafia/PowerSploit/master/Privesc/PowerUp.ps1 PowerUp.ps1
```
<img width="1352" alt="image" src="https://user-images.githubusercontent.com/44196051/171147278-075100ef-c9ea-4c30-85de-978f5bdc5b2d.png">

## To investigate

Go looking for what's going on there
```powershell
certutil.exe -urlcache | 
select-string  -Pattern 'ocsp|wininet|winhttp|complete|update|r3'  -NotMatch | 
sort
```

<img width="821" alt="image" src="https://user-images.githubusercontent.com/44196051/171147357-ece409d0-a658-4340-985f-aac58d5f3c14.png">

## Example output

<img width="1419" alt="image" src="https://user-images.githubusercontent.com/44196051/171147543-19dabafa-e28f-4ce4-bfa2-6df0239786f7.png">
