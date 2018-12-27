---
title: Select multiple recipients for SMS and MMS messages
description: Partners can show the select all contacts/unselect all menu option to allow users to easily select multiple recipients for an SMS or MMS message.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: a0d93bcd-818f-4118-ac11-38efbba5b4a2


ms.date: 05/02/2017
ms.topic: article


---

# Select multiple recipients for SMS and MMS messages


Partners can show the **select all contacts**/**unselect all** menu option to allow users to easily select multiple recipients for an SMS or MMS message. This menu option provides users with an easier way to add multiple recipients and may also meet a mandatory requirement for some mobile operator networks.

Windows 10 Mobile supports the following select multiple recipients feature:

-   A multi-select chooser, which enables users to choose multiple contacts.

-   A **select all contacts**/**unselect all** menu option, which enables users to select or unselect all their contacts. This option is not shown by default and must be enabled by the OEM.

**Note**  
Note that this feature will only be enabled if the `LimitRecipients` setting is set to more than 1 recipient. For more information, see [Maximum number of recipients for SMS and MMS](maximum-number-of-recipients-for-sms-and-mms.md).



<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-SIM** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="SelectMultipleRecipients"  
                         Description="Use to enable users to easily select multiple recipients for SMS and MMS messages."  
                         Owner=""  
                         OwnerType="OEM"> 

      <!-- Define the Targets --> 
      <Targets>
         <Target Id="">
            <TargetState>
               <Condition Name="" Value="" />
               <Condition Name="" Value="" />
            </TargetState>
         </Target>
      </Targets>

      <Static>
        <Settings Path="Multivariant">
          <Setting Name="Enable" Value="1" />
        </Settings>
        <Settings Path="AutoDataConfig">
          <Setting Name="Enable" Value="0" />
        </Settings>
      </Static>

      <!-- Specify the Variant -->
      <Variant Name=""> 
        <TargetRefs>
          <TargetRef Id="" /> 
        </TargetRefs>

        <Settings Path="Messaging/PerSimSettings/$(__ICCID)">  
          <Setting Name="AllowSelectAllContacts" Value="" />    
        </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

4.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

5.  Set the value for `AllowSelectAllContacts` to one of the following:

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
    <td><p>0 or 0x0</p></td>
    <td><p>The <strong>select all contacts</strong>/<strong>unselect all</strong> menu option is not shown.</p></td>
    </tr>
    <tr class="even">
    <td><p>1 or 0x1</p></td>
    <td><p>The <strong>select all contacts</strong>/<strong>unselect all</strong> menu option appears in the app menu.</p></td>
    </tr>
    </tbody>
    </table>



~~~
If `AllowSelectAllContacts` is not set or missing, the **select all contacts**/**unselect all** menu option is not shown.
~~~

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build containing this customization to a device.

2.  Open the **Messaging** application and create a new SMS or MMS message.

3.  Select the **+** button to add message recipients.

4.  Verify that the multi-select icon appears in the **Choose a contact** screen. If you have more than one contact, this icon will be active. Otherwise, it will appear grey or inactive.

5.  Tap the multi-select icon then tap **…** for more menu options.

6.  Verify that you can see the **select all contacts** menu option.

7.  Tap **select all contacts**.

8.  Tap **…** and verify that you can see the **unselect all** menu option.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
