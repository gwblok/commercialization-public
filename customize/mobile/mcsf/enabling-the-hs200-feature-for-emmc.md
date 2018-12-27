---
title: Enabling the HS200 feature for eMMC
description: You can configure the device to enable the HS200 feature for eMMC parts.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 2acec4b1-954c-4b0c-bb26-ea66352ad19f


ms.date: 05/02/2017
ms.topic: article


---

# Enabling the HS200 feature for eMMC


You can configure the device to enable the HS200 feature for eMMC parts. This eMMC feature delivers a theoretical throughput of 200 MB/s across the eMMC bus, using a 200 MHz single data rate clock with an 8-bit bus width. This can result in significant performance improvements, especially on higher-end eMMC parts.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  

    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="HS200"  
                         Description="Use to enable the HS200 eMMC feature."  
                         Owner=""  
                         OwnerType="OEM"> 

      <Static>  
        <Settings Path="Storage/SdBus/MainOS">  
          <Setting Name="DisableHS200Support" Value="" />   
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
    <td><p>Enable the HS200 feature.</p></td>
    </tr>
    <tr class="even">
    <td><p>1</p></td>
    <td><p>Disable the HS200 feature. This is the default value.</p></td>
    </tr>
    </tbody>
    </table>

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
