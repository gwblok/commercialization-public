---

Description: 'DISM Operating System uninstall Command-Line Options'
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'DISM Operating System uninstall Command-Line Options'

ms.date: 04/25/2018
ms.topic: article
ms.custom: RS5
---

# DISM operating system uninstall command-line options

> [!important]
> OEMs shouldn't use this setting in imaging or manufacturing scenarios. This setting is for IT administrators.

Windows gives a user the ability to uninstall and roll back to a previous version of Windows. You can use DISM to:
-   Find out how many days after an upgrade that an OS can be uninstalled
-   Initiate an uninstall
-   Remove the ability for a user to uninstall a Windows upgrade
-   Set the number of days that a user has to uninstall a Windows upgrade

## /Get-OSUninstallWindow

Run this command against an online image to see how many days after an upgrade that an uninstall can be initiated.

Syntax:
```
DISM /Online /Get-OSUninstallWindow
```

## /Initiate-OSUninstall

Run this command against an online image to revert a PC to a previous Windows installation.

Syntax:
```
DISM /Online /Initiate-OSUninstall
```

## /Remove-OSUninstall


Run this command against an online image to remove the ability to roll back a PC to a previous installation of Windows.

Syntax:
```
DISM /Online /Remove-OSUninstall
```

## /Set-OSUninstallWindow

Run this command against an online image to set the number of days after an upgrade that an uninstall can be initiated.

Syntax:
```
DISM /Online /Set-OSUninstallWindow /Value:<days>
```

Example:
```
DISM /Online /Set-OSUninstallWindow /Value:30
```

## <span id="related_topics"></span>Related topics

[DISM Image Management Command-Line Options](dism-image-management-command-line-options-s14.md)

[Deployment Image Servicing and Management (DISM) Command-Line Options](deployment-image-servicing-and-management--dism--command-line-options.md)
