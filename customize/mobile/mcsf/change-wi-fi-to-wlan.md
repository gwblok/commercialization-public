---
title: Change Wi-Fi to WLAN
description: To meet regulatory requirements and/or meet mobile operator requirements for some markets, partners can replace the string Wi-Fi with the generic term WLAN.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 53ffbe79-fcd0-4548-9e16-320df5c6de2e


ms.date: 05/02/2017
ms.topic: article


---

# Change Wi-Fi to WLAN


To meet regulatory requirements and/or meet mobile operator requirements for some markets, partners can replace the string **Wi-Fi** with the generic term **WLAN**. Enabling this customization changes all **Wi-Fi** strings to **WLAN**.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="WiFiToWLAN"  
                         Description="Use To replace the 'Wi-Fi' strings in the phone UI to 'WLAN' to meet mobile operator or regulatory requirements."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="WiFi/FirstBoot">  
          <Setting Name="WiFiToWLAN" Value="" />    
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value of `WiFiToWLAN` to one of the following:

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
    <td><p>Use to enable or replace all &quot;Wi-Fi&quot; strings with &quot;WLAN&quot;.</p></td>
    </tr>
    <tr class="even">
    <td><p>0 or 'Disabled'</p></td>
    <td><p>Use to disable the customization. This is the default behavior.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a phone.

2.  Go to the **Settings** screen and verify that **WLAN** now shows up instead of **Wi-Fi**.

3.  Tap **WLAN**, and verify that “Wi-Fi” does not appear in the WLAN setting screen.

    All other “Wi-Fi” strings on the phone should now show “WLAN”.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
