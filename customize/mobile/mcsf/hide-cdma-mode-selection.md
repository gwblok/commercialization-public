---
title: Hide CDMA mode selection
description: For CDMA phones, partners can hide CDMA option in the network Mode selection drop-down that appears on the Cellular SIM screen in Settings.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8ad8dc3d-1983-45ab-9f16-c82132677bf2


ms.date: 05/02/2017
ms.topic: article


---

# Hide CDMA mode selection


For CDMA phones, partners can hide **CDMA** option in the network **Mode** selection drop-down that appears on the **Cellular & SIM** screen in **Settings**.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-IMSI** value, **per-device** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="HideCDMAModeSelection"  
                         Description="Use to hide or show the 'CDMA' option in the network 'Mode' selection drop-down that appears in the cellular settings screen."  
                         Owner=""  
                         OwnerType="OEM"> 


~~~
<!-- Use for the per-IMSI case 

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
      <!-- Hides or shows the 'CDMA' option in the network mode selection screen. Set to 0 or 'No' (to show) or set to 1 or 'Yes' (to hide). -->
      <Setting Name="Hide3GPP2ModeSelection" Value="" />    
    </Settings>  
  </Variant>

-->

<!-- Use for the per-device case

  <Static>  
     <Settings Path="CellCore/PerDevice/CellUX">  
      <!-- Hides or shows the 'CDMA' option in the network mode selection screen. Set to 0 or 'No' (to show) or set to 1 or 'Yes' (to hide). -->
      <Setting Name="Hide3GPP2ModeSelection" Value="" />   
    </Settings>  
  </Static>

-->

</ImageCustomizations>
```
~~~

2.  Specify an `Owner`.

3.  Determine if you need to use the **per-IMSI** or **per-device** setting.

    For the **per-IMSI** case:

    1.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

    2.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

4.  Set the value for `Hide3GPP2ModeSelection` to one of the following:

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
    <td><p>Shows the <strong>CDMA</strong> option in the network <strong>Mode</strong> selection drop-down.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Yes'</p></td>
    <td><p>Hides the <strong>CDMA</strong> option in the network <strong>Mode</strong> selection drop-down.</p></td>
    </tr>
    </tbody>
    </table>



~~~
The default for this setting is to show the **CDMA** option in the **Mode** selection drop-down that appears in the **Cellular & SIM** settings screen.
~~~

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device.

2.  Go to the **Cellular & SIM** screen in **Settings**.

3.  Depending on the value that you set, verify whether the **CDMA** option in the network **Mode** selection drop-down is visible.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
