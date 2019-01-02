---
title: Permanent automatic mode
description: OEMs can enable permanent automatic mode for mobile networks that require the cellular settings to revert to automatic network selection after the user has manually selected another network when roaming or out of range of the home network.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 284e1cb7-1140-4aba-ad17-43097dd322c2


ms.date: 05/02/2017
ms.topic: article


---
# Permanent automatic mode

OEMs can enable permanent automatic mode for mobile networks that require the cellular settings to revert to automatic network selection after the user has manually selected another network when roaming or out of range of the home network.

<a href="" id="constraints---none"></a>**Constraints:** None
This customization supports: **per-IMSI** value, **per-device** value

## Instructions

1. Create a customization answer file using the contents shown in the following code sample.

   ```XML
   <?xml version="1.0" encoding="utf-8" ?>
   <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"
                        Name="PermanentAutomaticMode"
                        Description="Use to enable permanent automatic mode."
                        Owner=""
                        OwnerType="OEM">
    <!-- Use for the per-IMSI case -->
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
     </Static>

     <!-- Specify the Variant -->
     <Variant Name="">
       <TargetRefs>
         <TargetRef Id="" />
       </TargetRefs>

       <Settings Path="CellCore/PerIMSI/$(__IMSI)/General">
         <Setting Name="AvoidStayingInManualSelection" Value="" />
       </Settings>
     </Variant>

    <!-- Use for the per-device case -->
     <Static>
       <Settings Path="CellCore/PerDevice/General">  
         <Setting Name="AvoidStayingInManualSelection" Value="" />
       </Settings>
     </Static>

   </ImageCustomizations>
   ```

1. Specify an `Owner`.
1. Determine if you need to use the **per-IMSI** or **per-device** setting.

   For the **per-IMSI** case:

   1. Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.
   1. Define settings for a **Variant**, which are applied if the associated target's conditions are met.

1. Set the `AvoidStayingInManualSelection``Value` to either of the following:

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Value</th>
    <th>Description</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>1</p></td>
    <td><p>Enable permanent automatic mode.</p></td>
    </tr>
    <tr class="even">
    <td><p>0</p></td>
    <td><p>Disable permanent automatic mode. The cellular settings for network selection remain in manual mode.</p></td>
    </tr>
    </tbody>
    </table>

## Testing

1. Flash the build containing this customization to a device that has a UICC.

   > [!Note]
   > To fully test this customization, work with your mobile operator partner. The device needs to be out of range of the home network so that the user can select **manual** mode under **Network selection** in the **Settings** &gt; **Cellular & SIM** screen.

1. When the device is no longer roaming or is in range of the home network, verify that the **Network selection** mode changed to **automatic** without requiring user action.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
