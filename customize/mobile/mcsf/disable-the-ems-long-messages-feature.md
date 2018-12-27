---
title: Disable the EMS long messages feature
description: Partners can disable the enhanced messaging service (EMS), which concatenates text messages so that the user can enter more than 160 characters in a single message.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 73eeb587-2727-4eed-817d-147bb0089c0c


ms.date: 05/02/2017
ms.topic: article


---

# Disable the EMS long messages feature


Partners can disable the enhanced messaging service (EMS), which concatenates text messages so that the user can enter more than 160 characters in a single message. If EMS is disabled, the user can still enter more than 160 characters. However, the send button is disabled and the UI alerts the user that the text message is too long instead of showing the character count of the text entry.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-IMSI** value, **per-device** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="DisableEMSLongMessages"  
                         Description="Use to disable the enhnaced messaging service (EMS) long messages feature on Windows Phones. If EMS is disabled, 
                                      users can still enter more than 160 characters, but the send button is disabled and the user sees an alert 
                                      that the message is too long."  
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
          <!-- Set the value to 1 to limit the size of the message to one page and disable EMS. -->       
          <Setting Name="SmsPageLimit" Value="1" />             
        </Settings>  

      </Variant>

    -->

    <!-- Use for the per-device case

      <Static>  
        <Settings Path="CellCore/PerDevice/SMS">  
          <!-- Set the value to 1 to limit the size of the message to one page and disable EMS. -->       
          <Setting Name="SmsPageLimit" Value="1" />         
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

4.  Set `SmsPageLimit` to 1 to limit the size of the message to one page and disable EMS.

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device with a cellular connection.

2.  Open the messaging application and attempt to send a message with a length that exceeds 160 characters.

3.  Verify that the send button is disabled and that an alert that the text message is too long is showing next to the character count of the text entry.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
