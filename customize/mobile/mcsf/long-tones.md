---
title: Long tones
description: Partners can make a user option visible that makes it possible to toggle between short and long DTMF tones.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 788d595b-7a84-4d63-83dd-c82326f880be


ms.date: 05/02/2017
ms.topic: article


redirect_url: https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/dtmf-tones
---

# Long tones


Partners can make a user option visible that makes it possible to toggle between short and long DTMF tones.

By default, the device supports Dual-Tone Multi-frequency (DTMF) with continuous tones.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="ShowLongTones"  
                         Description="Use to make the user option for toggling between short and long tones visible to users."  
                         Owner=""  
                         OwnerType="OEM"> 

    <Static>

        <Settings Path="Phone/PhoneSettings">  
          <Setting Name="ShowLongTones" Value="" />      
        </Settings>  

    </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set `ShowLongTones` to one of the following values:

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
    <td><p>0 or False</p></td>
    <td><p>Hides the user option to make it possible for users to toggle between short and long tones.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or True</p></td>
    <td><p>Shows the user option.</p></td>
    </tr>
    </tbody>
    </table>



~~~
By default, the user option for toggling between short and long tones is hidden on GSM phones and visible for CDMA phones.
~~~

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
