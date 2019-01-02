---
title: LTE attach Mapping OEMConnectionId values to modem profiles
description: Partners can set the list of OEMConnectionId values that map to a LTE attach profile in the MBB driver.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: cd65fb93-fb90-48cd-9337-7ba7e6c03c37


ms.date: 05/02/2017
ms.topic: article


---

# LTE attach: Mapping OEMConnectionId values to modem profiles


Partners can set the list of OEMConnectionId values that map to a LTE attach profile in the MBB driver. This list is used to specify which OEMConnectionIds require a detach/attach in order for changes to apply. If an OEMConnectionId is not included in this list and the LTE attach info is updated, it will not take effect until the device is rebooted.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  
This customization supports: **per-device** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="LTEAttachProfileMap"  
                         Description="Use to set the list of OEMConnectionId values that map to a LTE attach profile on the MBB driver side."  
                         Owner=""  
                         OwnerType="OEM">

      <Static>  

        <Settings Path="CellCore/PerDevice/CellData/ModemProfiles">        
          <Setting Name="LTEAttachGuids" Value="" />    
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value of `LTEAttachGuids` to the semicolon-separated list of OEMConnectionId values that map to a LTE attach profile on the MBB driver. OEMConnectionIds are GUIDs in the string format “XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX”.

<a href="" id="testing-"></a>**Testing:**  
Refer to the documentation provided by the modem vendor and work with your mobile operator to test this customization on their network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
