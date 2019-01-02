---
title: Maximum number of participants in a VoLTE conference call
description: OEMs can specify the maximum number of participants or callers that can be added to a voice over LTE (VoLTE) conference call based on the mobile operator's network requirements.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: dbd7de51-e340-430e-9f6a-84985ef2900b


ms.date: 05/02/2017
ms.topic: article


---

# Maximum number of participants in a VoLTE conference call


OEMs can specify the maximum number of participants or callers that can be added to a voice over LTE (VoLTE) conference call based on the mobile operator's network requirements.

By default, Windows 10 Mobile supports up to 6-way conference (host + 5 participants) for VoLTE conference calls.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="VoLTEMaxConferenceCallPartyCount"  
                         Description="Use to set the maximum number of participants in a voice over LTE conference call."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Phone/PhoneSettings">  
          <Setting Name="ConferenceCallMaximumPartyCount" Value="" />
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the value of `ConferenceCallMaximumPartyCount` the maximum number of participants, including the host, in a VoLTE conference call. Specify the number in decimal or hexadecimal (with the 0x prefix).

    The default OS value is 6.

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build containing this customization to a phone.

2.  Work with your mobile operator partner to test this customization on their network.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
