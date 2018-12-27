---
title: Background cellular data restriction
description: To meet market or mobile operator requirements, OEMs can restrict background data in the data usage settings.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4d938b9f-f100-406b-be76-4259005d1b1a


ms.date: 05/02/2017
ms.topic: article


---

# Background cellular data restriction


To meet market or mobile operator requirements, OEMs can restrict background data in the data usage settings.

OEMs can set the default value to either never restrict usage of the data plan or restrict background data when roaming.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  

    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="DataSaverMode"  
                         Description="Use to restrict background data. OEMs can set the default value to either never restrict usage
                                      of the data plan or restrict background data when roaming."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="DataSense">  
          <Setting Name="DataSaverMode" Value="" />    
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value of `DataSaverMode` to one of the following:

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
    <td><p>0 or 'NeverRestrict'</p></td>
    <td><p>Never restrict usage of the data plan.</p></td>
    </tr>
    <tr class="even">
    <td><p>2 or 'RestrictWhenRoaming'</p></td>
    <td><p>Restrict background data when roaming.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build that contains this customization to a device.

2.  Go to the **Data usage** settings screen.

    Verify that the correct settings option is enabled depending on the default value that you set. A toggle to restrict background data also becomes available to the user.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
