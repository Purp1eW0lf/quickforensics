# Cmdline History

## Cmd history

If a threat actor leaves their session open, you can retrieve the commands they ran

```cmd
doskey /history
```

<img width="481" alt="image" src="https://user-images.githubusercontent.com/44196051/172158567-8e15e231-dce6-4b49-8051-79c7e59f8606.png">

If they close the prompt, then you are out of luck and will have to image the machine and use volatilty to pull out the commands run

## Powershell history

Other than the PowerShell Operational log (EVTX), you can leverage PSReadline History

I have written in detail about this elsewhere: https://labs.jumpsec.com/no-logs-no-problem-incident-response-without-windows-event-logs/#PSReadLine

```powershell
$Users = (Gci C:\Users\*\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt).FullName;
$Pasts = @($Users);
foreach ($Past in $Pasts) {
    write-host "`n----User Pwsh History Path $Past---" -ForegroundColor Magenta; 
    get-content $Past
}
```

![image](https://user-images.githubusercontent.com/44196051/172159460-df2ff680-585d-4395-87f1-2a8d56b7d309.png)
