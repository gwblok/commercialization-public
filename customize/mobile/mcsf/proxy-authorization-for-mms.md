---
title: Proxy authorization for MMS
description: Partners can specify the use of NAI information as a dedicated header for MMS authentication for mobile networks that require this functionality. The string value must be the MMS header used for authentication.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e52f6d8e-4d86-48e7-a708-976efdc26e77


ms.date: 05/02/2017
ms.topic: article


---

# Proxy authorization for MMS


Partners can specify the use of NAI information as a dedicated header for MMS authentication for mobile networks that require this functionality. The string value must be the MMS header used for authentication.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-SIM** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="ProxyAuthorizationMMS"  
                         Description="Use to set the NAI information as a dedicated header for MMS authentication."  
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
          <Setting Name="ProxyAuthorizationToken" Value="Proxy-Authorization:Basic" />     
        </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

4.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

5.  Do not change the `ProxyAuthorizationToken``Value`. `Proxy-Authorization` is the HTTP header and `Basic` denotes Basic64 encoding and not any other encoding.

<a href="" id="testing-steps-"></a>**Testing steps:**  
Work with your mobile operator to properly test this customization on their network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
