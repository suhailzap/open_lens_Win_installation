# OpenLens Windows Installation Guide

Welcome to the installation guide for OpenLens on Windows. Follow these steps to set up OpenLens using Scoop, a command-line installer for Windows. The process involves configuring PowerShell, installing Scoop, adding the Scoop installation directory to your system's PATH, and finally, installing OpenLens.

## Step 1: Configure PowerShell

Before installing Scoop, ensure that PowerShell allows script execution. Open PowerShell and run the following command to set the execution policy to 'RemoteSigned':

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

This command allows locally created scripts to run without a digital signature. After setting the execution policy, proceed to the next step.

![Configure PowerShell](images/configure_powershell.png)

## Step 2: Install Scoop

Now, let's install Scoop. Run the following command in PowerShell:

```powershell
iex (new-object net.webclient).downloadstring('https://get.scoop.sh')
```

This command downloads and installs Scoop on your system.

![Install Scoop](images/install_scoop.png)

## Step 3: Add Scoop to PATH

After installing Scoop, ensure its installation directory is added to your system's PATH environment variable. Run the following command in the command prompt:

```bash
[System.Environment]::SetEnvironmentVariable('PATH', [System.Environment]::GetEnvironmentVariable('PATH', [System.EnvironmentVariableTarget]::User) + ';C:\Users\<YourUsername>\scoop\shims\', [System.EnvironmentVariableTarget]::User)
```

Replace `<YourUsername>` with your actual username.

![Add Scoop to PATH](images/add_to_path.png)

## Step 4: Install OpenLens

With Scoop set up, install the OpenLens package using the following commands:

```powershell
scoop bucket add extras
scoop install openlens
```

This adds the necessary Scoop bucket and installs OpenLens on your system.

![Install OpenLens](images/install_openlens.png)

## Step 5: Revert Execution Policy (Optional)

If you want to revert the execution policy to its original state, run the following command:

```powershell
Set-ExecutionPolicy Restricted -Scope CurrentUser
```

This step is optional and is only necessary if you want to tighten the script execution policy.

![Revert Execution Policy](images/revert_policy.png)

Congratulations! You have successfully installed OpenLens on your Windows system using Scoop.

Note: The images used in this guide are for illustrative purposes and may not reflect the exact appearance of your system. Adjustments may be needed based on your specific configuration.
