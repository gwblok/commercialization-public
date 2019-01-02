---
title: Custom shutdown screen
description: Partners can add a static logo or background during shutdown.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3d7a9467-7330-4896-9baf-5664d74f8875


ms.date: 05/02/2017
ms.topic: article


---

# Custom shutdown screen


Partners can add a static logo or background during shutdown. Shutdown screen images must be in .JPG, .JPEG, or .PNG format.

The resolution of the custom logo or background image provided by the partner should match the screen resolution of the device. If the image resolution is less than or greater than the screen resolution, the OS will scale the image to fit the screen.

**Limitations and restrictions:**

-   The **goodbye** text shall not be removed, altered, or replaced and the area behind the **goodbye** text must be dark enough for the text to remain legible.

-   Any logos or images used in the shutdown screen shall be owned or licensed by the OEM or mobile operator partner.

-   Partners shall not lengthen the amount of time the shutdown screen is displayed and thereby extend the amount of time it takes for the phone to shut down.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="CustomShutdownScreen"  
                         Description="Use to add a static logo during shutdown."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  
        
        <Settings Path="BootandShutdownScreens">  
          <Asset Name="ShutdownImage" Source="" />
          <Setting Name="WindowsPhoneShutdownScreenOverride" Value="" />  
        </Settings>  

      </Static>
    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `Source` of the `ShutdownImage` asset to the full path and name of the static logo or custom background you want to use when the phone shuts down. For example, *C:\\Program Files (x86)\\Windows Kits\\10\\CustomizationAssets\\CustomShutdownScreen\\CustomLogo.png*.

4.  Set the value of the `WindowsPhoneShutdownScreenOverride` setting to the file name of the custom screen or logo that you just added. For example, CustomLogo.png.

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a phone.

2.  Go through initial phone setup.

3.  Shut down the phone.

4.  Verify that you can see the **goodbye** text superimposed over your custom static logo or background.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
