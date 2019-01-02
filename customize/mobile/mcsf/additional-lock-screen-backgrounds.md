---
title: Additional lock screen backgrounds
description: OEMs can add new lock screen background images for the lock screen and also set the default lock screen background.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 444d8e7f-2ac8-4dcd-893c-b4679a195093


ms.date: 05/02/2017
ms.topic: article


---

# Additional lock screen backgrounds


OEMs can add new lock screen background images for the lock screen and also set the default lock screen background.

**Limitations and restrictions**:

-   The lock screen backgrounds included by Microsoft shall not be removed, moved, or altered.

-   The user can modify the default lock screen background by selecting a new photo from the Photos application or by changing the lock screen background settings.

-   Lock screen background images must be in .JPG, .JPEG, or .PNG format.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  

<a href="" id="adding-more-lock-screen-backgrounds"></a>**Adding more lock screen backgrounds**  
OEMs can provide a set of images to complement the Backgrounds album. The set of images will be available to end-users to select as a lock screen background when the user selects the **Sample images** background provider in the **Lock screen** settings screen and launches the photo picker. The images will be appended to the end of the backgrounds album. Although there is no limit to the number of additional lock screen backgrounds, we recommend that partners add no more than 26 backgrounds.

To add a set of lock screen backgrounds:

1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="AdditionalLockScreenBackgrounds"  
                         Description="Use to add additional lock screen backgrounds and set the default lock screen background."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="LockScreen">  
          <Asset Name="Wallpapers" Source="" />
          <Asset Name="Wallpapers" Source="" />
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

    If you are setting the default lock screen background in addition to adding a set of lock screen backgrounds, see *Setting the default system lock screen background* after this section.

2.  Specify an `Owner`.

3.  Add additional lock screen backgrounds by adding more `Asset` elements.

    -   Set the asset's `Name` to `Wallpapers`.

    -   Set `Source` to the full path to the lock screen background source file on your development machine. For example: *C:\\Program Files (x86)\\Windows Kits\\10\\OEMCustomizationAssets\\AdditionalLockScreenBackgrounds\\Image1.jpg*.

<a href="" id="setting-the-default-system-lock-screen-background"></a>**Setting the default system lock screen background**  
OEMs can set an image to be the default system lock screen background and this supersedes the default device system lock screen background. This image will be shown during the following scenarios:

-   During first boot, unless device restore overrides the image with a backed up image.

-   When **Sample images** is selected as the **Background** in the **Lock screen** settings screen and no custom image is assigned.

-   During any error condition when the lock screen API fails to set the image and the system rolls back to the default system image.

The default lock screen image can be one of the images supplied as the default lock screen background set to be shown on the photo picker. We recommend that the default lock screen background image also be part of the set.

**To configure the default lock screen background:**

1.  Create a customization answer file using the contents shown in the following code sample or use the sample AdditionalLockScreenBackgrounds.xml file.

    ```
       <Settings Path="LockScreen">  
          <Setting Name="DefaultWallpaper" Value="" />  
       </Settings>  
    ```

2.  Specify an `Owner`.

3.  Set the `DefaultWallpaper` value to the file name of the image that you want to set as the default lock screen. For example, *Image1.jpg*.

4.  Use the customization answer file to create your custom OS image.

<a href="" id="testing-"></a>**Testing:**  
1.  Flash an OS image that contains this customization to a phone.

2.  If you added more lock screen backgrounds:

    1.  Go to **Lock screen** settings screen.

    2.  Make sure the **Background** setting is set to **Sample images**.

    3.  Select **Browse** and verify that your additional lock screen backgrounds have been appended at the end.

3.  If you set the default lock screen background:

    1.  Turn off the phone then turn it on again.

    2.  Verify that the lock screen background matches the image that you set as the default lock screen.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
