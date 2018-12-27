---
title: Support HTTP cache-control no-transform for MMS
description: For networks that require it, OEMs can add support for the HTTP header Cache-Control No-Transform directive for MMS messages.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 982c6948-8459-4de3-bb9e-9a49c0682c4d


ms.date: 05/02/2017
ms.topic: article


---

# Support HTTP cache-control no-transform for MMS


For networks that require it, OEMs can add support for the HTTP header Cache-Control No-Transform directive for MMS messages. When set, proxies and transcoders are instructed not to change the HTTP header and the content should not be modified (`Cache-Control: no-transform\r\n`).

When this directive is not set or the registry setting is missing, the HTTP header is set to Cache-Control No-Cache (`Cache-Control: no-cache\r\n`).

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-SIM** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="SetCacheControlNoTransform"  
                         Description="Use to add support for the HTTP header Cache-Control No-Transform directive for MMS messages."  
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
      </Static>

      <!-- Specify the Variant -->
      <Variant Name=""> 
        <TargetRefs>
          <TargetRef Id="" /> 
        </TargetRefs>

        <Settings Path="Messaging/PerSimSettings/$(__ICCID)">  
          <Setting Name="SetCacheControlNoTransform" Value="1" />        
        </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

4.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

5.  Do not modify the `SetCacheControlNoTransform``Value`. A value of 1 or 0x1 adds support for the HTTP header Cache-Control No-Transform directive.

    When the `SetCacheControlNoTransform``Value` is set to 0 or 0x0 or when the setting is not set, the default HTTP header Cache-Control No-Cache directive is used.

<a href="" id="testing-"></a>**Testing:**  
Flash the build containing this customization to a device with a UICC.

**Warning**  
To fully verify this customization, you will need to use a tool that captures HTTP traffic.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
