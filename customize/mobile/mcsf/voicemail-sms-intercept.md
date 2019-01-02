---
title: Voicemail SMS intercept
description: Partners can define a filter that intercepts an incoming SMS message and triggers visual voicemail synchronization. The filtered message does not appear in the user’s conversation list.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 182c627c-ab07-481f-a970-7cd096813076


ms.date: 05/02/2017
ms.topic: article


---

# Voicemail SMS intercept


Partners can define a filter that intercepts an incoming SMS message and triggers visual voicemail synchronization. The filtered message does not appear in the user’s conversation list.

A visual voicemail sync is triggered by an incoming SMS message if the following conditions are met:

-   The message sender value starts with the string specified in the `SyncSender` setting. The length of the specified values must be greater than 3 characters but less than 75 characters.

-   The body of the message starts with the string specified in the `SyncPrefix` setting. The length of the specified values must be greater than 3 characters but less than 75 characters.

-   Visual voicemail is configured and enabled. For more information, see [Visual voicemail](visual-voicemail.md).

<a href="" id="constraints---atomic"></a>**Constraints:** Atomic  
This customization supports: **per-SIM** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="VoicemailSMSIntercept"  
                         Description="Use to define a filter that intercepts an incoming SMS message and triggers visual voicemail synchronization."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>

        <Settings Path="Messaging/GlobalSettings/VoicemailIntercept">  
          <Setting Name="SyncSender" Value="" />       
          <Setting Name="SyncPrefix" Value="" />       
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Specify a value for `SyncSender` that is greater than 3 characters but less than 75 characters in length.

    For networks that support it, this value can be a short code of the mailbox server that sends a standard SMS notification.

4.  Specify a value for `SyncPrefix` that is greater than 3 characters but less than 75 characters in length.

    For networks that support it, this value can be the keyword for the SMS notification.

**Note**  
The `SyncSender` and `SyncPrefix` values vary for each mobile operator, so OEMs must work with their mobile operators to obtain the correct or required values.

Make sure that the correct visual voicemail settings for the mobile operator are also set. For more information, see [Visual voicemail](visual-voicemail.md).

 

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build containing this customization to a phone that has a UICC.

2.  Successfully testing this customization requires the correct values, so work with your mobile operator partner to test this customization on their network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
