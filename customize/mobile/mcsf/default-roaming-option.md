---
title: Default roaming option
description: Partners can set the default value for the Default roaming options option in the Cellular SIM settings screen.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3d02bf12-08c1-4889-89c4-a76b0c60e7ef


ms.date: 05/02/2017
ms.topic: article


---

# Default roaming option


Partners can set the default value for the **Default roaming options** option in the **Cellular & SIM** settings screen.

Users can later change the default roaming option on the device.

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="DefaultRoamingOption"  
                         Description="Use to set the default roaming option."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Connections/General">  
          <Setting Name="DataRoam" Value="" />    
       </Settings>  

      </Static>
    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value of `DataRoam` to one of the following:

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Value</th>
    <th>Option</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>0 or 'DoNotRoam'</p></td>
    <td><p>Don’t roam</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'DomesticRoaming'</p></td>
    <td><p>Don’t roam (domestic roaming if applicable)</p></td>
    </tr>
    <tr class="odd">
    <td><p>2 or 'InternationalRoaming'</p></td>
    <td><p>Roam (international roaming if applicable)</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-"></a>**Testing:**  
1.  Flash the build containing this customization to a device.

2.  Go to the **Settings** &gt; **Cellular & SIM** screen.

3.  Verify that the **Default roaming options** shows the correct default value that you set.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
