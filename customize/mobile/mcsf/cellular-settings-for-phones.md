---
title: Hide Cellular & SIM Settings
description: OEMs can hide certain user options for phones that appear in the Cellular SIM screen in Settings.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 328fb6ed-50b6-4e73-8752-704fe7bcf587


ms.date: 05/02/2017
ms.topic: article


---
# Hide Cellular & SIM Settings

OEMs can hide certain user options for phones that appear in the **Cellular & SIM** screen in **Settings**.

These options include:

* For World mode: **Network Mode selection** drop-down
* For GSM: **Network Selection** drop-down
* For CDMA: **Network Type** drop-down

<a href="" id="constraints---none"></a>**Constraints:** None
This customization supports: **per-IMSI** value, **per-device** value

## Instructions

1. Create a customization answer file using the contents shown in the following code sample.

   ```XML
   <?xml version="1.0" encoding="utf-8" ?>
   <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"
                        Name="CellularSettings"
                        Description="Use to hide certain user options for phones that appear in the cellular+SIM settings screen."
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
        <Settings Path="CellCore/PerIMSI/$(__IMSI)/CellUX">
          <!-- Hides or shows the 'Network Mode selection' drop-down in the SIM settings screen for world mode phones.
               Set to 0 or 'No' (to show) or set to 1 or 'Yes' (to hide). -->
          <Setting Name="HideModeSelection" Value="" />

          <!-- Hides or shows the 'Network Selection' drop-down in the SIM settings screen for 3GPP or GSM phones. 
               Set to 0 or 'No' (to show) or set to 1 or 'Yes' (to hide). -->
          <Setting Name="Hide3GPPNetworks" Value="" />

          <!-- Hides or shows the 'Network Type' drop-down in the SIM settings screen for 3GPP2 or CDMA phones. 
               Set to 0 or 'No' (to show) or set to 1 or 'Yes' (to hide). -->
          <Setting Name="Hide3GPP2Selection" Value="" />
        </Settings>
      </Variant>

    <!-- Use for the per-device case -->
       <Static>  
          <Settings Path="CellCore/PerDevice/CellUX">
           <!-- Hides or shows the 'Network Mode selection' drop-down in the SIM settings screen for world mode phones.
               Set to 0 or 'No' (to show) or set to 1 or 'Yes' (to hide). -->
           <Setting Name="HideModeSelection" Value="" />
           <!-- Hides or shows the 'Network Selection' drop-down in the SIM settings screen for 3GPP or GSM phones. 
                Set to 0 or 'No' (to show) or set to 1 or 'Yes' (to hide). -->
           <Setting Name="Hide3GPPNetworks" Value="" />

           <!-- Hides or shows the 'Network Type' drop-down in the SIM settings screen for 3GPP2 or CDMA phones. 
                Set to 0 or 'No' (to show) or set to 1 or 'Yes' (to hide). -->
           <Setting Name="Hide3GPP2Selection" Value="" />
         </Settings>
       </Static>
   </ImageCustomizations>
   ```

1. Specify an `Owner`.
1. Determine if you need to use the **per-IMSI** or **per-device** setting.

   For the **per-IMSI** case:

   1. Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.
   1. Define settings for a **Variant**, which are applied if the associated target's conditions are met.

1. For World mode phones: Set the value for `HideModeSelection` to one of the following:

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
    <td><p>0 or 'No'</p></td>
    <td><p>Shows the <strong>Network Mode selection</strong> drop-down in the <strong>SIM</strong> settings screen.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Yes'</p></td>
    <td><p>Hides the <strong>Network Mode selection</strong> drop-down in the <strong>SIM</strong> settings screen.</p></td>
    </tr>
    </tbody>
    </table>

1. For 3GPP or GSM phones: Set the value for `Hide3GPPNetworks` to one of the following:

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
    <td><p>0 or 'No'</p></td>
    <td><p>Shows the <strong>Network Selection</strong> drop-down in the <strong>SIM</strong> settings screen.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Yes'</p></td>
    <td><p>Hides the <strong>Network Selection</strong> drop-down in the <strong>SIM</strong> settings screen.</p></td>
    </tr>
    </tbody>
    </table>

1. For 3GPP2 or CDMA phones: Set the value for `Hide3GPP2Selection` to one of the following:

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
    <td><p>0 or 'No'</p></td>
    <td><p>Shows the <strong>Network Type</strong> drop-down in the <strong>SIM</strong> settings screen.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Yes'</p></td>
    <td><p>Hides the <strong>Network Type</strong> drop-down in the <strong>SIM</strong> settings screen.</p></td>
    </tr>
    </tbody>
    </table>

## Testing

1. Flash the build containing this customization to a phone.
1. Go to the **Cellular & SIM** screen in **Settings**.
1. Verify that the user options are visible only if appropriate.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
