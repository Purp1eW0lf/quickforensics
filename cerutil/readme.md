# Certutil cache

```powershell
certutil.exe -urlcache -split -f https://github.com/BloodHoundAD/SharpHound/releases/download/v1.0.3/SharpHound-v1.0.3.zip sharphound.zip
```

Go looking for what's going on there
```
certutil.exe -urlcache | select-string  -Pattern 'ocsp|wininet|winhttp|complete|update|r3'  -NotMatch | sort
```
