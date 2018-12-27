---
title: Expiration time for SMS messages
description: Partners can set the expiration time before the device deletes the received parts of a long SMS message.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 502b888a-6545-4be6-af98-5b7939bbd790


ms.date: 05/02/2017
ms.topic: article


---

# Expiration time for SMS messages


Partners can set the expiration time before the device deletes the received parts of a long SMS message.

For example, if the device is waiting for a three-part SMS message and the first part has been received, the first part will be deleted when the time expires and the other part of the message has not arrived. If the second part of the message arrives before the time expires, the first and second parts of the message will be deleted if the last part does not arrive after the time expires. The expiration time is reset whenever the next part of the long message is received.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-IMSI** value, **per-device** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample or use the sample SMSExpirationTime.xml file.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="SMSExpirationTime"  
                         Description="Use to set the expiration time before the device deletes the received parts of a long SMS message."  
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
          <Setting Name="MessageExpirySeconds" Value="" />      
               <!-- Default is 0x15180 which is 1 day or 86400 seconds. -->
        </Settings>  

      </Variant>

    -->

    <!-- Use for the per-device case

      <Static>  
        <Settings Path="CellCore/PerDevice/SMS">  
          <Setting Name="MessageExpirySeconds" Value="" />      
               <!-- Default is 0x15180 which is 1 day or 86400 seconds. -->
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

4.  Set `MessageExpirySeconds` to the number seconds that the device should wait before deleting the received parts of a long SMS messages. This value should be in hexadecimal and must be prefixed with 0x.

    The default value is 0x15180, which is equivalent to 1 day or 86,400 seconds.

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device with a UICC.

2.  From another device, send a long SMS message to the device containing the customization.

3.  Verify that received parts of the long message are deleted within the expiration time that you have set if the next part is not received within that same amount of time.

    **Note**  
    Work with your mobile operator to fully test this customization.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
