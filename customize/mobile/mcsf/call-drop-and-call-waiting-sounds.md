---
title: Call drop and call waiting sounds
description: OEMs can customize the call drop and call waiting sounds.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 35849a27-a4eb-4e0a-82f9-00b100b29f60


ms.date: 05/02/2017
ms.topic: article


---

# Call drop and call waiting sounds


OEMs can customize the call drop and call waiting sounds.

On devices that exhibit a loud snap or tone during a phone call, OEMs can customize these sounds to add 50 ms of silence and improve the user experience. When used for this purpose, OEMs must:

-   Add a sound file that contains 50 ms of silence. The sound file must be in a .wma format.

-   Set the registry settings to the name of the sound file. This removes the loud snap or tone heard during some phone calls.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>

    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="CallDropCallWaitingSounds"  
                         Description="Use to customize the call drop and call waiting sounds."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="EventSounds">  
          <!-- Use to add the OEM sound file. Change the Source path to poitn to the location and file name of the .wma sound file. -->
          <Asset Name="NotificationSounds" Source="" />
          <Asset Name="NotificationSounds" Source="" />

          <!-- Use to set the default call drop sound. Set the value to the file name of the sound file. -->
          <Setting Name="DefaultCallDropSound" Value="" /> 

          <!-- Use to set the default call waiting sound. Set the value to the file name of the sound file. -->
          <Setting Name="DefaultCallWaitingSound" Value="" /> 
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Add additional notification sounds by adding a `NotificationSounds` asset. To do this:

    -   Set the asset's `Name` to `NotificationSounds`.

    -   Set `Source` to the full path to the call drop sound file on your development machine. For example: *C:\\Path\\CallDropSound.wma*.

    -   Repeat the previous steps for any additional ringtone sound, such as if you are using a different sound file for the call waiting sound.

4.  Set the value of `DefaultCallDropSound` to the desired default ringtone sound file name. For example: *CallDropSound.wma*.

5.  Set the value of `DefaultCallWaitingSound` to the desired default ringtone sound file name. For example: *CallWaitingSound.wma*.

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build that contains this customization to a device.

2.  Receive or make a phone call.

3.  Verify that a loud snap or tone is no longer heard.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
