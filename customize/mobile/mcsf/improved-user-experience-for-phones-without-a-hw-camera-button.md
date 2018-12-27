---
title: Improved user experience for phones without a HW camera button
description: On mobile devices that do not have a hardware camera button present, OEMs can provide a better user experience by enabling this customization so that parts of the UI and service are updated to indicate to the user that there is no camera button on the device. When this customization is enabled
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 45441077-2a0a-43b9-bb37-0925c85b784b


ms.date: 05/02/2017
ms.topic: article


---

# Improved user experience for phones without a HW camera button


On mobile devices that do not have a hardware camera button present, OEMs can provide a better user experience by enabling this customization so that parts of the UI and service are updated to indicate to the user that there is no camera button on the device. When this customization is enabled:

-   The camera roll text will not include the string **camera button**.

-   The **camera** settings screen will not include the string **camera button**.

-   The **camera** settings screen will not include settings that are button-specific.

When the user launches the camera app, the device displays a message on the viewfinder that shows the user how to take a picture by tapping on the screen.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="HWCameraShutterButtonNotPresent"  
                         Description="Use to provide a better user experience for phones that do not have a hardware camera button."  
                         Owner=""  
                         OwnerType="OEM"> 

      <Static>  

        <Settings Path="Photos/OEM">  
          <Setting Name="HWCameraShutterButtonNotPresent" Value="" />   
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner` value in the customization answer file.

3.  Set the value for `HWCameraShutterButtonNotPresent` to one of the following values:

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
    <td><p>0 or 'False, present'</p></td>
    <td><p>Indicates that there is a HW camera shutter button. This is the default value.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'True, not present'</p></td>
    <td><p>Indicates that there is no HW camera shutter button.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build that contains this customization to a mobile device without a dedicated hardware camera button.

2.  Navigate to the camera **Settings** screen and verify that **camera button** is not displayed in the UI.

3.  Verify that you do not see the following options in the UI:

    -   **Press and hold camera button**

4.  Navigate to the camera roll. If the camera roll is empty, verify that the caption displayed on the empty camera roll does not reference the camera button.

    If the default camera app is configured to work above the lock screen, verify that the app that launches is the OEM lens app that you chose.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
