# open_lens_Win_installation
Open-lens-windows_installation 

First install the scoop:
allows script execution. You can check the current execution policy by running:
powershell
Get-ExecutionPolicy
Open PowerShell and run the following command to set the execution policy to 
'RemoteSigned':
powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
This command sets the execution policy for the current user only and allows locally created scripts to run 
without a digital signature. After setting the execution policy, try running the Scoop installation command
again:
powershell
iex (new-object net.webclient).downloadstring('https://get.scoop.sh')
After installing Scoop, make sure its installation directory is added to your system's 
PATH environment variable. The Scoop installation directory is typically C:\Users\
<YourUsername>\scoop\.
You can add it to the PATH by running the following command in the command 
prompt:
bash
[System.Environment]::SetEnvironmentVariable('PATH', 
[System.Environment]::GetEnvironmentVariable('PATH', 
[System.EnvironmentVariableTarget]::User) + ';C:\Users\<YourUsername>\
scoop\shims\', [System.EnvironmentVariableTarget]::User)
Scoop
scoop bucket add extras
scoop install openlens
Final step to revert back the policy :
To revert it :
Set-ExecutionPolicy Restricted -Scope CurrentUser
