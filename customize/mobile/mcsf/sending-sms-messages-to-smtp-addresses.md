---
title: Send SMS messages to SMTP addresses
description: Partners can configure SMS messages to be sent to email addresses as well as phone numbers.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4cbc6176-16cd-41b4-93f7-2e270509c399


ms.date: 05/02/2017
ms.topic: article


---

# Send SMS messages to SMTP addresses


Partners can configure SMS messages to be sent to email addresses as well as phone numbers.

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-SIM** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="SMStoSMTPShortCode"  
                         Description="Use to configure SMS messages to be sent to email addresses and phone numbers."  
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
          <Setting Name="AllowSMStoSMTPAddress" Value="" />    
          <Setting Name="SMStoSMTPShortCode" Value="" />    
        </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

4.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

5.  Set the value for `AllowSMStoSMTPAddress` to one of the following values:

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
    <td><p>0 or 'False'</p></td>
    <td><p>Disables sending SMS messages to SMTP addresses.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'True'</p></td>
    <td><p>Enables sending SMS messages to SMTP addresses.</p></td>
    </tr>
    </tbody>
    </table>

     

6.  Set the `SMStoSMTPShortCode` value to the correct short code for your mobile operator. This value is the destination SMTP gateway phone number, and must be provided by the mobile operator.

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device that contains a SIM or network connection for your mobile operator.

2.  Open the messaging app and attempt to send a message to a valid email address.

3.  The message should send and arrive successfully.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
