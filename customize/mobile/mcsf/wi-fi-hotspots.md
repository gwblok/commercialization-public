---
title: Connecting to open Wi-Fi hotspots in Windows 10
description: Partners can change the default settings for detecting Wi-Fi hotspots.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 0900eb56-c120-41e8-9193-240b1e7d1fae


ms.date: 05/02/2017
ms.topic: article


---

# Wi-Fi hotspots


Partners can change the default settings for detecting Wi-Fi hotspots.

Windows 10 automatically connects users to Wi-Fi so they can get online quickly in more places. It can connect them to open Wi-Fi hotspots that it knows about through crowdsourcing.
## How it works
Users choose the settings for automatically connecting to suggested open hotspots by going to Settings > Network & Internet > Wi-Fi on a Windows 10 PC or a phone with Windows 10 Mobile in Settings > Network & wireless > Wi-Fi > Additional settings. To use this feature, customers will need to be signed in with their Microsoft account on your Windows 10 PC or mobile device. (Note that this feature isn't available in all countries or regions.)

Windows 10 learns about open Wi-Fi hotspots a Windows PC or Windows phone connects to by collecting information about the network, like whether the open Wi-Fi network has a high-quality Internet connection. By using that information from your device and from other Windows customers' devices, we build a database of these high-quality networks. When you’re in range of one of these Wi-Fi hotspots, you automatically get connected to it.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="WiFiConnections"  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="WiFi/FirstBoot">  
          <Setting Name="AutoConnectAllowed" Value="" />    
          <Setting Name="DefaultAutoConnectState" Value="" />  
          <Setting Name="DefaultWiFiSharingState" Value="" />  
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value of `AutoConnectAllowed` to one of the following values:

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
    <td><p>Use to enable Wi-Fi detection. When enabled, users can opt-in to Wi-Fi detection.</p>
    <p>This is the default OS value.</p></td>
    </tr>
    <tr class="even">
    <td><p>0 or 'Disabled'</p></td>
    <td><p>Use to disable Wi-Fi detection.</p></td>
    </tr>
    </tbody>
    </table>

     

4.  Set the value of `DefaultAutoConnectState` to one of the following values:

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
    <td><p>Sets the checkbox for <strong>Automatically connect to Wi-Fi networks and accept terms for me</strong> during initial phone setup.</p>
    <p>This is the default OS value.</p></td>
    </tr>
    <tr class="even">
    <td><p>0 or 'Disabled'</p></td>
    <td><p>Clears the checkbox for <strong>Automatically connect to Wi-Fi networks and accept terms for me</strong> during initial phone setup.</p></td>
    </tr>
    </tbody>
    </table>

     

5.  Set the value of `DefaultWiFiSharingState` to one of the following values:

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
    <td><p>Sets the checkbox for <strong>Allow me to exchange Wi-Fi network access with my contacts</strong> during initial phone setup.</p>
    <p>This is the default OS value.</p></td>
    </tr>
    <tr class="even">
    <td><p>0 or 'Disabled'</p></td>
    <td><p>Clears the checkbox for <strong>Allow me to exchange Wi-Fi network access with my contacts</strong> during initial phone setup.</p></td>
    </tr>
    </tbody>
    </table>

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
