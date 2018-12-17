---
author: kpacquer
Description: 'Push-button reset features by default restore only drivers (installed through INF packages) and preinstalled Windows apps.'
ms.assetid: 909227f2-8969-4ab3-b296-c54977a38977
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Recovery components
ms.author: kenpacq
ms.date: 05/02/2017
ms.topic: article
ms.custom: RS5
---

# Recovery components


Push-button reset features by default restore only drivers (installed through INF packages) and preinstalled Windows apps. To configure the features to restore other customizations such as settings and Windows desktop applications, you will need to prepare one or more customization packages which contain the customizations. These customizations packages are in the form of provisioning packages (.ppkg).

Push-button reset looks for, and automatically restores provisioning packages which are located in the folder C:\\Recovery\\Customizations. **New in Windows 10, version 1809**: Windows will also look for and restore certain customizations in the C:\\Recovery\\AutoApply folder. If customizations are in this folder and extensibility points aren't configured, the customizations in this folder will be restored.

To protect the packages from tampering or accidental deletion, the Write/Modify permissions of C:\\Recovery\\Customizations should be restricted to the local Administrators user group.

Some settings and customizations cannot be included in provisioning packages. Instead, you can restore them using an unattend file applied using the Push-button reset extensibility points. For settings which are supported by both provisioning packages and unattend, it is recommended that you specify them using only one of the mechanisms, not both. To learn more, see [How push-button reset features work](how-push-button-reset-features-work.md).

## <span id="auto-apply"></span>Auto-Apply folders

**New in Windows 10, version 1809** Auto-apply folders make Push-button reset customizations easier to configure for the reset experience. This new method takes XML and related asset files and copies them to their corresponding location on the restored OS. Using Auto-apply folders simplifies the configuration process and helps to eliminate commonly-made mistakes that result in a misconfigured PBR.

Auto-apply folders can't be used in conjunction with the legacy configuration method that utilizes extensibility points. 

> [!important]
> If both extensibility points are configured and Auto-apply folders are present in C:\\Recovery, the Auto-apply folders will be ignored.

### Auto-apply customizations

The following customizations are supported by Auto-apply folders:

-    TaskbarLayoutModification.xml
-    LayoutModification.xml
-    OOBE
-    Unattend.xml

### Configure Auto-apply

To use Auto-apply folders, you have to copy configuration files and any related asset files C:\\Recovery\\AutoApply. Related asset files are files that the configuration files rely on, like an graphic that unattend will set as a wallpaper or .lnk files that are used by TaskbarLayoutModification.xml.

During a recovery, files in this AutoApply folder will get copied to the correct folders in the restored image. For example, when you place unattend.xml in the AutoApply folder, it will be copied to the C:\\Windows\\Panther folder during the recovery process.

The following table shows the available customizations and where to copy the configuration and related asset files so that PBR can restore them to the restored OS:


| Customization | Copy configuration to: | Copy related assets to: |
| --- | --- | --- |
| TaskbarLayoutModification.xml | C:\\Recovery\\AutoApply\\ | C:\\Recovery\\AutoApply\\Customizationfiles |
| LayoutModification.xml | C:\\Recovery\\AutoApply\\ | C:\\Recovery\\AutoApply\\Customizationfiles |
| OOBE.xml | Copy %windir%\\System32\\OOBE\info and all it's contents to C:\\Recovery\\AutoApply\\OOBE | N/A - The copied OOBE\\Info folder should include all the files to support OOBE |
| Unattend.xml | C:\\Recovery\\AutoApply\\ | C:\\Recovery\\AutoApply\\CustomizationFiles |


## <span id="desktop-apps"></span>Capturing Windows desktop applications using Windows User State Migration Tool (USMT)'s ScanState tool


The Windows User State Migration Tool (USMT) ScanState.exe has been updated in Windows 10 to support capturing Windows desktop applications applications. This functionality can be activated by specifying the `/apps` option.

When `/apps` is specified, ScanState uses a set of application discovery rules to determine what should be captured, and stores the output as a reference device data image inside a provisioning package. In general, the reference device data includes the following:

-   Windows desktop applications installed using either Microsoft Windows Installer or other installers
-   All files and folders outside of the Windows namespace (in other words, outside of \\Windows, \\Program Files, \\Program Files (x86), \\ProgramData, and \\Users). This applies only to the volume on which Windows is installed.
-   Not captured: Windows apps.
-   Not captured: User state/data.

You can also specify additional rules to include or exclude specific files, folders, and registry settings. For example, if you are using ScanState during factory deployment, you might need to exclude manufacturing-specific tools so that they will not be restored when end users use Push-button reset features. To specify additional rules, you will need to author a migration XML and specify the `/i` option when using ScanState.exe.

ScanState’s /apps option also supports the following optional parameters:

| Parameter | Use |
| --- | --- |
| `+/-sysdrive` | Specifies whether applications, files, and folders outside of the Windows namespace should be captured.<p>If `+sysdrive` is specified, all contents on the system drive are examined and eligible to be captured according to the discovery rules.<p>If `-sysdrive` is specified, only contents within the Windows namespace are examined and eligible to be captured according to the discovery rules.<p>`+sysdrive` is the default. |
| `+/-oeminfo` | Specifies whether the OEM-specific help and support info should be captured.<p>If `+oeminfo` is specified, OEM and support info are captured.<p>If `-oeminfo` is specified, OEM and support info are not captured.<p>`+oeminfo` is the default. |




**Important**  
-   Although push-button reset features can restore multiple provisioning packages, only one of the packages can contain reference device data image captured using ScanState.
-   ScanState should be used only after all customizations have been applied to the PC. It does not support appending additional changes to an existing reference device data image.
-   A provisioning package captured using ScanState.exe can only be applied using push-button reset features and deployment media created using Windows Imaging and Configuration Designer (ICD). It cannot be applied using tools such as DISM or USMT’s LoadState.exe.
-   When you prepare ScanState for capturing customizations, you should exclude Windows Defender settings to prevent possible failures during recovery that can be caused by file conflicts. For more information, see Step 1 in [Deploy push-button reset features](deploy-push-button-reset-features.md).


## <span id="restoring_settings_using_unattend.xml_and_extensibility_scripts"></span>Restoring settings using unattend.xml and extensibility points

> [!TIP]
> **New in Windows 10, version 1809** You can use Auto-apply folders to automatically restore unattend.xml, layoutmodification.xml, and oobe.xml. If using Auto-apply folders, you don't have to configure extensibilty scripts as outlined below.

Most settings which are configured using unattend.xml and other configuration files (e.g. oobe.xml, LayoutModification.xml) cannot be restored using provisioning packages. Instead, you will need to use the Push-button reset extensibility points in order to restore them during recovery. These extensibility points allow you run scripts which can:

-   Inject an unattend.xml into the recovered OS
-   Copy other configuration files and assets into the recovered OS

**Important**  
-   You should not use unattend.xml (or other mechanisms) to boot the recovered OS into Audit Mode. The recovered OS must remain configured to boot to OOBE.
-   A copy of the configuration files and assets which need to be restored must be placed under C:\\Recovery\\OEM. Contents in this folder are not modified by push-button reset features and are automatically backed up to recovery media created using the **Create a recovery drive** utility. To protect the unattend.xml and configuration files/assets from tampering or accidental deletion, Write/Modify permissions of C:\\Recovery\\OEM should be restricted to the local Administrators user group.



To learn how to author scripts to be run using extensibility points, see [Add a script to push-button reset features](add-a-script-to-push-button-reset-features.md).

To learn how to use ScanState to capture and store the resulting PPKG under C:\\Recovery\\Customizations, which is restored automatically during PBR, see [Deploy push-button reset features using ScanState](deploy-push-button-reset-features.md).

## <span id="Recovery_strategies_for_common_customizations"></span><span id="recovery_strategies_for_common_customizations"></span><span id="RECOVERY_STRATEGIES_FOR_COMMON_CUSTOMIZATIONS"></span>Recovery strategies for common customizations


The following table outlines the recovery strategy for common customizations which are described in the User Experience Windows Engineering Guide (UX WEG) as well as those covered in the OEM Policy Document (OPD). For up-to-date details on these customizations, refer to the latest version of the UX WEG and OPD.


|                                  Customization                                  |                                                                                      How it is configured                                                                                      |                                                              How it can be restored during PBR                                                               |
|---------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                               OOBE – HID pairing                                |                                                 Settings in the <code>&lt;hidSetup&gt;</code> section of OOBE.xml and images (e.g. .png files)                                                 |           <ul><li>Use PBR extensibility script to restore OOBE.xml and images from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>           |
|                                 OOBE – OEM EULA                                 |                                 <code>&lt;Eulafilename&gt;</code> setting in OOBE.xml and license terms .rtf file(s) stored under %WINDIR%\System32\Oobe\Info                                  |         <ul><li>Use PBR extensibility script to restore OOBE.xml and .rtf files from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>         |
|                   OOBE – Preconfigured language and time zone                   |                                                               Settings in the <code>&lt;defaults&gt;</code> section of OOBE.xml                                                                |                <ul><li>Use PBR extensibility script to restore OOBE.xml from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>                 |
|                        OOBE – Hide mobile broadband page                        |                                                                 Microsoft-Windows-WwanUI \| NotInOOBE setting in unattend.xml                                                                  |              <ul><li> Use PBR extensibility points to restore unattend.xml from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>              |
|                          OOBE – OEM Registration page                           |                                                   Settings in the &lt;registration&gt; section of OOBE.xml and HTML files for in-place links                                                   |        <ul><li> Use PBR extensibility script to restore OOBE.xml and HTML files from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>         |
|                         Start – Pinned tiles and groups                         |      LayoutModification.xml stored under %SYSTEMDRIVE%\Users\Default\AppData\Local\Microsoft\Windows\Shell or settings under Microsoft-Windows-Shell-Setup \| StartTiles in unattend.xml       | <ul><li>Use PBR extensibility points to restore LayoutModification.xml or unattend.xml from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>  |
|                          Start – Prepopulated MFU list                          |                                             LayoutModification.xml stored under %SYSTEMDRIVE%\Users\Default\AppData\Local\Microsoft\Windows\Shell                                              |         <ul><li>Use PBR extensibility points to restore LayoutModification.xml from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>          |
|                             Continuum – Form factor                             |                      Settings in unattend.xml:<ul><li>Microsoft-Windows-Deployment \| DeviceForm</li><li>Microsoft-Windows-GPIOButtons \| ConvertibleSlateMode</li></ul>                       |              <ul><li> Use PBR extensibility points to restore unattend.xml from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>              |
|                            Continuum – Default mode                             |                                                              Microsoft-Windows-Shell-Setup \| SignInMode setting in unattend.xml                                                               |              <ul><li>Use PBR extensibility points to restore unattend.xml from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>               |
|                 Desktop – Default and additional accent colors                  |                RunSynchronous command in unattend.xml which adds the AGRB hex color values to the registry under HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Themes\Accents                 |              <ul><li> Use PBR extensibility points to restore unattend.xml from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>              |
|                           Desktop – Background image                            |                                   Microsoft-Windows-Shell-Setup \| Themes \| DesktopBackground setting in unattend.xml and image (e.g. .jpg/.png/.bmp file)                                    | <ul><li> Use PBR extensibility points to restore unattend.xml and background image file from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul> |
|                         Desktop – Pinned taskbar items                          |    Settings under Microsoft-Windows-Shell-Setup \| TaskbarLinks in unattend.xml and shortcut (.lnk) files stored in a folder under %ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\    |      <ul><li> Use PBR extensibility points to restore unattend.xml and .lnk files from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>       |
|                             Desktop – Systray icons                             |                                                        Settings under Microsoft-Windows-Shell-Setup \| NotificationArea in unattend.xml                                                        |              <ul><li>Use PBR extensibility points to restore unattend.xml from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>               |
|           Mobile broadband – Rename "WiFi" to "WLAN" in network list            |                                                             Microsoft-Windows-SystemSettings \| WiFiToWlan setting in unattend.xml                                                             |              <ul><li>Use PBR extensibility points to restore unattend.xml from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>               |
|         Mobile broadband – Enable Network Selection control in Settings         |                                                      Microsoft-Windows-SystemSettings \| DisplayNetworkSelection setting in unattend.xml                                                       |              <ul><li> Use PBR extensibility points to restore unattend.xml from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>              |
|                    PC Settings – Preinstalled settings apps                     | Settings apps are preinstalled in the same way as any other app, and automatically appear in Settings. Capability declared in the app manifest determines whether it is a settings app or not. |                                                  Restored automatically along with other preinstalled apps                                                   |
|                    Default browser and handlers of protocols                    |                                      Default application association settings XML file imported using the /Import-DefaultAppAssociations command in DISM                                       |                                      <ul><li>Use PBR extensibility points to [Import Default App associations](export-or-import-default-application-associations.md)</li></ul> or <ul><li>Use an unattend file with a [RunSynchronousCommand](https://docs.microsoft.com/windows-hardware/customize/desktop/unattend/microsoft-windows-deployment-runsynchronous-runsynchronouscommand) to [Import Default App associations](export-or-import-default-application-associations.md), adding the unattend file to the auto-apply folders</li></ul>
|
|                   Support information in Contact Support app                    |                                                Settings under Microsoft-Windows-Shell-Setup \| OEMInformation in unattend.xml and logo.bmp file                                                |       <ul><li> Use PBR extensibility points to restore unattend.xml and .bmp file from C:\Recovery\OEM</li></ul>or<ul><li>Auto-apply folders</li></ul>       |
|                             Store content modifier                              |                                                       Microsoft-Windows-Store-Client-UI \| StoreContentModifier setting in unattend.xml                                                        |                                      <ul><li> Use PBR extensibility points to restore unattend.xml from C:\Recovery\OEM</li> or <li>Auto-apply folders</li>                                      |
| Windows desktop applications (including driver applets installed via setup.exe) |                                                                                    MSI or custom installers                                                                                    |             Use ScanState to capture and store the resulting PPKG under C:\Recovery\Customizations, which is restored automatically during PBR.              |
|                                  RDX contents                                   |                                                                                     See UX WEG for details                                                                                     |                                                              Should not be restored during PBR                                                               |

