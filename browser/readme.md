# Brower forensics

Locations
```
Chrome :\Users\*\AppData\Local\Google\Chrome\User Data\Default\History
Edge C:\Users\*\AppData\Local\Microsoft\Edge\User Data\Default\History
Safari /System/Volumes/Data/Users/*/Library/Safari/History.db , Downloads.plist
Firefox C:\Users\*\AppData\Roaming\Mozilla\Firefox\Profiles\*\Downloads.json, Places.sqlite
```

[Thread for how to analyse in detail](https://twitter.com/Purp1eW0lf/status/1498359576739164167?s=20&t=nLxtOHrh5uw79X5Bn92Efw)

But in short:

```bash
sqlite3 [history file]
.mode line
select * from downloads;
```
