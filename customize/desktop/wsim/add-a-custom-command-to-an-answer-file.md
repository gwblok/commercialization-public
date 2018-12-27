---
title: Add a Custom Command to an Answer File
description: Add a Custom Command to an Answer File
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ea547858-0493-4e53-ae52-786555aca2b2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Add a Custom Command to an Answer File

The following procedure describes how to configure a custom command to run automatically during Windows Setup.

1. Open Windows System Image Manager (Windows SIM).
1. Create or open an answer file. For more information, see [Create or Open an Answer File](create-or-open-an-answer-file.md).
1. On the **Insert** menu, point to **Synchronous Command**, and then click a configuration pass on the submenu. The **Create Synchronous Command** dialog box opens.
1. In the **Enter command line** box, type the command-line syntax. In the **Order** box, select the order of the commands that will run, and then click **OK**. The command is added to the answer file in the selected configuration pass, as follows:

    * Commands that are added to the **1 windowsPE** configuration pass appear in the setting **Microsoft-Windows-Setup\\RunSynchronous**.
    * Commands that are added to the **4 specialize** or **6 auditUser passes** configuration pass appear in the setting **Microsoft-Windows-Deployment\\RunSynchronous**.
    * Commands that are added to the **7 oobeSystem** configuration pass appear in the setting **Microsoft-Windows-Shell-Setup\\FirstLogonCommands**.

      > [!Note]
      > If you create a user account that does not include administrative rights, commands that are added to the **7 oobeSystem** configuration pass may not be run. Details are as follows:
      > * If User Account Control is enabled, a dialog box appears when that user logs on for the first time. The dialog box provides an option to allow an administrator to apply the commands. If the user clicks **Cancel**, these commands are not run.
      > * If User Account Control is disabled, these commands are not run.

## Related topics

[Windows System Image Manager How-to Topics](windows-system-image-manager-how-to-topics.md)

[Create or Open an Answer File](create-or-open-an-answer-file.md)

[Configure Components and Settings in an Answer File](configure-components-and-settings-in-an-answer-file.md)

[Validate an Answer File](validate-an-answer-file.md)

[Hide Sensitive Data in an Answer File](hide-sensitive-data-in-an-answer-file.md)

[Add a Device Driver Path to an Answer File](add-a-device-driver-path-to-an-answer-file.md)

[Add a Package to an Answer File](add-a-package-to-an-answer-file.md)

[Find a Component, Setting, or Package in Windows SIM](find-a-component-setting-or-package-in-windows-sim.md)
