---
title: Configure Quick actions
description: OEMs can change the default set of actions for each slot on the Quick actions screen in Notifications actions.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 005cb05d-947d-4317-ade9-85760577d034


ms.date: 05/02/2017
ms.topic: article


---

# Configure Quick actions


OEMs can change the default set of actions for each slot on the **Quick actions** screen in **Notifications & actions**.

The **Notifications & actions** settings screen contains a section at the top for users to configure **Quick actions**, which are actions that users can have available for quick access or without having to open the apps list or the settings screen to find them. Each quick action has a slot. If a user selects a quick action to go into an occupied slot (for example, Slot 1), and the chosen action already exists in another slot (for example, Slot 2), the two quick actions will swap so that the user-selected action always moves to the slot that the user has selected even though the action may already be in another slot.

> [!NOTE]
> In Windows 10 Mobile, the quick actions are not configurable through MCSF settings or Windows provisioning. OEMs must directly set the registry key to change the OS default quick actions.

 

Slots are ordered right-to-left so Slot 1 is always on the right and Slot 5 only appears in large screen devices.

The default pinned quick actions for 4-slot mobile devices are:

-   Slot 4: Wi-Fi
-   Slot 3: Bluetooth
-   Slot 2: Rotation lock
-   Slot 1: All settings

The default pinned quick actions for 5-slot mobile devices are:

-   Slot 5: Camera
-   Slot 4: Wi-Fi
-   Slot 3: Bluetooth
-   Slot 2: Rotation lock
-   Slot 1: All settings

OEMs can change the default quick action for each slot. If an OEM chooses not to configure all the slots available for the device, only the slot that was set will be changed and the other default Windows quick actions will remain set.

A slot cannot be empty. If an OEM sets the value for Slot 5, but the mobile device is not a large screen device, the OS ignores the value set for Slot 5. If an invalid value is used, the OS ignores the setting.

<a href="" id="instructions-"></a>**Instructions:**  
**To override the default pinned quick actions**

-   Set the `HKLM\Software\Microsoft\Shell\OEM\QuickActions\Slot` registry key and then set the value of the slot number that you want to configure to a friendly name value.

    The following table shows the friendly names that you can use as the value for the slot number that you want to configure.

    | FriendlyName                        | Description                  |
    |:------------------------------------|:-----------------------------|
    | Microsoft.QuickAction.AllSettings   | Pins All settings            |
    | Microsoft.QuickAction.Connect       | Pins the Connect app         |
    | Microsoft.QuickAction.Note          | Pins the Note app            |
    | Microsoft.QuickAction.Flashlight    | Pins the Flashlight app      |
    | Microsoft.QuickAction.RotationLock  | Pins Rotation lock           |
    | Microsoft.QuickAction.BatterySaver  | Pins Battery saver           |
    | Microsoft.QuickAction.Bluetooth     | Pins Bluetooth settings      |
    | Microsoft.QuickAction.WiFi          | Pins Wi-Fi settings          |
    | Microsoft.QuickAction.AirplaneMode  | Pins Airplane mode settings  |
    | Microsoft.QuickAction.Vpn           | Pins VPN settings            |
    | Microsoft.QuickAction.Cellular      | Pins Cellular settings       |
    | Microsoft.QuickAction.MobileHotspot | Pins Mobile hotspot settings |
    | Microsoft.QuickAction.Camera        | Pins the Camera app          |
    | Microsoft.QuickAction.Brightness    | Pins Brightness              |
    | Microsoft.QuickAction.QuietHours    | Pins Quiet hours             |
    | Microsoft.QuickAction.Location      | Pins Location settings       |

    For example, to change Slot 4 on 4-slot mobile devices from Wi-Fi to Airplane mode, set the value for `HKLM\Software\Microsoft\Shell\OEM\QuickActions\Slot\4` to Microsoft.QuickAction.AirplaneMode.

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build that contains this customization to a mobile device.

2.  Verify that the default quick action(s) that you set are showing up in the correct slot(s). For large screen devices, verify that there are 5 quick actions that are showing up instead of 4.

3.  Navigate to the **Quick actions** screen in **Notifications & actions** screen and verify that the default quick settings action(s) that you set are also showing up in the correct slots.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)
