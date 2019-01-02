---
title: Hide the weak charger notification option UI
description: Partners can configure the device to hide the dialog that is displayed when the user connects the device to an incompatible charging source and hide the USB setting that notifies the user when the device is connected to a slower charger.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 527b9e5a-c6b2-45b9-a5b8-9f9cb5e23bcf


ms.date: 05/02/2017
ms.topic: article


---

# Hide the weak charger notification option UI


Partners can configure the device to hide the dialog that is displayed when the user connects the device to an incompatible charging source and hide the USB setting that notifies the user when the device is connected to a slower charger.

When this customization is configured, if the device is connected to an incompatible charger, the option to show the **Phone charging slowly** dialog is hidden, and the **Notify me if my mobile device is charging slowly over USB** toggle is hidden.

By default, the OS shows the weak charger notification option UI.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="USBHideWeakChargerNotificationUI"  
                         Description="Use to hide the weak charger notification option UI."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="WeakCharger">  
          <Setting Name="HideWeakChargerNotifyOptionUI" Value="" /> 
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner` value in the customization answer file.

3.  Set the value for `HideWeakChargerNotifyOptionUI` to one of the following values:

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
    <td><p>Shows the weak charger notification option UI.</p>
    <p>This is the default OS behavior.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'True'</p></td>
    <td><p>Hides the weak charger notification option UI.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Build an image that has this customization configured, and flash this image to a device.

2.  Connect the device to an incompatible charging source.

3.  If the weak charger notification UI is suppressed, verify the following behavior:

    -   Confirm that the device does not display the dialog that states that a weak or unsupported USB charger is connected.

    -   Verify that the **Notify me if my mobile device is charging slowly over USB** setting is also hidden to a user in the **USB** settings screen.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
