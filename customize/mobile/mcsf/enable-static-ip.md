---
title: Enable static IP
description: To facilitate Wi-Fi certification tests, OEMs can enable a screen from the Wi-Fi settings screen that provides UI elements that allow you to specify a static IP address, gateway address, and DNS server address.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 568786bc-4608-4fe0-b9e7-b1721073edc5


ms.date: 05/02/2017
ms.topic: article


---

# Enable static IP


To facilitate Wi-Fi certification tests, OEMs can enable a screen from the Wi-Fi settings screen that provides UI elements that allow you to specify a static IP address, gateway address, and DNS server address.

To enable the **Static IP** UI, set the value of the `EnableStaticIP` setting to 1. If the setting is not set, or is set to any value other than 1, the static IP UI is not enabled. When enabled, the Wi-Fi **Static IP** UI button appears directly below the **Advanced** button in the Wi-Fi settings screen.

**Warning**  
The static IP UI must only be used for certification purposes and not for production or retail devices.

 

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="EnableStaticIP"  
                         Description="Use to show the static IP settings in the advanced Wi-Fi settings screen.
                                      This customization is for testing purposes only and should not be set in 
                                      production or retail images."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="WiFi/Config">  
          <Setting Name="EnableStaticIP" Value="" />    
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value of `EnableStaticIP` to one of the following:

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
    <td><p>1</p></td>
    <td><p>Use to show the <strong>Static IP</strong> settings under <strong>Settings</strong> &gt; <strong>Wi-Fi</strong> &gt; <strong>Static IP</strong>.</p></td>
    </tr>
    <tr class="even">
    <td><p>0</p></td>
    <td><p>Use to disable the customization.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a device.

2.  Go to the **Settings** &gt; **Wi-Fi** screen and connect to a Wi-Fi network.

3.  From the Wi-Fi settings screen, verify that you can see the **Static IP** setting.

4.  Tap **Static IP** and configure your IP settings.

5.  Reboot the device.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
