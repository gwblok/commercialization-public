---

Description: 'Enable and disable manufacturing mode in Windows 10 in S mode'
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'Windows 10 in S mode manufacturing mode'

ms.date: 04/25/2018
ms.topic: article


---

# Enable manufacturing mode

## Overview

To run scripts, installers, and diagnostic tools on the factory floor, Windows 10 in S mode and Windows 10 S have a manufacturing mode. This mode allows you to run unsigned code in Audit Mode. Enable manufacturing mode by adding a registry key to an offline image. Disable manufacturing mode by removing the registry key when booted into audit mode.


> [!IMPORTANT]
> Don't ship a Windows 10 in S mode PC with the registry in place. Remove the registry key prior to shipping the device.

Before shipping a Windows 10 in S mode PC, remove the manufacturing registry key and exclude it from recovery packages.


## Enable manufacturing mode

Here's how to enable manufacturing mode.

On your technician PC:

1. Mount your Windows 10 in S mode image.

    ```
    Dism /Mount-Wim /WimFile:D:\sources\install.wim /index:1 /MountDir:C:\mount\windows
    ```
    Where D: is your Windows 10 in S mode installation media.

2. Load the SYSTEM registry hive from your mounted image into regedit on your technician PC. We'll use a temporary hive called HKLM\Windows10S.

    ```
	reg load HKLM\Windows10S C:\Mount\Windows\Windows\System32\Config\System
    ```

3. Add the manufacturing registry key.

    ```
    reg add HKLM\Windows10S\ControlSet001\Control\CI\Policy /v ManufacturingMode /t REG_DWORD /d 1
    ```

4. Unload the registry hive from your technician PC.

    ```
    reg unload HKLM\Windows10S
    ```

5. Unmount the image and commit changes.

    ```
    Dism /Unmount-Image /MountDir:"C:\mount\windows" /Commit
    ```

The Windows 10 in S mode image now has the manufacturing key that will allow you to make changes in audit mode.

## Remove the manufacturing registry key

When you're finished making changes to your PC in audit mode, you'll remove the manufacturing registry key. 

While still booted into audit mode:

1. Open Command Prompt.

2. Remove the registry key.

    ```
    reg delete HKLM\system\ControlSet001\Control\CI\Policy /v ManufacturingMode
    ```

The manufacturing registry key is now removed. You can check the Registry Editor to double check that the key has been removed.

On your Windows 10 in S mode PC in audit mode:

1. Open Registry Editor by clicking on the start menu and typing `regedit` and press enter.

2. Use the registry browser in the left pane to navigate to Computer\HKEY\_LOCAL_MACHINE\SYSTEM\ControlSet001\Control\CI\Policy.

3. Under _policy,_ you should not see a key called _manufacturingmode_.

## Exclude the manufacturing registry key from recovery

When you create a recovery package, exclude the manufacturing registry key. Create an exclusion file that tells scanstate to skip the registry key when it captures a recovery package.

1. Create an .xml file in a text editor.

2. Copy and paste the following code. This tells ScanState to not capture the registry key in the recovery package that it creates:

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <migration urlid="http://www.microsoft.com/migration/1.0/migxmlext/ExcludeManufacturingMode">
    <component type="System">
        <displayName>Exclude manufacturing regkey</displayName>
            <role role="Settings">
                <rules context="System">
                    <unconditionalExclude>
                        <objectSet>
                            <pattern type="Registry">HKLM\SYSTEM\CurrentControlSet\Control\CI\Policy [ManufacturingMode]</pattern>
                        </objectSet>
                    </unconditionalExclude>
                </rules>
            </role>
    </component>
    </migration>
    ```

3. Save the file as exclusion.xml.

4. When you use scanstate to generate a recovery package, add /i:exclusion.xml to the scanstate command to exclude the manufacturing key from the capture. This command creates a recovery package that excludes the manufacturing registry key, and places it into the recovery folder.

    ```
    Scanstate.exe /config:T:\deploymenttools\Config_SettingsOnly.xml /o /v:13 /ppkg C:\Recovery\Customizations\usmt.ppkg /i:exclusion.xml /l:C:\Scanstate.log
    ```


