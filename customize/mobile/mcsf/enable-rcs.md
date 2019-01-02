---
title: Enable RCS
description: OEMs can configure the RCS settings using the multivariant support in the OS. Using these settings, you can Specify whether the device is RCS-enabled.Specify whether to use single registration for RCS.Configure the user experience for RCS.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 119C8C71-5D9F-41C9-BF07-3A099808776C


ms.date: 05/02/2017
ms.topic: article


---

# Enable RCS


OEMs can configure the RCS settings using the multivariant support in the OS. Using these settings, you can:

-   Specify whether the device is RCS-enabled.
-   Specify whether to use single registration for RCS.
-   Configure the user experience for RCS.

The following design principles for RCS settings apply in Windows 10 Mobile:

-   An OEM can set a policy that cannot be overwritten by the user.
-   A user can set the value for a setting unless the setting is hidden by the mobile operator or OEM, or if the setting is available only to the mobile operator or OEM.
-   The IMS and RCS services have a defined default behavior in the event that a policy or setting is not set.
-   Backup and restore are slot-based. Any per-slot SIM settings are backups for the associated slot. When the settings are restored, they are restored in the corresponding slot even if a different SIM is in that slot.
-   When there are no per-user or per-slot settings, then settings are applied per-SIM, not per-slot. For example, if the user sets group text ON for their Contoso SIM in Slot 1, and has group text OFF for their Fabrikam SIM in Slot 2, if the user swaps the Contoso SIM into Slot 2 and reboots the device, group text will be set to ON.

## RCS settings model


-   **Global policy** - The global policy reads from the Windows 10 Mobile registry location and if a value isn't found, the Windows Phone 8.1 registry location is used. If no value is found in the Windows Phone 8.1 location, the messaging app uses the default behavior of the app.

-   **Per-SIM policy** - The per-SIM policy is written to the Slot 1 or Slot 2 location based on the corresponding slot for the specific SIM.

    -   The per-SIM policy in Slot 1 reads from the Windows 10 Mobile registry location for Slot 1. If a value is not found, the messaging app falls back to the Windows Phone 8.1 location. If no value is found in Windows Phone 8.1 location, the messaging app uses the default behavior of the app.

    -   The per-SIM policy in Slot 2 reads from the Windows 10 Mobile registry location for Slot 2. If a value is not found, the messaging app uses the default app behavior.

-   **Per-SIM path policy** - The per-SIM path policy is written to the Slot 1 or Slot 2 location based on the corresponding slot for the specific SIM.

    -   The per-SIM policy in Slot 1 reads from the Windows 10 Mobile registry location for Slot 1. If a value is not found, the messaging app uses the default behavior of the app.

    -   The per-SIM policy in Slot 2 reads from the Windows 10 Mobile registry location for Slot 2. If a value is not found, the messaging app uses the default app behavior of the app.

-   **Per-provider SIM settings** - The per-provider SIM settings apply for single and dual SIM devices. The per-provider SIM settings are written to the Slot 1 or Slot 2 location based on the corresponding slot for the specific SIM. Each per-provider SIM setting (such as group text) has three separate values that determine its behavior in Windows 10 Mobile.

    The following table shows the expected behavior if all of the values are set in the Windows 10 Mobile location. This applies to both Slot 1 and Slot 2. In summary, if the setting is hidden from the user, any user setting value is ignored when the messaging app is determining which value to use.

    | OEM: Is it hidden? | User setting value | OEM default value | Final value |
    |--------------------|--------------------|-------------------|-------------|
    | No                 | N/A                | Off               | Off         |
    | No                 | On                 | Off               | On          |
    | Yes                | N/A                | Off               | Off         |
    | Yes                | On                 | Off               | Off         |

    Per-provider SIM Slot 2 settings will fall back to the default service behavior. The following table shows the expected behavior.

    <table border="1" rules="cols">
    <thead valign="bottom">
        <tr>
            <th colspan="3">Windows 10 Mobile OEM configuration</th>
            <th colspan="2">Windows 10 Mobile behavior</th>
            <th rowspan="2">Windows 10 Mobile final value</th>
        </tr>
        <tr>
            <th>OEM: Is it hidden?</th>
            <th>User setting value</th>
            <th>OEM default value</th>
            <th>OEM: Is it hidden?</th>
            <th>OEM and user default fallback behavior</th>
        </tr>
    </thead>
    <tbody valign="top">
        <tr>
            <td>N/A</td>
            <td>N/A</td>
            <td>N/A</td>
            <td>Yes</td>
            <td>On</td>
            <td>On</td>
        </tr>
        <tr>
            <td>No</td>
            <td>Off</td>
            <td>On</td>
            <td>Yes</td>
            <td>On</td>
            <td>Off</td>
        </tr>
        <tr>
            <td>Yes</td>
            <td>N/A</td>
            <td>Off</td>
            <td>Yes</td>
            <td>On</td>
            <td>Off</td>
        </tr>
        <tr>
            <td>No</td>
            <td>N/A</td>
            <td>Off</td>
            <td>Yes</td>
            <td>On</td>
            <td>Off</td>
        </tr>
    </tbody>
    </table>

     

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-SIM** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="EnableRCS"  
                         Description="Use to configure RCS settings."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <!-- Define the Targets --> 
      <Targets>
         <Target Id="">
            <TargetState>
               <Condition Name="" Value="" />
               <Condition Name="" Value="" />
            </TargetState>
         </Target>
      </Targets>
      
      <Static>
        <Settings Path="Multivariant">
          <Setting Name="Enable" Value="1" />
        </Settings>
        <Settings Path="AutoDataConfig">
          <Setting Name="Enable" Value="0" />
        </Settings>

        <!-- Configure these global settings to specify whether the device supports RCS. -->
        <Settings Path="CellCore/PerDevice/RCS">  
          <Setting Name="SystemEnabled" Value="" />
          <Setting Name="UserEnabled" Value="" />
        </Settings> 
      </Static>

      <!-- Specify the Variant -->
      <Variant Name=""> 
        <TargetRefs>
          <TargetRef Id="" /> 
        </TargetRefs>

        <!-- Use these settings to specify whether to use single registration for RCS. -->
        <Settings Path="CellCore/PerIMSI/$(__IMSI)/RCS">  
          <Setting Name="UseSingleRegistration" Value="" />
        </Settings> 

        <!-- Use these settings to configure the user experience for RCS -->
        <Settings Path="Messaging/PerSimSettings/$(__ICCID)/RcsOptions">  
          <Setting Name="ShowRcsEnabled" Value="" />
          <Setting Name="RcsEnabled" Value="" />
          <Setting Name="RcsSendReadReceipt" Value="" />
          <Setting Name="RcsFileTransferAutoAccept" Value="" />
        </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's Mobile Country Code (MCC), Mobile Network Code (MNC), and Service Provider Name (SPN).

4.  Define the settings for a **Variant**, which are applied if the associated target's conditions are met.

5.  To specify whether the system is RCS-enabled and the RCS package is installed, set `SystemEnabled` to one of the following values.

    | Value      | Description                                                                                                                                              |
    |:-----------|:---------------------------------------------------------------------------------------------------------------------------------------------------------|
    | 0 or 'No'  | The system is not RCS-enabled.                                                                                                                           |
    | 1 or 'Yes' | The system is RCS-enabled. If the system supports RCS, you can also specify whether to show the user setting by configuring the value for `UserEnabled`. |
     

6.  To show the user setting if RCS is enabled on the device, set `UserEnabled` to one of the following values.

    | Value      | Description                                                  |
    |:-----------|:-------------------------------------------------------------|
    | 0 or 'No'  | Don't show the user setting if RCS is enabled on the device. |
    | 1 or 'Yes' | Show the user setting if RCS is enabled on the device.       |

7.  To specify whether to use single registration for RCS, set `UseSingleRegistration` to one of the following values.

    | Value        | Description                                                                                                      |
    |:-------------|:-----------------------------------------------------------------------------------------------------------------|
    | 0 or 'False' | Do not use single registration for RCS.                                                                          |
    | 1 or 'True'  | Use single registration for RCS. The RCS stack will use the modem interface to communicate with the RCS backend. |

8.  To configure the user experience for RCS, set the following settings.

    -   To show or hide the toggle for RCS activation, set `ShowRcsEnabled` to one of the following values.

        | Value        | Description                                                                                                                                   |
        |:-------------|:----------------------------------------------------------------------------------------------------------------------------------------------|
        | 0 or 'False' | Hides the toggle for RCS activation. This is the default OS value.                                                                            |
        | 1 or 'True'  | Shows the toggle for RCS activation. If you use this value, you can also configure the default value for the service by setting `RcsEnabled`. |
    -   To set the default value for the RCS service toggle, set `RcsEnabled` to one of the following values.

        | Value        | Description                                                     |
        |:-------------|:----------------------------------------------------------------|
        | 0 or 'False' | RCS service toggle is set to Off. This is the default OS value. |
        | 1 or 'True'  | RCS service toggle is set to On.                                |
    -   To specify whether a read receipt is sent to the sender, set `RcsSendReadReceipt` to one of the following values.

        | Value        | Description                                                         |
        |:-------------|:--------------------------------------------------------------------|
        | 0 or 'False' | A read receipt is not sent to the sender.                           |
        | 1 or 'True'  | A read receipt is sent to the sender. This is the default OS value. |
    -   To specify whether to automatically download an incoming RCS file transfer when the file size is less than the limit for the warning file size, set `RcsFileTransferAutoAccept` to one of the following values.

        | Value        | Description                                                                             |
        |:-------------|:----------------------------------------------------------------------------------------|
        | 0 or 'False' | Do not automatically download the incoming RCS file transfer.                           |
        | 1 or 'True'  | Do automatically download the incoming RCS file transfer. This is the default OS value. |

         

<a href="" id="testing-"></a>**Testing:**  
Work with your mobile operator partner to test this customization on the operator's network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
