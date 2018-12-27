---
title: Data transfer indicator
description: OEMs can display a data transfer indicator on a device’s status bar for mobile operators that require it.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a677eb4a-458b-419e-8fd6-32d1f1b0b827


ms.date: 05/02/2017
ms.topic: article


---

# Data transfer indicator


OEMs can display a data transfer indicator on a device’s status bar for mobile operators that require it. When this feature is enabled, an arrow is displayed above the cellular data connection icon or Wi-Fi connection icon to indicate that data transfer is occurring.

The data transfer indicator, the cellular data connection icon, and the cellular signal strength icon are promoted on the status bar for 10 seconds and does not appear more frequently than once every 5 minutes. The data transfer indicator and the Wi-Fi connection icon are not promoted on the status bar.

However, users can tap the status bar to view the data transfer indicator above the bearer that’s transmitting data. The data transfer indicator, the cellular data connection icon, and the cellular signal strength icon are displayed for 10 seconds if cellular data transfer is occurring. The data transfer indicator and the Wi-Fi connection icon are displayed for 2 seconds if Wi-Fi data transfer is occurring.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="DataTransferIndicator"  
                         Description="Use to display a data transfer indicator on a device's status bar for operators that require it."  
                         Owner=""  
                         OwnerType="OEM"> 

      <Static>  
        <Settings Path="Shell/SystemTray/DataActivity">  
          <Setting Name="DataActivityIcon" Value="" />   
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set `DataActivityIcon` to one of the following values:

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
    <td><p>0 or 'Disabled'</p></td>
    <td><p>Hides the data transfer indicator in the status bar.</p>
    <p>This is the default behavior if the setting is not set.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Enabled'</p></td>
    <td><p>Shows the data transfer indicator in the status bar.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Flash an image that contains this customization to a device.

2.  Turn off Wi-Fi and send data over your cellular connection. For example, send an email with a photo attachment. Verify that the arrow that indicates data transfer appears above the cellular data connection icon on the status bar.

3.  Turn on Wi-Fi and send data over your Wi-Fi connection. Verify that the arrow that indicates data transfer appears above the Wi-Fi connection icon on the status bar.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
