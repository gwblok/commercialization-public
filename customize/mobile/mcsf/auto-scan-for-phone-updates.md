---
title: Auto scan for phone updates
description: OEMs can show or hide the auto scan for updates setting on the device.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ffaddfb7-cacb-45bd-8ee0-94c8b2cd0904


ms.date: 05/02/2017
ms.topic: article


---

# Auto scan for phone updates


OEMs can show or hide the auto scan for updates setting on the device. When auto scan is visible, users can see a checkbox in the **Settings** &gt; **device update** screen to inform them when updates are available for their devices. When hidden, the device will always scan for updates and the user option is not visible.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="DisplayCheckForUpdates"  
                         Description="Use to show or hide the auto scan setting in the Settings > Phone Update screen."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="DeviceUpdate">  
          <!-- Use to determine whether to show or hide the auto scan settings for device updates. Set the value to 0 or 'Hidden', 
               or set to 1 or 'Visible'. -->
          <Setting Name="DisplayCheckForUpdates" Value="" />    
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value of `DisplayCheckForUpdates` to one of the following:

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
    <td><p>0 or 'Hidden'</p></td>
    <td><p>The device will always scan for updates and the <strong>Tell me when updates are available for my phone</strong> checkbox is not displayed.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Visible'</p></td>
    <td><p>The <strong>Tell me when updates are available for my phone</strong> checkbox is displayed in the <strong>Settings</strong> &gt; <strong>phone update</strong> screen.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a device.

2.  Go to the **Settings** &gt; **phone update** screen.

3.  Depending on the value you set for `DisplayCheckForUpdates`, verify whether the **Tell me when updates are available for my phone** checkbox is visible or hidden.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
