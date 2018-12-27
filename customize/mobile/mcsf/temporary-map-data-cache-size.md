---
title: Temporary map data cache size
description: When a user attempts to view map data for a location that was not preloaded or is not already installed on the phone, map data will be downloaded to dynamically render a map.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 275fcc7e-257f-4c88-9b52-37e924ab6f64


ms.date: 05/02/2017
ms.topic: article


---

# Temporary map data cache size


When a user attempts to view map data for a location that was not preloaded or is not already installed on the phone, map data will be downloaded to dynamically render a map. This data is stored in a temporary cache that the Maps application maintains for this purpose. By default this cache is allowed to use a maximum of 128 MB of storage. For phones with a limited amount of available storage, OEMs can specify that the cache only use a maximum of 64 MB of storage. Microsoft recommends that this customization only be used for phones with a limited amount of internal storage space. Reducing the size of the online cache for Map data does not affect the size of the installed (or offline) maps.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample or use the sample UseSmallerCache.xml file.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  

    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="UseSmallerCache"  
                         Description="Use to reduce the size of the online cache for Map data to a maximum of 64 MB of storage."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  
        <Settings Path="Maps/Storage">  
          <Setting Name="UseSmallerCache" Value="" />  
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set `UseSmallerCache` to one of the following values:

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
    <td><p>1 or Yes</p></td>
    <td><p>Reduces the size of the online cache for Map data to a maximum of 64 MB. This does not affect installed (offline) maps.</p></td>
    </tr>
    <tr class="even">
    <td><p>0 or No</p></td>
    <td><p>Reverts the size of the online cache for Map data to the default maximum of 128 MB.</p></td>
    </tr>
    </tbody>
    </table>

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
