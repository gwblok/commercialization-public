---
title: Disable voicemail phone number display
description: Disable voicemail phone number display on the call progress screen.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6427c974-8def-4d7f-92db-9329e2b213d6


ms.date: 05/02/2017
ms.topic: article


---

# Disable voicemail phone number display


Disable voicemail phone number display on the call progress screen.

By default, when a user calls the voicemail number, the number dialed is displayed below the **Voicemail** label on the call progress screen. If the user enters a phone number directly using the keypad, the actual number dialed (and displayed on the call progress screen) may differ from what the user entered and may potentially cause confusion. To address possible user confusion, partners can control whether the dialed voicemail phone number is displayed below the **Voicemail** label on the call progress screen.

<a href="" id="constraints---firstvariationonly"></a>**Constraints:** FirstVariationOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="DisableVoicemailPhoneNumberDisplay"  
                         Description="Use to either display or hide the voicemail phone number displayed in the call progress screen."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <Static>  
        <Settings Path="Phone/PhoneSettings">  
          <Setting Name="DisableVoicemailPhoneNumberDisplay" Value="" />
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set the `DisableVoicemailPhoneNumberDisplay` setting to one of the following values:

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
    <td><p>Shows the phone number below the <strong>Voicemail</strong> label on the call progress screen.</p>
    <p>This is the default OS behavior.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 'True'</p></td>
    <td><p>Hides the phone number below the <strong>Voicemail</strong> label on the call progress screen.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build containing this customization to a phone that has a UICC or SIM.

2.  Open the phone app.

3.  Call the voicemail either by pressing and holding "1" from the keypad screen, tapping the voicemail icon, or calling the voicemail number directly.

4.  Depending on the value that you set for `DisableVoicemailPhoneNumberDisplay`, verify that the voicemail phone number is either displayed or hidden below the **Voicemail** label on the call progress screen.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
