---
title: Control Panel device icon
description: OEMs can change the default icon associated with the phone on a connected computer.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8a443574-47db-4ef3-b155-9f07fef289bf


ms.date: 05/02/2017
ms.topic: article


---

# Control Panel device icon


OEMs can change the default icon associated with the phone on a connected computer.

When the user connects a phone to a Windows computer, the phone name and icon shows up in the **Devices and Printers** list. OEMs can change the default icon associated with the phone.

**Limitations and restrictions:**

Create an icon to represent the phone that meets the following specifications:

-   **Filename:** Device.ico

-   **Dimensions, bit level and transparency:**

    256x256: 32bit + Alpha

    48x48: 32bit + Alpha

    48x48: 8bit 256

    48x48: 8bit 16

    32x32: 32bit + Alpha

    32x32: 8bit 256

    32x32: 4bit 16

    24x24: 32bit + Alpha

    24x24: 8bit 256

    24x24: 4bit 16

    16x16: 32bit + Alpha

    16x16: 8bit 256

    16x16: 4bit 16

-   Match the orientation and general creative style of the sample image. To avoid issues associated with the localization of the screen image text, the phone image must depict a phone that is turned off.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="ControlPanelDeviceIcon"  
                         Description="Use to change the icon associated with the phone when connecting to a Windows computer."
                         Owner=""  
                         OwnerType="OEM"> 

       <Static>

          <Settings Path="MediaTransferProtocol/DeviceAssets">  
             <!-- Use to add the icon to represent the phone when connected to a Windows computer. -->
             <Asset Name="DeviceIcon" Source="C:\Path\Device.ico" />
             
             <!-- Use to specify the file name of the device icon to use -->
             <Setting Name="Icon" Value="Device.ico" /> 
          </Settings>  

       </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Add the icon you want to use to represent the phone when connected to a Windows computer. To do this:

    1.  Set the asset `Name` to **DeviceIcon**.

    2.  Specify the file name and location of the asset on your workstation by setting the `Source`.

4.  Set the `Icon` value to the name of your custom icon. For example, *Device.ico*.

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a phone.

2.  On the Windows computer, open **Device Manager** and remove the driver associated with the phone.

3.  Connect the phone to the computer using a USB cable.

4.  On the computer, navigate to the **Devices and Printers** screen. Verify that the phone icon that you included in the build is visible.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
