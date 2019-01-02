---
title: Voice over LTE call indication
description: Partners can add a string to the phone's call progress screen to indicate if the active call is a voice over LTE (VoLTE) call depending on whether the phone call is in high quality voice status such as when using AMR-WB codec.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7a881c37-f07c-4d03-b5b6-3ac2f5b240e6


ms.date: 05/02/2017
ms.topic: article


---

# Voice over LTE call indication


Partners can add a string to the phone's call progress screen to indicate if the active call is a voice over LTE (VoLTE) call depending on whether the phone call is in high quality voice status such as when using AMR-WB codec. The high quality voice status is determined by the modem and RIL implementation. This string is combined with the PLMN for the mobile operator and is only shown if the combination of the PLMN and the custom string is less than the maximum width available. For example, "Litware VoLTE" will be shown but "Litware Wireless VoLTE" may be too long and may be truncated.

The OS uses the **PhoneMediaQuality** field in the **PH\_CALL\_INFO** structure to determine whether the phone call is in high quality voice status. In the current modem and RIL implementation, PhoneMediaQuality\_High is used to indicate high quality audio during VoLTE calls. **PhoneMediaQuality** must be equal to PhoneMediaQuality\_High and the `VoLTEAudioQualityString` must be set in order for the OS to display the string in the phone's call progress screen.

**Note**  
Depending on the current modem and RIL implementation, it is possible that the AMR-WB codec is being used and the phone call is in high quality voice status but not a VoLTE call. The OS does not restrict the use of this string in these cases.

 

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="VoLTEAudioQualityString"  
                         Description="Use to add a string to the call progress screen to indicate if the call is a voice over LTE call."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Phone/PhoneSettings">  
          <Setting Name="VoLTEAudioQualityString" Value="" />
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `Value` to the string that you want to display in the call progress screen to indicate that the call is a VoLTE call. This string is combined with the PLMN so if the string is 'VoLTE', the resulting string is '*PLMN\_String* VoLTE'. For example, the string displayed in the call progress screen can be 'Litware VoLTE' if the *PLMN\_String* is 'Litware'.

    The `Value` you specify for `VoLTEAudioQualityString` must exceed 10 characters.

    **Note**  
    This customization does not support a resource-only DLL for localized strings so you need to set the new string directly as the value.

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build containing this customization to a phone.

2.  Work with your mobile operator partner to test this customization on their network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
