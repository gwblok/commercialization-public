---
title: Always display the dialed phone number
description: OEMs can change the default behavior so that the number that's displayed in the call screen always matches the dialed phone number even if the number that the call connected to may be different.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e7cb2120-5bda-4db2-bd8f-816312f3d3a6


ms.date: 05/02/2017
ms.topic: article


---

# Always display the dialed phone number


By default, when a user dials a phone number and the call is connected, the number that shows up in the call screen is the phone number that the call is connected to. This connected phone number may not match the phone number that the user dialed.

OEMs can change the default behavior so that the number that's displayed in the call screen always matches the dialed phone number even if the number that the call connected to may be different.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="DisplayNumberAsDialed"  
                         Description="Use to display the outgoing phone number that was dialed rather than the number that the call was connected to. "  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  

        <Settings Path="Phone/PhoneSettings">  
          <Setting Name="DisplayNumberAsDialed" Value="" />
        </Settings>  

      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `DisplayNumberAsDialed` setting to one of the following values:

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
    <td><p>Display the connected phone number. This may not match the number that was dialed.</p>
    <p>This is the default OS behavior.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'True'</p></td>
    <td><p>Always display the phone number that was dialed even when the connected phone number is different.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
Work with your mobile operator partner to test this customization on their network.

1.  Flash the build containing this customization to a phone.

2.  Set up the phone and then call a valid phone number until the call is connected.

3.  If you set `DisplayNumberAsDialed` to 1 or 'True', try dialing your voicemail number or your subscriber number and verify that the number (as dialed) is displayed in the phone's call screen UI without the call translation to the voicemail number.

4.  If you set `DisplayNumberAsDialed` to 1 or 'True', try dialing one of the supplementary codes (which look like \#227 or \*227, for example) and verify that the number (as dialed) is displayed in the phone's call screen UI without the call translation to the phone number that these codes translate to.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
