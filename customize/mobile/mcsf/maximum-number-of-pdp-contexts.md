---
title: Maximum number of PDP contexts
description: OEMs can set different maximum values for the number of PDP contexts for the device if required by their mobile operator.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d27996d9-e96f-4de9-8cd8-0f35e352ec15


ms.date: 05/02/2017
ms.topic: article


---

# Maximum number of PDP contexts


OEMs can set different maximum values for the number of PDP contexts for the device for 3GPP network if required by their mobile operator.

By default, the OS enforces a maximum of four (4) simultaneous packet data protocol (PDP) contexts for 3GPP connections, and one (1) PDP context for 3GPP2 connections.

The same maximums apply for both roaming and non-roaming scenarios. This maximum does not include packet contexts used internally by the modem.

<a href="" id="constraints---none"></a>**Constraints:**
1. The setting `MaxNumberOfPDPContexts` is applicable for 3GPP networks only. It does not apply to 3GPP2 network.
2. This customization supports: **per-IMSI** value, **per-device** value.

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?> 

    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="MaxNumberOfPDPContexts"  
                         Description="Use to set the maximum number of concurrent packet contexts for the home carrier's 3GPP network"  
                         Owner=""  
                         OwnerType="OEM"> 

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

        <Settings Path="CellCore/PerIMSI/$(__IMSI)/CellData">  
          <Setting Name="MaxNumberOfPDPContexts" Value="" />      
        </Settings>  

      </Variant>

    -->

    <!-- Use for the per-device case

      <Static>  
        <Settings Path="CellCore/PerDevice/CellData">  
          <Setting Name="MaxNumberOfPDPContexts" Value="" />   
        </Settings>  
      </Static>

    -->


~~~
</ImageCustomizations>
```
~~~

2.  Specify an `Owner`.

3.  Determine if you need to use the **per-IMSI** or **per-device** setting.

    For the **per-IMSI** case:

    1.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

    2.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

4.  Set the value for `MaxNumberOfPDPContexts` as required by the mobile operator. You can specify a value between 1 through 4 (inclusive), or 0x1 through 0x4 (hexadecimal).

<a href="" id="testing-"></a>**Testing:**  
Work with your mobile operator partner to test this customization on their network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
