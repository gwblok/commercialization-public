---
title: User agent string for MMS messages
description: Partners can replace the entire user agent string for MMS.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c1bb6108-3db1-4aac-802a-143bc02b8acf


ms.date: 05/02/2017
ms.topic: article


---

# User agent string for MMS messages


Partners can replace the entire user agent string for MMS.

By default, this string has the format WindowsPhoneMMS/*MicrosoftMMSVersionNumber* WindowsPhoneOS/*OSVersion*-*buildNumber* *OEM*-*deviceName*, in which the *italicized text* is replaced with the appropriate values for the phone.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-SIM** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="MMSUAString"  
                         Description="Use to replace the entire user agent string for MMS messages."  
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
          <Setting Name="UserAgentString" Value="" />     
        </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

4.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

5.  Set the `UserAgentString``Value` to the new user agent string for MMS in its entirely.

    By default, this string has the format WindowsPhoneMMS/*MicrosoftMMSVersionNumber* WindowsPhoneOS/*OSVersion*-*buildNumber* *OEM*-*deviceName*, in which the *italicized text* is replaced with the appropriate values for the device.

<a href="" id="testing-"></a>**Testing:**  
Work with your mobile operator to test this customization on their network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
