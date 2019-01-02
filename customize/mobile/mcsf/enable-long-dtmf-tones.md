---
title: Enable long DTMF tones
description: OEMs can enable long DTMF tones if the user presses a dialpad key for an extended period.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 14747b64-7ed2-41fd-ba0f-e9c76289fe65


ms.date: 05/02/2017
ms.topic: article


redirect_url: https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/dtmf-tones
---

# Enable long DTMF tones


OEMs can enable long DTMF tones if the user presses a dialpad key for an extended period.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="ContinuousDTMFEnabled"  
                         Description="Use to enable long DTMF tones if the user presses a dialpad key for an extended period."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Phone/PhoneSettings"> 
          <Setting Name="ContinuousDTMFEnabled" Value="" />
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set `ContinuousDTMFEnabled` to one of the following values:

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
    <td><p>0 or 'False'</p></td>
    <td><p>Fixed length (burst mode) DTMF tones are emitted.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'True'</p></td>
    <td><p>DTMF tones will persist as long as the user presses a corresponding dialpad key.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build that contains this customization to a phone.

2.  Test this customization on both VoLTE and non-VoLTE phone calls.

    -   If enabled, DTMF tones will last as long as the key is being pressed.

    -   If disabled, DTMF tones will be of fixed length.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
