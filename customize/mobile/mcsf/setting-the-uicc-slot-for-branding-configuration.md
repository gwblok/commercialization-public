---
title: Setting the UICC slot for branding configuration
description: OEMs can specify which UICC slot will be used for branding configuration.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 59c4ba6c-e9c7-4982-bebd-3c001bfa733c


ms.date: 05/02/2017
ms.topic: article


---

# Setting the UICC slot for branding configuration


OEMs can specify which UICC slot will be used for branding configuration.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="SetBrandingSlot"  
                         Description="Use to specify which UICC slot to use for branding configuration."
                         Owner=""  
                         OwnerType="OEM"> 

       <Static>

          <Settings Path="Multivariant">  
             <Setting Name="BrandingSlot" Value="" /> 
          </Settings>  

       </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `BrandingSlot``Value` to use one of the following values depending on which UICC slot you want to use for branding configuration:

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
    <td><p>Slot 0</p></td>
    </tr>
    <tr class="even">
    <td><p>1</p></td>
    <td><p>Slot 1</p></td>
    </tr>
    </tbody>
    </table>

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
