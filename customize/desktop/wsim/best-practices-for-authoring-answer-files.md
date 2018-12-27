---
title: Best Practices for Authoring Answer Files
description: Best Practices for Authoring Answer Files
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 59761ac8-d6ff-4803-a4eb-d2668f846441
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Best Practices for Authoring Answer Files

We recommend the following best practices for creating answer files.

There are many ways in which you can use answer files. For more information about how to use an answer file with Windows Setup, see [Windows Setup Automation Overview](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/windows-setup-automation-overview). For more information about how to use an answer file with the **Sysprep** tool, [Using Answer Files with Sysprep](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/use-answer-files-with-sysprep). For more information about how to use an answer file with Deployment Image Servicing and Management (DISM), see [DISM Unattended Servicing Command-Line Options](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/dism-unattended-servicing-command-line-options).

## Always Validate Answer Files in Windows SIM

The recommended way to author answer files is to create them in Windows System Image Manager (Windows SIM). However, if you use a manually authored answer file, you must validate the answer file in Windows SIM to verify that the answer file works.

Because available settings and default values can sometimes change, you must revalidate your answer file when you reuse it.

## Avoid Unnecessary Settings

You can introduce unnecessary settings by inserting a setting's parent node into the answer file.

Windows SIM does not create an empty setting in an answer file. Although empty settings are ignored during Windows Setup, empty strings can extend installation time. Therefore, as you author your answer file, remove any settings that are not required.

In general, it is best to expand down to the lowest level of a component and select only those elements that you intend to set. For the default value, you do not have to include the element unless it is a required element.

## Understand Configuration Passes

Configuration passes represent different phases of installation. Understanding what happens during each configuration pass is very important to creating answer files. For more information, review [Windows Setup Automation Overview](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/windows-setup-automation-overview) and [How Configuration Passes Work](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/how-configuration-passes-work).

## Avoid Creating Empty Elements

Windows SIM supports creating empty elements in an answer file. By right-clicking a string setting type and then clicking **Write empty string**, you create an empty element in the answer file. However, some settings support empty elements, and some do not. In some cases, creating an empty element causes Windows Setup to fail. Before you create an empty element, see the component-setting documentation in the Windows® Unattended Setup Reference (Unattend.chm).

## <a href="" id="creating-architecture-specific-sections-for-each-configuration-pass-"></a>Creating Architecture-Specific Sections for Each Configuration Pass

If you perform cross-platform deployments, do not duplicate components for different architecture types in a single answer file. If you have multiple components that apply to different architecture types in a single answer file, the installation program may apply settings in the components more than once, or it may apply the settings incorrectly.

For cross-platform deployments, you must create architecture-specific settings for each configuration pass in an answer file. For example, for a 32-bit preinstallation environment and a 64-bit destination computer, you must specify only x86-based components in the **windowsPE** configuration pass and only x64-based components in all other configuration passes.

For 64-bit answer files, the wow64 settings are the 32-bit versions of an app, for those apps that include both 32-bit and 64-bit modes.

## Improve Security for Answer Files

Answer files store sensitive data, including product keys, passwords, and other account information. You can help protect this sensitive data by following these best practices:

* **Restrict access to answer files.** Depending on your environment, you can change the access control lists (**ACLs**) or permissions on a file. Only approved accounts can access answer files.
* **Hide passwords.** To improve security in answer files, you can hide the passwords for local accounts by using Windows SIM. For more information, see [Hide Sensitive Data in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/hide-sensitive-data-in-an-answer-file).
* **Delete the cached answer file.** During unattended Windows installation, answer files are cached to the computer. For each configuration pass, sensitive information such as domain passwords and product keys are deleted in the cached answer file. However, other information is still readable in the answer file. Before you deliver the computer to a customer, delete the cached answer file in **%WINDIR%\\panther**.

  > [!Note]
  > Delete the answer file only if no settings will be processed during the **oobeSystem** configuration pass. The **oobeSystem** configuration pass is processed immediately before Out-Of-Box Experience (OOBE) starts. This is typically the first time that a customer turns on the computer. If you delete the answer file from this folder, those settings will not be processed.

## Do Not Overwrite Existing Files When You Are Using Data Images or $OEM$ Folders

When you add data, such as additional drivers or applications, do not overwrite Windows system files. Overwriting system files can corrupt your computer. For information about how to add drivers and applications, see [How to Create a Data Image](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/create-a-data-image-using-dism) and [How to Manage Files and Folders in a Distribution Share](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/manage-files-and-folders-in-a-distribution-share).

## Use Separate Answer Files to Deploy to Multiple Architecture Types

Create separate answer files for each architecture type that you intend to deploy to. If a single answer file contains multiple components that apply to different architecture types, the component settings may be applied more than once or may be applied incorrectly.

## Use Multiple Answer Files for Specific Customizations

You can use multiple answer files (Unattend.xml) to create different sets of customizations that you can apply to your images at different times. For example, you can use a generic answer file that contains your branding and support information during Windows Setup. After installation finishes, when you run the **Sysprep** tool, you can apply a second answer file to add more customizations. When you must service your Windows image, you can use a different answer file with **DISM**.

For example, you can define your basic customizations in an answer file that you use with Windows Setup. After installation finishes, you can use an answer file with **Sysprep** or **DISM**. For example, if you want to keep all of the drivers that were added to the installation during a **generalize** process, you can create an answer file to use with **Sysprep** that contains the **PersistAllDeviceInstalls** setting. You can apply an answer file by running the following command: **Sysprep /generalize /unattend:**<em>answerfile</em>.

For more information about how to use an answer file with Windows Setup, see [Windows Setup Command-Line Options](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/windows-setup-command-line-options).

For more information about how to use an answer file with **Sysprep**, see [Sysprep Command-Line Syntax](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/sysprep-command-line-options).

For more information about how to use an answer file with DISM, see [DISM Unattended Servicing Command-Line Options](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/dism-unattended-servicing-command-line-options).

## Use the Correct Mechanisms to Add Updates to a Windows Image

Use only the Microsoft-supported servicing mechanisms to update a Windows image.

Use **DISM** to update an offline Windows image. For more information, see [Service an Offline Image](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/service-a-mounted-windows-image).

During installation, you can also configure the computer to automatically download updates from Windows Update.

> [!Warning]
> Never overwrite Windows system files by using `$OEM$` subfolders or data images.

If you have additional device drivers to add to a computer, add these drivers offline by using **DISM**. You can also include additional drivers in an unattended installation by using the **Microsoft-Windows-PnPCustomizationsNonWinPE** and **Microsoft-Windows-PnPCustomizationWinPE** components. For more information, see [How to Add and Remove Drivers Offline](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/add-and-remove-drivers-to-an-offline-windows-image).

## Specify Language Settings

To change languages by using an answer file, use the **Microsoft-Windows-International-Core-WinPE** component. There are two components in which you can specify language settings:

* **Microsoft-Windows-International-Core-WinPE**. Language settings are applied during the **windowsPE** configuration pass.
* **Microsoft-Windows-International-Core**. Language settings are applied during the **specialize** or **oobeSystem** configuration pass.

Because some languages require a restart, we recommend that you configure your language settings during the **windowsPE** configuration pass because the computer will always restart. If you process language settings during the **specialize** or **oobeSystem** configuration pass, the computer might require an additional restart.

## Use the Sysprep/generalize Command with LocalAccounts to Change Account Information

You can use the **Sysprep** command with the **generalize** option and the **LocalAccounts** settings to change account information about an existing user account.

If you specify the settings in the following example in the **specialize** configuration pass, all the values of *NEWVALUE* will be changed. However, *MyAccount* will retain its security group memberships. *MyAccount* is considered to be the same account with a different display name, description, and password value.

```xml
<LocalAccount>
   <Name>MyAccount</Name>
   <DisplayName>NEWVALUE</DisplayName>
   <Description>NEWVALUE</Description>
   <Password>
      <PlainText>false</PlainText>
      <Value>NEWVALUEBASE64</Value>
   </Password>
</LocalAccount>
```

## Related topics

[Windows System Image Manager (Windows SIM) Technical Reference](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/windows-system-image-manager-technical-reference)

[Sysprep Overview](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/sysprep--system-preparation--overview)

[Windows Setup Technical Reference](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/windows-setup-technical-reference)

[Deployment Image Servicing and Management (DISM)](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/dism---deployment-image-servicing-and-management-technical-reference-for-windows)
