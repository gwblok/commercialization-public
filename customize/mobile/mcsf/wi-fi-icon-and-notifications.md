---
title: Wi-Fi icon and notifications
description: Partners can configure settings related to the Wi-Fi icon.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 28f18979-6b85-4b2d-8c72-72e97ce49636


ms.date: 05/02/2017
ms.topic: article


---

# Wi-Fi icon and notifications


Partners can configure settings related to the Wi-Fi icon.

Settings that can be configured include:

-   Adjusting the percentages represented by the five bands in the status bar Wi-Fi icon.

-   Modifying the minimum connection strength for displaying a Wi-Fi network to the user. The default is 15%.

-   Specifying how frequently the **Wi-Fi** screen in **Settings** is updated.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="WiFiIconAndNotifications"  
                         Description="Use to configure settings related to Wi-Fi, including the percentages represented by the five bands in
                                      the status bar Wi-Fi icon and the minimum connection strength for displaying a Wi-Fi network to the user."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="WiFi/Config">  
          <Setting Name="ScanInterval" Value="" />    
          <Setting Name="SignalStrengthBar" Value="" />   
          <Setting Name="SignalStrengthDelta" Value="" />  
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the values for the following settings:

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td><p><strong>Setting name</strong></p></td>
    <td><p><strong>Description</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><code>ScanInterval</code></p></td>
    <td><p>Specifies how often the list of available networks is updated when the user is in the <strong>Wi-Fi</strong> screen in <strong>Settings</strong>.</p>
    <p>Set the value to the number of seconds multiplied by 1000. For example, the default is 6000 (or 6 seconds). To use a hexadecimal value, convert the decimal value to hexadecimal and add the 0x prefix.</p></td>
    </tr>
    <tr class="odd">
    <td><p><code>SignalStrengthBar</code></p></td>
    <td><p>Specifies the lowest acceptable signal strength for networks to be displayed in the <strong>Wi-Fi</strong> screen in <strong>Settings</strong>.</p>
    <p>Set the value is to a percentage from 0 to 100. The default value is 15%. If you are using a hexadecimal value, add the 0x prefix.</p></td>
    </tr>
    <tr class="even">
    <td><p><code>SignalStrengthDelta</code></p></td>
    <td><p>Specifies the difference in signal strength, as a percentage, between each bar in the Wi-Fi icon.</p>
    <p>Set the value to a number between 0 and 25. The default value is 15%. If you are using a hexadecimal value, add the 0x prefix.</p></td>
    </tr>
    </tbody>
    </table>

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
