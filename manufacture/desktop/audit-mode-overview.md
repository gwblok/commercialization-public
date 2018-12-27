---

Description: Audit Mode Overview
ms.assetid: c4d7921f-0709-40bd-bbc5-38fd793d6b88
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Audit Mode Overview

ms.date: 11/28/2017
ms.topic: article


---

# Audit Mode Overview


When Windows boots, it starts in either Out-Of-Box Experience (OOBE) mode or in audit mode. OOBE is the default out-of-box experience that allows end users to enter their account information, select language, accept the Microsoft Terms of Service, and set up networking.

You can configure Windows to boot to audit mode instead. In audit mode, you can make additional changes to the Windows installation before you send the computer to a customer or capture the image for reuse in your organization. For example, you can install drivers included in a driver package, install applications, or make other updates that require the Windows installation to be running. When you use an answer file, Windows processes settings in the [auditSystem](auditsystem.md) and [auditUser](audituser.md) configuration passes.

When you boot to audit mode, you log into the system using the built-in administrator account. After you log on to the system, the built-in administrator account is immediately disabled during the [auditUser](audituser.md) configuration pass. The next time that the computer reboots, the built-in administrator account remains disabled. For more information, see [Enable and Disable the Built-in Administrator Account](enable-and-disable-the-built-in-administrator-account.md).

**Important**  
-   If you are in audit mode and a password-protected screen saver starts, you cannot log back on to the system. The built-in administrator account that was used to log on to audit mode is immediately disabled after logon.

    To disable the screen saver, either change the power plan through Control Panel or configure and deploy a custom plan. For more information, see [Create a Custom Power Plan](create-a-custom-power-plan-technicalreference.md).

-   Settings in an unattended answer file from the [oobeSystem](oobesystem.md) configuration pass do not appear in audit mode.

-   If you're running scripts, installers, and diagnostic tools on Windows 10 S in Audit Mode, you may have to enable manufacturing mode for Windows 10 S. See [Manufacturing mode](windows-10-s-manufacturing-mode.md) for details.
 

## <span id="Benefits_of_using_Audit_Mode"></span><span id="benefits_of_using_audit_mode"></span><span id="BENEFITS_OF_USING_AUDIT_MODE"></span>Benefits of using Audit Mode


In audit mode, you can do the following:

-   **Bypass OOBE.** You can access the desktop as quickly as possible. You do not have to configure default settings such as a user account, location, and time zone.

-   **Install applications, add device drivers, and run scripts.** You can connect to a network and access additional installation files and scripts. You can also install additional language packs and device drivers. For more information, see [Add a Driver Online in Audit Mode](add-a-driver-online-in-audit-mode.md).

-   **Test the validity of a Windows installation.** Before you deploy the system to end users, you can perform tests on the system without creating a user account. Then you can prepare the system to start in OOBE on the next boot.

-   **Add more customizations to a reference image.** This reduces the number of images that you have to manage. For example, you can create a single reference image that contains the basic customizations that you want to apply to all Windows images. You can then boot the reference image to audit mode and make additional changes that are specific to the computer. These changes can be customer-requested applications or specific device drivers.

## <span id="Boot_to_Audit_Mode"></span><span id="boot_to_audit_mode"></span><span id="BOOT_TO_AUDIT_MODE"></span>Boot to Audit Mode


You can boot to audit mode on a new or existing Windows installation. For more information, see [Boot Windows to Audit Mode or OOBE](boot-windows-to-audit-mode-or-oobe.md).



## <span id="related_topics"></span>Related topics


[Understanding Servicing Strategies](understanding-servicing-strategies.md)

[Windows Setup Configuration Passes](windows-setup-configuration-passes.md)

[How Configuration Passes Work](how-configuration-passes-work.md)

[Windows Setup Scenarios and Best Practices](windows-setup-scenarios-and-best-practices.md)

[Windows Setup Installation Process](windows-setup-installation-process.md)

[Windows Setup Automation Overview](windows-setup-automation-overview.md)

[Windows Setup Supported Platforms and Cross-Platform Deployments](windows-setup-supported-platforms-and-cross-platform-deployments.md)

[Windows 10 S manufacturing mode](windows-10-s-manufacturing-mode.md)

 

 






