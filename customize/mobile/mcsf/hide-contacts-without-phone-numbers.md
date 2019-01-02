---
title: Hide contacts without phone numbers
description: Partners can change the default OS behavior so that both contacts with phone numbers and contacts without phone numbers are shown in the People Hub.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 68af9970-42a3-467c-9aec-dda028e28715


ms.date: 05/02/2017
ms.topic: article


---

# Hide contacts without phone numbers


Partners can change the default OS behavior so that both contacts with phone numbers and contacts without phone numbers are shown in the People Hub.

By default, contacts that do not have phone numbers are hidden in the People Hub.

<a href="" id="constraints---imagetimeonly"></a>**Constraints:** ImageTimeOnly  

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="HideContactsWithoutPhoneNumbers"  
                         Description="Use to show or hide in the People Hub the contacts without phone numbers."  
                         Owner=""  
                         OwnerType="OEM"> 
      <Static>  
        <Settings Path="People/ContactsFilteringSettings">  
          <Setting Name="HideContactsWithoutPhoneNumbers" Value="" />
        </Settings>  
      </Static>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Set `HideContactsWithoutPhoneNumbers` to one of the following values:

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
    <td><p>1 or 'True'</p></td>
    <td><p>In the People Hub, this hides contacts without phone numbers.</p>
    <p>This is the default OS behavior.</p></td>
    </tr>
    <tr class="even">
    <td><p>0 or 'False'</p></td>
    <td><p>In the People Hub, this shows contacts with phone numbers and contacts without phone numbers.</p></td>
    </tr>
    </tbody>
    </table>

     

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash a build containing this customization to a device.

2.  Set up the device and then add a few contacts. Make sure to include contacts with phone numbers and contacts without phone numbers.

3.  Open the People Hub.

    -   If you set `HideContactsWithoutPhoneNumbers` to 0 or 'False', verify that under the **Contacts** heading the filter shows **showing all** at the top of the contacts list. Confirm that all contacts, with and without phone numbers, are showing.

    -   If you set `HideContactsWithoutPhoneNumbers` to 1 or 'True' (or did not set this setting), verify that under the **Contacts** heading the filter shows **showing contacts with phone numbers** at the top of the contacts list. Confirm that only contacts with phone numbers are showing.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
