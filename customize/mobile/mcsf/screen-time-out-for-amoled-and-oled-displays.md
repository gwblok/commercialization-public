---
title: Screen timeout for AMOLED and OLED displays
description: OEMs can remove the 15 minutes, 30 minutes, and Never options from the Screen times out after dropdown in the Lock screen settings screen. This is recommended for phones with AMOLED and OLED screens to prevent screen damage.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 27f5b4e2-6586-4893-a011-23e5f80df9b8


ms.date: 05/02/2017
ms.topic: article


---

# Screen timeout for AMOLED and OLED displays


OEMs can remove the **15 minutes**, **30 minutes**, and **Never** options from the **Screen times out after** dropdown in the **Lock screen** settings screen.

This is recommended for phones with AMOLED and OLED screens to prevent screen damage.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="ScreenTimeout"  
                         Description="Use to remove the 15 minutes, 30 minutes, and Never options from the screen time-out option in the Lock screen settings screen."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  
        <Settings Path="LockScreen">  
          <!-- Set the value to 1 or 0x1 to remove the 15 minutes, 30 minutes, and Never options from the lock screen settings screen -->
          <Setting Name="ScreenTimeOut" Value="" />  
        </Settings>  
      </Static>
    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  To hide or remove the **15 minutes**, **30 minutes**, and **Never** options from the **Screen times out after** dropdown in the **Lock screen** settings screen, set `ScreenTimeOut` to 1 or 0x1.

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a phone.

2.  Go to the **lock screen** screen in **Settings**.

3.  Tap the **Screen times out after** setting and verify that the **15 minutes**, **30 minutes**, and **never** options are no longer included in the list.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
