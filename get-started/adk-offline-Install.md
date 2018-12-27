---
title: Install the ADK offline
Description: Instructions on how to build an offline installer for the Windows ADK
MSHAttr: 'PreferredLib:/library/windows/hardware'
ms.date: 05/02/2017
ms.topic: article
---
# Install the Windows ADK offline

To install the Windows ADK on a PC that does not have Internet access, first download the installer files on a PC that has internet access. Next, copy the installer files to a location that is accessible to the offline computer. Then run ADKSetup.exe using either the GUI or the command line.

## Install the Windows ADK on an offline computer using the GUI

1. On a PC that has Internet access, see [Download and install the Windows ADK](adk-install.md).
1. Click one of the links to download the ADK version you desire, and **Save** adksetup.exe to a location on your computer.
1. Copy the downloaded files to a location that the offline computer can access. For example, copy the files to removable media or to a file server that the computer can access.
1. On the offline computer, change directory to the location of the copied files.
1. Run ADKSetup.exe, and then select the Windows ADK features that you want to install.

## Install the Windows ADK on an offline computer using the command line

If you have a scenario where you need to silently install the Windows ADK, you can install using the command line.

1. On a PC that has Internet access, see [Download and install the Windows ADK](adk-install.md).
1. Click one of the links to download the ADK version you desire, and **Save** adksetup.exe to a location on your computer.
1.  Open a Command Prompt window as administrator.
1. Change to the directory that stores the Adksetup.exe file:

   ```PowerShell
   cd %userprofile%\downloads
   ```

1. Run adksetup.exe. Use /quiet to run the installer silently. Use /layout to specify where the offline install files will be copied to.

   ```PowerShell
   adksetup /quiet /layout c:\temp\ADKoffline
   ```

1. Copy the downloaded files to a location that the offline computer can access. For example, copy the files to removable media or to a file server that the offline computer can access.
1. On the offline computer, open a Command Prompt window as an administrator.
1. Change to the directory that contains adksetup.exe.
1. Run adksetup.exe. Use /quiet for a silent installation, /installpath to specify where to install the ADK, and /features to specify features. For example, install Deployment Tools and Windows PE to c:\ADK silently:

   ```PowerShell
   adksetup.exe /quiet /installpath c:\ADK /features OptionId.DeploymentTools OptionId.WindowsPreinstallationEnvironment
   ```

## Related topics

[ADKSetup Command-Line Syntax](https://technet.microsoft.com/en-us/library/dn621910.aspx).
