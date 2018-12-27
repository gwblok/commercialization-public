---
title: LTE attach GUID for user configured internet APN
description: Partners can set the OEMConnectionId that is used when creating the user-configured connection for internet from the SIM settings screen.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 13bb20b7-d7e6-41be-b372-334886a21153


ms.date: 05/02/2017
ms.topic: article


---

# LTE attach: GUID for user configured internet APN


Partners can set the OEMConnectionId that is used when creating the user-configured connection for internet from the **SIM** settings screen.

The value is a GUID in the string format “XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX”. It is used as the value for the OEMConnectionId field of the connection and it identifies the modem profile used for the LTE Attach. If this value is not set, the APN configuration entered by the user does not affect the LTE Attach GUID used by the device.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-IMSI** value, **per-device** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?> 

    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="LTEAttachUserConfigGUID"  
                         Description="Use to set the OEMConnectionId used for the LTE attach profile in the modem."  
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

        <Settings Path="CellCore/PerIMSI/$(__IMSI)/CellUX">  
          <Setting Name="LTEAttachGUID" Value="" />      
        </Settings>  

      </Variant>

    -->

    <!-- Use for the per-device case

      <Static>  
        <Settings Path="CellCore/PerDevice/CellUX">  
          <Setting Name="LTEAttachGUID" Value="" />   
        </Settings>  
      </Static>

    -->

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Determine if you need to use the **per-IMSI** or **per-device** setting.

    For the **per-IMSI** case:

    1.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

    2.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

4.  Set the value for `LTEAttachGuid` to the OemConnectionId GUID used for the LTE attach profile in the modem. The value is a GUID in the string format “XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX”.

<a href="" id="testing-"></a>**Testing:**  
Refer to the documentation provided by the modem vendor and work with your mobile operator to test this customization on their network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
