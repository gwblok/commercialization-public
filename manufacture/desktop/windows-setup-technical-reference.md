---

Description: Windows Setup Technical Reference
ms.assetid: f0fa0e04-e8ca-43b8-a789-0ef854e09333
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Windows Setup Technical Reference

ms.date: 05/02/2017
ms.topic: article


---

# Windows Setup Technical Reference


Windows Setup is a bootable program that installs the Windows operating system.

## <span id="BKMK_APP"></span><span id="bkmk_app"></span>Practical applications


-   You can install or upgrade the Windows operating system on a PC from a USB key, a mounted .ISO file, DVD, or network device.
-   You can automate the Windows installation process, including the configuration of drivers, packages, files, and Windows system settings by using answer files created from [Windows System Image Manager Technical Reference](https://msdn.microsoft.com/library/windows/hardware/dn922445).
-   You can use Windows Setup as an installer for your own customized Windows images.
-   You can use the menus in Windows Setup to prepare the hard drives before installation.

## <span id="What_s_New"></span><span id="what_s_new"></span><span id="WHAT_S_NEW"></span>What's New


-   Windows 8.1 upgrades are different from previous Windows upgrade scenarios. For more info, see [Windows 8.1 Upgrade Scenarios for OEMs](windows-81-upgrade-scenarios-for-oems.md).

-   Windows Setup cannot be used to perform automated upgrades to most editions of Windows 8.1.

    For volume-licensed editions of Windows, we've added a new command-line option, `setup /auto`, to help enable upgrades. Note, we only plan to use this option for upgrades to Windows 8.1, and we may remove the option in future versions of Windows. For more info, see [Windows Setup Command-Line Options](windows-setup-command-line-options.md).

-   [Settings for Automating OOBE](settings-for-automating-oobe.md): The [NetworkLocation](https://msdn.microsoft.com/library/windows/hardware/dn923171) setting is no longer needed to automate OOBE. The functionality of the [ProtectYourPC](https://msdn.microsoft.com/library/windows/hardware/dn915741) setting has changed.

## <span id="BKMK_LINKS"></span><span id="bkmk_links"></span>See also


The following table contains links to resources related to this scenario.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Content type</th>
<th align="left">References</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Planning</strong></p></td>
<td align="left"><p><a href="windows-setup-scenarios-and-best-practices.md" data-raw-source="[Windows Setup Scenarios and Best Practices](windows-setup-scenarios-and-best-practices.md)">Windows Setup Scenarios and Best Practices</a> | <a href="windows-setup-automation-overview.md" data-raw-source="[Windows Setup Automation Overview](windows-setup-automation-overview.md)">Windows Setup Automation Overview</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Deployment</strong></p></td>
<td align="left"><p><a href="windows-setup-installation-process.md" data-raw-source="[Windows Setup Installation Process](windows-setup-installation-process.md)">Windows Setup Installation Process</a> | <a href="windows-81-upgrade-scenarios-for-oems.md" data-raw-source="[Windows 8.1 Upgrade Scenarios for OEMs](windows-81-upgrade-scenarios-for-oems.md)">Windows 8.1 Upgrade Scenarios for OEMs</a> | <a href="boot-from-a-dvd.md" data-raw-source="[Boot from a DVD](boot-from-a-dvd.md)">Boot from a DVD</a> | <a href="install-windows-from-a-usb-flash-drive.md" data-raw-source="[Install Windows from a USB Flash Drive](install-windows-from-a-usb-flash-drive.md)">Install Windows from a USB Flash Drive</a> | <a href="deploy-a-custom-image.md" data-raw-source="[Deploy a Custom Image](deploy-a-custom-image.md)">Deploy a Custom Image</a> | <a href="winpe-create-usb-bootable-drive.md" data-raw-source="[WinPE: Create USB Bootable drive](winpe-create-usb-bootable-drive.md)">WinPE: Create USB Bootable drive</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Operations</strong></p></td>
<td align="left"><p><a href="automate-windows-setup.md" data-raw-source="[Automate Windows Setup](automate-windows-setup.md)">Automate Windows Setup</a> | <a href="use-a-configuration-set-with-windows-setup.md" data-raw-source="[Use a Configuration Set with Windows Setup](use-a-configuration-set-with-windows-setup.md)">Use a Configuration Set with Windows Setup</a>| <a href="add-device-drivers-to-windows-during-windows-setup.md" data-raw-source="[Add Device Drivers to Windows During Windows Setup](add-device-drivers-to-windows-during-windows-setup.md)">Add Device Drivers to Windows During Windows Setup</a> | <a href="add-a-custom-script-to-windows-setup.md" data-raw-source="[Add a Custom Script to Windows Setup](add-a-custom-script-to-windows-setup.md)">Add a Custom Script to Windows Setup</a> | <a href="add-multilingual-support-to-windows-setup.md" >Add languages to Windows Setup</a> | <a href="boot-windows-to-audit-mode-or-oobe.md" data-raw-source="[Boot Windows to Audit Mode or OOBE](boot-windows-to-audit-mode-or-oobe.md)">Boot Windows to Audit Mode or OOBE</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Tools and settings</strong></p></td>
<td align="left"><p><a href="windows-setup-command-line-options.md" data-raw-source="[Windows Setup Command-Line Options](windows-setup-command-line-options.md)">Windows Setup Command-Line Options</a> | <a href="windows-setup-supported-platforms-and-cross-platform-deployments.md" data-raw-source="[Windows Setup Supported Platforms and Cross-Platform Deployments](windows-setup-supported-platforms-and-cross-platform-deployments.md)">Windows Setup Supported Platforms and Cross-Platform Deployments</a> | <a href="windows-setup-states.md" data-raw-source="[Windows Setup States](windows-setup-states.md)">Windows Setup States</a> | <a href="windows-setup-edition-configuration-and-product-id-files--eicfg-and-pidtxt.md" data-raw-source="[Windows Setup Edition Configuration and Product ID Files (EI.cfg and PID.txt)](windows-setup-edition-configuration-and-product-id-files--eicfg-and-pidtxt.md)">Windows Setup Edition Configuration and Product ID Files (EI.cfg and PID.txt)</a> | <a href="windows-setup-log-files-and-event-logs.md" data-raw-source="[Windows Setup Log Files and Event Logs](windows-setup-log-files-and-event-logs.md)">Windows Setup Log Files and Event Logs</a> | <a href="windows-setup-configuration-passes.md" data-raw-source="[Windows Setup Configuration Passes](windows-setup-configuration-passes.md)">Windows Setup Configuration Passes</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Related technologies</strong></p></td>
<td align="left"><p><a href="https://msdn.microsoft.com/library/windows/hardware/dn922445" data-raw-source="[Windows System Image Manager Technical Reference](https://msdn.microsoft.com/library/windows/hardware/dn922445)">Windows System Image Manager Technical Reference</a> | <a href="http://go.microsoft.com/fwlink/?LinkId=206281" data-raw-source="[Unattended Windows Setup Reference](http://go.microsoft.com/fwlink/?LinkId=206281)">Unattended Windows Setup Reference</a> | <a href="sysprep--system-preparation--overview.md" data-raw-source="[Sysprep (System Preparation) Overview](sysprep--system-preparation--overview.md)">Sysprep (System Preparation) Overview</a> | <a href="winpe-intro.md" data-raw-source="[WinPE for Windows 10](winpe-intro.md)">WinPE for Windows 10</a></p></td>
</tr>
</tbody>
</table>

 

 

 






