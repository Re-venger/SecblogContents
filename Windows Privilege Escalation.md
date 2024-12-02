


#### What can be exploited
- misconfigurations on windows services or scheduled tasks.
- Excessive privileges assigned to our account.
- Vulnerable Software.
- Missing windows security patches.


#### Where to look for Passwords or Other sensitive informations

**Console History**
use **%userprofile%** in cmd.
for powershell replace this with **$Env:userprofile**
````shell-session
type %userprofile%\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt
````


*Windows Deployment Service - allows centralised execution of windows OS on many hosts. these are also called unattended installation*
Key location for this are
- C:\Unattend.xml
- C:\Windows\Panther\Unattend.xml
- C:\Windows\Panther\Unattend\Unattend.xml
- C:\Windows\system32\sysprep.inf
- C:\Windows\system32\sysprep\sysprep.xml


Listing all users on window and spawning shell
1. list all users and domains with `cmdkey /list`
2. use `runas /savecred /user:admin cmd.exe` to get shell.


IIS configurations

look for db or admin or  any kind of username and passwords for the web configurations
- C:\inetpub\wwwroot\web.config
- C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\web.config
- to find easily
```shell-session

type C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\web.config | findstr connectionString
```

Retrieve Credentials from software: PuTTY for ex.

PuTTY won't allow users to store their SSH password, it will store proxy configurations that include cleartext authentication credentials.
```shell-session
reg query HKEY_CURRENT_USER\Software\SimonTatham\PuTTY\Sessions\ /f "Proxy" /s
```



#### Scheduled Tasks and AlwaysInstallElevated

- schtasks - checks for the scheduled tasks.
- icacls - checks for file permissions.
- AlwaysInstallElevated - always installs the msi packages with elevated privileges






All of the services configurations are stored on the registry under `HKLM\SYSTEM\CurrentControlSet\Services\`