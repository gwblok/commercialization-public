---
title: Maximum length for SMS messages
description: Partners can specify a maximum length for SMS messages.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7a266e23-f514-4b25-9e9c-73fa7b97e1e5


ms.date: 05/02/2017
ms.topic: article


---

# Maximum length for SMS messages


Partners can specify a maximum length for SMS messages. This requires setting both the maximum number of SMS fragments per SMS message, from 1 to 255, and the maximum size in bytes of each SMS fragment, from 16 to 140 bytes.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-IMSI** value, **per-device** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="MaxLengthSMS"  
                         Description="Use to configure the maximum length for SMS messages."  
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
        <Settings Path="CellCore/PerIMSI/$(__IMSI)/SMS">  
          <Setting Name="SmsFragmentLimit" Value="" />  
          <Setting Name="SmsPageLimit" Value="" />
        </Settings>  
      </Variant>

    -->

    <!-- Use for the per-device case

      <Static>  
        <Settings Path="CellCore/PerDevice/SMS">  
          <Setting Name="SmsFragmentLimit" Value="" />  
          <Setting Name="SmsPageLimit" Value="" />
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

4.  Use `SmsFragmentLimit` to set the maximum number of bytes in the user data body of an SMS message. You must set the value between 16 (**0x10**) and 140 (**0x8C**).

5.  Use `SmsPageLimit` to set the maximum number of segments in a concatenated SMS message. You must set the value to 255 (**0xFF**) or smaller.

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device that contains a UICC or a configured CDMA connection.

2.  Open the messaging application and attempt to send a message with a length that exceeds the combination of `SmsFragmentLimit x SmsPageLimit`.

    You should receive an error message indicating that the message was too long.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
