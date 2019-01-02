---
title: Change SIM to SIM/UIM
description: Partners can change the string \ 0034;SIM \ 0034; to \ 0034;SIM/UIM \ 0034; in the device UI.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3d304e12-14ff-4c7b-a46c-9d7cdcd97223


ms.date: 05/02/2017
ms.topic: article


---

# Change SIM to SIM/UIM


Partners can change the string "SIM" to "SIM/UIM" in the device UI.

Enabling this customization changes all "SIM" strings to "SIM/UIM".

<a href="" id="constraints---none"></a>**Constraints:** None  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="SIMToSIMUIM"  
                         Description="Use to replace the 'SIM' strings in the device UI to 'SIM/UIM' to accommodate scenarios such as Dual Mode cards of 
                                      SIM cards on the device."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="CellCore/PerDevice/UIX">  
          <!-- Set the value to 0 or "SIM" (to use the default SIM string), or set to 1 or "UIM" (to use the alternate SIM/UIM string) -->
          <Setting Name="SIMToSIMUIM" Value="" />    
       </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value of `SIMToSIMUIM` to one of the following:

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
    <td><p>0 or 'SIM'</p></td>
    <td><p>Uses the default string &quot;SIM&quot;.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'UIM'</p></td>
    <td><p>Uses the alternate string &quot;SIM/UIM&quot;.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a device without a SIM.

2.  During the initial device setup, verify that you see the following error:

    **SIM/UIM error**

    **The SIM/UIM card is missing or invalid. You can still make emergency calls if your mobile operator supports it.**

3.  In the Start screen, verify that the phone tile shows **No SIM/UIM**.

    All other "SIM" strings on the device should now show "SIM/UIM".

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
