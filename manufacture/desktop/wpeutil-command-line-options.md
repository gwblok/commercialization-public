---

Description: 'Wpeutil Command-Line Options'
ms.assetid: 6537713a-510e-40cd-8518-d1150422bfe8
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Wpeutil Command-Line Options'

ms.date: 05/02/2017
ms.topic: article
ms.custom: RS5
---

# Wpeutil Command-Line Options


The Windows PE utility (Wpeutil) is a command-line tool that enables you to run commands during a Windows PE session. For example, you can shut down or restart Windows PE, enable or disable a firewall, set language settings, and initialize a network.

## <span id="Wpeutil_Command-Line_Options"></span><span id="wpeutil_command-line_options"></span><span id="WPEUTIL_COMMAND-LINE_OPTIONS"></span>Wpeutil Command-Line Options


Wpeutil uses the following conventions.

**Wpeutil** {command} \[*argument*\]

For example:

```
Wpeutil Shutdown
Wpeutil Enablefirewall
Wpeutil SetMuiLanguage de-DE
```

> [!important]
> Wpeutil can only accept one command per line.



| Command | Description |
| --- | ---  |
| **CreatePageFile [/path=&lt;path&gt;] [/size=&lt;size&gt;]** | Creates a page file to a specified path and size. The default path is C:\pagefile.sys and default size is 64 megabytes. At least one option must be specified. For example:<br></br>`Wpeutil CreatePageFile /path=C:\pagefile.sys`<br></br>-or-<br></br>`Wpeutil CreatePageFile /path=C:\pagefile.sys /size=128 <br></br>**Important**  <br></br>If a page file exists, the **/CreatePageFile** option must be set equal to or greater than the current size of the page file or the command will fail. |
| **DisableExtendedCharactersForVolume &lt;path_on_target_volume&gt;** | Disables extended character support for DOS-compatible file names (8.3 format) for the volume that contains <em>path on target volume</em>. This command only applies to NTFS volumes. The <em>path on target volume</em> must specify the root of the volume. For example:<br></br>`Wpeutil DisableExtendedCharactersForVolume C:\`<br></br>If disabled, all files that have been created with extended characters will be converted to a short file name. |
| **DisableFirewall** | Disables a firewall. For example:<br></br>`Wpeutil DisableFirewall` |
| **EnableExtendedCharactersForVolume** <em>&lt;path_on_target_volume&gt;</em> | Allows 8.3 format file names to contain extended characters on the volume that contains <em>path on target volume</em>. This command only applies to NTFS volumes. The <em>path on target volume</em> must specify the root of the volume. For example:<br></br>`Wpeutil EnableExtendedCharactersForVolume C:\` <br></br> **Note**:<br></br>If you are installing an operating system in a language that has extended characters that are enabled by default, such as ja-JP or ko-KR, or using a copy of Windows PE in a language that doesn't have extended characters enabled, such as en-US, the installation will cause a Chkdsk error during first boot. Enabling this option before you install to that volume will prevent Chkdsk command from running. |
| **EnableFirewall** | Enables a firewall. For example:<br></br>`Wpeutil EnableFirewall` |
| **InitializeNetwork [/NoWait]** | Initializes network components and drivers, and sets the computer name to a randomly-chosen value. The **/NoWait** option will skip the time where your PC would otherwise wait to acquire an IP address. If you don't use **/NoWait**, Windows PE will wait to acquire an address before it finishes loading your WinPE session. **/NoWait** is helpful for environments that don't use DHCP.<br></br> For example:<br></br>`Wpeutil InitializeNetwork`<br></br>`wpeutil InitializeNetwork /NoWait` |
| **ListKeyboardLayouts** <em>&lt;LCID&gt;</em> | Lists the supported keyboard layouts (Name and ID) for a given Locale ID (LCID) value. The keyboard layouts will also be updated in the registry under the key: **HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\CurrentVersion\WinPE\KeyboardLayouts**. For example:<br></br>`Wpeutil ListKeyboardLayouts 0x0409`<br></br>-or-<br></br>`Wpeutil ListKeyboardLayouts 1033`<br></br>For a list of valid Locale IDs, see [Locale ID (LCID) Chart](http://go.microsoft.com/fwlink/?LinkId=209839). |
| **Reboot** | Restarts the current Windows PE session. For example:<br></br>`Wpeutil Reboot`|
| **SaveProfile** | Stops logging and saves the custom profile to the location the user specified earlier with the **Dism /enable-profiling** command. For more information about the **/enable-profiling** command-line option, see [DISM Windows PE Servicing Command-Line Options](dism-windows-pe-servicing-command-line-options.md). For example:<br></br>`Wpeutil SaveProfile profile_file_name &quot;short description&quot;` |
| **SetKeyboardLayout** <em>&lt;keyboard_layout_ID&gt;</em> | Sets the keyboard layout in the current Windows PE session. This will take effect for processes after the command succeeds. To obtain a list of supported keyboard layouts, enter:<br></br>`Wpeutil ListKeyboardLayouts 0x0409`<br></br>To set the keyboard for en-US, for example:<br></br>`Wpeutil SetKeyboardLayout 0409:00000409` |
|**SetMuiLanguage** <em>&lt;language-name&gt;</em>[**;**<em>&lt;language-name&gt;</em>]  | Sets the language. <em>&lt;language-name&gt;</em> uses the international language code format (for example, en-US for the U.S. English language). You can specify multiple languages in priority order, by separating them with a semicolon. For example:<br></br>`Wpeutil SetMuiLanguage de-DE;en-US` |
| **SetUserLocale** <em>&lt;language-name&gt;</em>[**;**<em>&lt;language-name&gt;</em>] | Sets the user locale. <em>&lt;language-name&gt;</em> uses the international language code format (for example, en-US for the U.S. English language). You can specify multiple languages in priority order, by separating them with a semicolon. For example:<br></br>`Wpeutil SetUserLocale de-DE;en-US` |
| **Shutdown** | Shuts down the current Windows PE session. For example:<br></br>`Wpeutil Shutdown`<br></br>**Note**:<br></br>You can also do the following in the Command Prompt window: <ul><li>Click the **Close** button</li><li>Type EXIT</li></ul> |
| **UpdateBootInfo** | Populates the registry with information about how Windows PE boots. <br></br>After you run this command, query the registry. For example:<br></br>`wpeutil UpdateBootInfo reg query HKLM\System\CurrentControlSet\Control /v PEBootType`<br></br>The results of this operation might change after loading additional driver support.<br></br>To determine where Windows PE is booted from, examine the following:<ul><li>**PEBootType**: Error, Flat, Remote, Ramdisk:SourceIdentified Ramdisk:SourceUnidentified, Ramdisk:OpticalDrive</li><li>**PEBootTypeErrorCode**: HRESULT code</li><li>**PEBootServerName**: Windows Deployment Services server name</li><li>**PEBootServerAddr**: Windows Deployment Services server IP address</li><li>**PEBootRamdiskSourceDrive**: Source drive letter, if available.</li><li>**PEFirmwareType**: Firmware boot mode: 0x1 for BIOS, 0x2 for UEFI.</li></ul><br></br>If you are not booting Windows Deployment Services, the best way to determine where Windows PE booted from is to first check for PEBootRamdiskSourceDrive registry key. If it is not present, scan the drives of the correct PEBootType and look for some kind of tag file that identifies the boot drive. |
| **WaitForNetwork** | Waits for the network card to be initialized. Use this command when creating scripts to make sure that the network card has been fully initialized before continuing. |
|**WaitForRemovableStorage** | During the Windows PE startup sequence, this command will block startup until the removable storage devices, such as USB hard drives, are initialized. For example:<br></br>`Wpeutil WaitForRemovableStorage`<br></br>**Note**:<br></br>This spelling of **WaitForRemovableStorage** is correct. |     

 


## <span id="related_topics"></span>Related topics


[WinPE for Windows 10](winpe-intro.md)

[WinPE: Mount and Customize](winpe-mount-and-customize.md)

[DISM Windows PE Servicing Command-Line Options](dism-windows-pe-servicing-command-line-options.md)










