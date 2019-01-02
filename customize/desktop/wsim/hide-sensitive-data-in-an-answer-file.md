---
title: Hide Sensitive Data in an Answer File
description: Hide Sensitive Data in an Answer File
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b71b5922-d6b8-4d64-9773-649e6ce44c60
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Hide Sensitive Data in an Answer File

You can use Windows® System Image Manager (Windows SIM) to hide the password for the administrator account, and for any other user accounts on the local system, in an answer file. Hiding passwords in an answer file prevents users from reading the answer file and identifying passwords for local accounts.

The settings that you can hide include the following:

* **Microsoft-Windows-Shell-Setup | AutoLogon | Password**
* **Microsoft-Windows-Shell-Setup | UserAccounts | AdministratorPassword**
* **Microsoft-Windows-Shell-Setup | UserAccounts | LocalAccounts | LocalAccount | Password**

This option only hides the passwords in an answer file. It does not provide encryption or other security benefits. Consider answer files as sensitive data and be careful about authorizing access to your answer files.

> [!Note]
> You can hide only local account passwords in an answer file. Domain passwords, product keys, and other sensitive data may still be available as clear text in an answer file.

To hide account passwords in an answer file:

1. Open Windows SIM.
1. Open a Windows image. For more information, see [Open a Windows Image or Catalog File](open-a-windows-image-or-catalog-file.md).
1. Create or open an answer file. For more information, see [Create or Open an Answer File](create-or-open-an-answer-file.md).
1. Add one of the following password settings to your answer file:
    * **Microsoft-Windows-Shell-Setup | AutoLogon | Password**
    * **Microsoft-Windows-Shell-Setup | UserAccounts | AdministratorPassword**
    * **Microsoft-Windows-Shell-Setup | UserAccounts | LocalAccounts | LocalAccount | Password**
1. Add a value to one or more of the password settings. The component is added to the answer file in the specified configuration pass.
1. On the **Tools** menu, click **Hide Sensitive Data**. This makes sure that when the answer file is saved, the password information will be hidden.
1. Save the answer file and close Windows SIM. The answer file will resemble the following example.

    ```xml
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
          <UserAccounts>
             <LocalAccounts>
                <LocalAccount wcm:action="add">
                   <Password>
                      <Value>UABhAHMAcwB3AG8AcgBkADEAMgAzADQANgBQAGEAcwBzAHcAbwByAGQA</Value>
                      <PlainText>false</PlainText>
                   </Password>
                   <Description>MyAccountName</Description>
                   <DisplayName>MyAccountName</DisplayName>
                   <Group>FabrikamGroup</Group>
                   <Name>MyAccountName</Name>
                </LocalAccount>
             </LocalAccounts>
          </UserAccounts>
       </component>
    ```

> [!Note]
> Windows SIM adds the **PlainText** element to the answer file. This element is used during Windows Setup to indicate whether or not the password is in plain text.

## Related topics

[Windows System Image Manager How-to Topics](windows-system-image-manager-how-to-topics.md)

[Create or Open an Answer File](create-or-open-an-answer-file.md)

[Configure Components and Settings in an Answer File](configure-components-and-settings-in-an-answer-file.md)

[Validate an Answer File](validate-an-answer-file.md)

[Add a Device Driver Path to an Answer File](add-a-device-driver-path-to-an-answer-file.md)

[Add a Package to an Answer File](add-a-package-to-an-answer-file.md)

[Add a Custom Command to an Answer File](add-a-custom-command-to-an-answer-file.md)

[Find a Component, Setting, or Package in Windows SIM](find-a-component-setting-or-package-in-windows-sim.md)
