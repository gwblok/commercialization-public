---
title: Hide the auto brightness setting
description: OEMs can hide the automatic brightness setting for phones that do not have an ambient light sensor.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 81255b22-afcd-43e8-bf0c-8af3926900ac


ms.date: 05/02/2017
ms.topic: article


---

# Hide the auto brightness setting


OEMs can hide the automatic brightness setting for phones that do not have an ambient light sensor.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="HideAutoBrightness"  
                         Description="Use to hide the auto brightness setting for phones without an ambient light sensor."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Brightness">  
          <Setting Name="HideAutoBrightness" Value="" />
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set `Value` to one of the following:

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
    <td><p>0 or 'Show'</p></td>
    <td><p>Use to show the <strong>Automatically adjust</strong> setting in the <strong>Settings</strong> &gt; <strong>brightness</strong> screen.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'Hide'</p></td>
    <td><p>Use to hide the <strong>Automatically adjust</strong> setting in the <strong>Settings</strong> &gt; <strong>brightness</strong> screen.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build that contains this customization to a phone.

2.  In **Settings**, go to the **Brightness** screen.

3.  Verify that the **Automatically adjust** toggle is hidden or visible depending on the `Value` that you set for `HideAutoBrightness`.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
