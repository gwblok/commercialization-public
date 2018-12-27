---
title: Display location icon
description: Partners can hide the location icon in the system tray if they choose.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e14197b8-43b1-40c5-824d-b648e6bf0406


ms.date: 05/02/2017
ms.topic: article


---

# Display location icon


Partners can hide the location icon in the system tray if they choose.

By default, the location icon in the system tray is displayed whenever an app requests the user's location. Users may override the setting in the **Location** settings screen.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="LocationIcon"  
                         Description="Use to configure the display of the location icon in the system tray."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Shell/SystemTray/Location">  
          <Setting Name="LocationIcon" Value="" />    
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value of `LocationIcon` to one of the following:

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
    <td><p>1 or 'Enabled'</p></td>
    <td><p>Displays the location icon in the system tray. This is the default.</p></td>
    </tr>
    <tr class="even">
    <td><p>0 or 'Disabled'</p></td>
    <td><p>Hides the location icon in the system tray.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a device.

2.  Depending on the value you set for `LocationIcon`, verify if the location icon is displayed or is hidden in the system tray if an app that requests the user's location is launched.

3.  Go to the **Settings** &gt; **Location** screen. Change the value of the **Show icon** option and verify if the location icon is displayed or is hidden from the system tray based on the setting you chose.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
