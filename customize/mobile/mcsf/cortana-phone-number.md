---
title: Cortana phone number
description: Partners can configure a phone book entry for Cortana to allow users to initiate speech from a car that doesn't have support for activating speech on the device that is connected over Bluetooth.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 286e76cc-2099-421e-921b-3dbd925caf65


ms.date: 05/02/2017
ms.topic: article


---

# Cortana phone number


Partners can configure a phone book entry for Cortana to allow users to initiate speech from a car that doesn't have support for activating speech on the device that is connected over Bluetooth. The custom phone book entry will show up in the car's UI, but not in the Windows 10 Mobile UI.

When the user dials the custom phone number from the car, the device activates Cortana (or the device's default speech engine if Cortana is turned off or is not available), instead of making a phone call. The phone number also becomes associated with the contact name **Cortana** (or **Speech**) when the car downloads the phone book from the phone. To start the device's speech engine, the user can dial the custom contact from the car's UI or use the car's speech engine to "call Cortana" (or "call Speech" if Cortana is not enabled).

Once the phone book entry for Cortana has been configured, users cannot change the number. Only OEMs or mobile operators can change this number. Partners must set this phone number to a number that will not be used for actual phone numbers. Partners must also not use phone numbers that are used for emergencies, such as 911 in the United States.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="CortanaPhoneNumber"  
                         Description="Use to assign a phone number to associate with Cortana. Users can use this number to start a 
                                      conversation with Cortana on the phone if a car doesn't have support for activating speech on 
                                      the phone that is connected over Bluetooth."  
                         Owner=""  
                         OwnerType="OEM"> 

      <Static>  
        <Settings Path="Bluetooth/BTAGService">   
          <Setting Name="CortanaPhoneNumber" Value="" />  
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value for `CortanaPhoneNumber` to a phone number that will not be used for actual phone numbers or for those used for emergencies. The phone number should be specified for all countries/regions that support Cortana or legacy speech. If Cortana is off or not available for the market, the string **Speech** is used instead of **Cortana**.

    The default Cortana phone number is currently set to a fictitious phone number, 5555559876. If you do not change the default value, the OS will only recognize this phone number.

<a href="" id="testing-"></a>**Testing:**  
1.  Flash an image that contains this customization to a phone.

2.  Connect your phone to your car over Bluetooth.

3.  If Cortana or the default phone speech engine is supported, start the phone's speech engine by dialing the custom contact from the car's UI. Alternatively, you can use the car's speech engine and say "call Cortana" (or "call Speech) if Cortana is not enabled).

    Verify that the phone activates either Cortana or the default speech instead of making a phone call. If Cortana is available, start a conversation.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
