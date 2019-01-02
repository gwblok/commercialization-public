---
title: Enable the data connection prompt
description: Partners can set the device to display a dialog that asks for permission to enable the data connection when the user connects the device to a host computer via a USB cable.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b72aa5ac-a192-46bb-bfa8-4abf9296a50d


ms.date: 05/02/2017
ms.topic: article


---

# Enable the data connection prompt


Partners can set the device to display a dialog that asks for permission to enable the data connection when the user connects the device to a host computer via a USB cable. Partners may need to enable this customization for certain markets.

By default, when the user connects the device to a host computer via a USB cable, the USB data connection is automatically enabled. This means that certain media files on the device, including pictures and music, are accessible through Windows Explorer on the host computer.

This setting is also available to users in the **USB** settings screen.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="USBDataConnection"  
                         Description="Use to display a dialog that asks for permission to enable the data connection when 
                                      the user connects the device to a host computer via a USB cable."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  
        <Settings Path="USBData">  
          <Setting Name="PromptForDataConnection" Value="" />   
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner` value in the customization answer file.

3.  Set the `Value` to one of the following:

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
    <td><p>0</p></td>
    <td><p>When the user connects the device to a host computer via a USB cable, do not display a dialog that asks for permission to enable the data connection. This is the default value.</p></td>
    </tr>
    <tr class="even">
    <td><p>1</p></td>
    <td><p>When the user connects the device to a host computer via a USB cable, display a dialog that asks for permission to enable the data connection.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Build an image that has this customization enabled, and flash this image to a device.

2.  Connect the device to a host computer using a USB cable.

3.  Confirm that the device displays a dialog that asks for permission to enable the data connection.

4.  Verify that the setting also appears in the **USB** settings screen.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
