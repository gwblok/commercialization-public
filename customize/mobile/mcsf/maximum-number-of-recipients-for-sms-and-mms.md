---
title: Maximum number of recipients for SMS and MMS
description: Partners can set the maximum number of recipients to which a single SMS or MMS message can be sent.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: fbaa5d20-5129-4c36-8f17-eac3841db042


ms.date: 05/02/2017
ms.topic: article


---

# Maximum number of recipients for SMS and MMS


Partners can set the maximum number of recipients to which a single SMS or MMS message can be sent.

The maximum number of recipients that a user can send an SMS or MMS message to is limited to 500. This limit exists because the OS also supports the [Select multiple recipients for SMS and MMS messages](select-multiple-recipients-for-sms-and-mms-messages.md) feature and having the number of recipients for SMS or MMS messages limited to a large, but finite, number ensures that there is no system performance degradation or negative impact to the user experience. The maximum number of recipients that a user can send messages to is in the range 0 &lt;= 500 (decimal).

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-SIM** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="LimitMessagingMaxRecipients"  
                         Description="Use to set the maximum number of recipients for SMS or MMS messages."  
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
          <Setting Name="LimitRecipients" Value="" />    
        </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

4.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

5.  The `LimitRecipients` setting limits the maximum number of recipients that a user can send messages to, and this value is in the range 0 &lt; `LimitRecipients` &lt;= 500 (decimal). When setting the value for `LimitRecipients`, you can use either decimal or the equivalent hexadecimal value (with a 0x prefix).

    Set the value for `LimitRecipients` according to the following rules:

    -   If `LimitRecipients` is not set, the maximum number of recipients defaults to 500.

    -   If `LimitRecipients` is set to a value greater than 500, the maximum number of recipients is set to 500.

    -   If `LimitRecipients` is set to 1, the maximum number of recipients is set to 1 and the multi-select button in the single select screen is disabled

    -   If `LimitRecipients` is set to a value between 2 and 500, the maximum number of recipients is equal to the number that was set

<a href="" id="instructions-"></a>**Instructions:**  

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device with a UICC or network connection.

2.  Make sure your device contains more contacts than the number you set for `LimitRecipients`.

3.  Open the messaging application, create a new message, and tap **+** to add recipients.

4.  If [Select multiple recipients for SMS and MMS messages](select-multiple-recipients-for-sms-and-mms-messages.md) is not enabled, the behavior for `LimitRecpients` is the same as in Windows Phone 8.

5.  If [Select multiple recipients for SMS and MMS messages](select-multiple-recipients-for-sms-and-mms-messages.md) is enabled, tap the multi-select menu option, tap **…**, choose **select all contacts** and verify that you can see the following message:

    **Too many contacts**

    **You can select up to X contacts. If you select all, you will have Y contacts.**

    *X* is the decimal equivalent of the value that you set for `LimitRecipients`. *Y* is the total number of contacts you have selected.

6.  If [Select multiple recipients for SMS and MMS messages](select-multiple-recipients-for-sms-and-mms-messages.md) is enabled, tap the multi-select menu option, individually tap the names of your contacts and select one more than the number you set for `LimitRecipients`. Verify that you can see the following message:

    **Too many contacts**

    **You can select up to X contacts, and you already have that many**.

    *X* is the decimal equivalent of the value that you set for `LimitRecipients`.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
