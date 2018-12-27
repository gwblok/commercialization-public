---
title: Start + theme settings Enabling dark mode
description: OEMs can choose to specify whether the dark mode is applied.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 32D71592-3CAC-4912-ADFE-BD987B6AD9FD


ms.date: 05/02/2017
ms.topic: article


---

# Start + theme settings: Enabling dark mode


OEMs can choose to specify whether the dark mode is applied.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="DefaultBackgroundColor"  
                         Description="Specifies whether the dark mode is applied."
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Theme">  
          <Setting Name="DefaultBackgroundColor" Value="" /> 
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set `DefaultBackgroundColor` to specify a mode. The possible values are:

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
    <td><p>0 or 'Light'</p></td>
    <td><p>Enables light mode.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Dark'</p></td>
    <td><p>Enables dark mode. This is the default OS setting.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Flash an image containing this customization to a phone.

2.  Verify that the phone is using the correct mode.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
