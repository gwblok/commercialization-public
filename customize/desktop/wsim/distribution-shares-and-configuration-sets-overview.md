---
title: Distribution Shares and Configuration Sets Overview
description: Distribution Shares and Configuration Sets Overview
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9281b886-bc80-4f77-96b9-6ff87e1ba60d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Distribution Shares and Configuration Sets Overview

A distribution share is an optional set of folders that contain custom scripts, images, branding, applications, drivers, and other files. These files can be copied to Windows® during installation through an answer file (Unattend.xml).

During installation, Windows connects to the path of the server share by using the credentials that you specify in an answer file. Only the files that you specify in the answer file are copied to the Windows installation.

If you are installing Windows in an environment that does not have a network share or server share, you can copy the necessary files from the distribution share to a configuration set. A configuration set is a subset of the files in a distribution share. You can copy a configuration set to external storage, such as a USB flash drive or an external hard disk, to use during installation.

## Folders in a Distribution Share

When you create a distribution share by using Windows System Image Manager (Windows SIM), three folders are created automatically. The folders are named `$OEM$`, `Out-of-Box Drivers`, and `Packages`. If you create your own distribution share, it must contain at least one of these folders for Windows SIM to recognize it as a valid distribution share.

### <a href="" id="-oem--folders"></a>**$OEM$ Folders**

You can use the `$OEM$` folder and subfolders only when you are creating configuration sets. You can use `$OEM$` to include logos for branding and to add applications and other files that customize the unattended installation.

As a general rule, to add new files and resources to Windows, use a data image. For more information, see [How to Create a Data Image](http://go.microsoft.com/fwlink/?LinkId=224962).

For more information about how to use `$OEM$` folders, see [How to Manage Files and Folders in a Distribution Share](http://go.microsoft.com/fwlink/?LinkId=224963).

> [!Important]
> Do not overwrite existing files that are carried and serviced by the operating system. Using the `$OEM$` folder to update or overwrite these files can cause the operating system to behave unpredictably and cause serious issues.

The following table describes the `$OEM$` folder and its subfolders.

|Folder                   | Definition | 
|-------------------------|------------|
`$OEM$`                   | Contains supplemental folders and files for an automated or customized installation.|
|`$OEM$\$$`               | Contains files that Windows Setup copies to the `%WINDIR%` folder (for example, `C:\Windows`) during installation.| 
| `$OEM$\$$\System32`     | Contains files that Windows Setup copies to the `%WINDIR%\System32` folder during installation. | 
| `$OEM$\$1`              | Represents the root of the drive on which you installed Windows (also called the boot partition), and contains files that Windows Setup copies to the boot partition during installation. | 
| `$OEM$\$1\`_subfolder_  | Represents subfolders of the root drive. Example: `$OEM$\$1\MyDriver`. | 
| `$OEM$\`_driveletter\subfolder_ | Represents other drive letters and subfolders. Multiple instances of this type of folder can exist under the `$OEM$\`_driveletter_ folder. Example: `$OEM$\D\MyFolder` . | 

### Out-of-Box Drivers

Drivers are a type of software that enables hardware or devices to function.

The **Out-of-Box Drivers** folder includes additional device drivers that you install during Windows Setup by using Windows SIM. Windows Setup uses the following types of drivers:

* **In-box drivers**. Windows Setup handles in-box drivers the same way that it handles packages.
* **Out-of-box drivers**. By using Windows SIM, you can add out-of-box device drivers that are based on .inf files. Typically, these out-of-box drivers are processed during the **auditSystem** configuration pass. Your .inf-based out-of-box drivers must be in a distribution-share subfolder that is called Out-of-Box Drivers. For more information, see [How to Manage Files and Folders in a Distribution Share](http://go.microsoft.com/fwlink/?LinkId=224963).
* **In-box drivers that are installed via a .msi file.** In-box drivers that require a .msi file are added the same way that applications are added.
  > [!Note]
  > By using the **Microsoft-Windows-PnpCustomizationsWinPE** component, you must add boot-critical device drivers that are required for installation during the **windowsPE** configuration pass. For more information, see [How to Add Device Drivers by Using Windows Setup](http://go.microsoft.com/fwlink/?LinkId=224975). You can also add device drivers to an offline image by using Deployment Image Servicing and Management (**DISM**). For more information, see [How to Add and Remove Drivers Offline](http://go.microsoft.com/fwlink/?LinkId=224967).

### Packages

The **Packages** folder is a location for Windows software updates. Package types include service packs, security updates, language packs, and other packages that Microsoft issues. You must use Windows SIM to import packages to a distribution share. After a package is imported and available in the **Distribution Share** pane, you can add the package to the answer file. For more information, see [How to Add Packages to a Distribution Share](http://go.microsoft.com/fwlink/?LinkId=225111).

## Configuration Sets

After an answer file (**Unattend.xml**) has been validated and saved, you can create a configuration set. A configuration set is a subset of a distribution share that you can create by using Windows SIM. Configuration sets are useful when a network share is not available. You can store configuration sets on removable media and use them in the field. Creating a configuration set exports binaries that are referenced in the answer file and puts them together in a self-contained file set that can be accessed from the Unattend.xml file.

### Contents of a Configuration Set

A configuration set contains a complete collection of files, drivers, applications, patches, and answer files that are used to customize Windows installations. A configuration set contains all the required binaries, which are packaged with an associated answer file (**Unattend.xml**).

### Benefits of Configuration Sets

Using configuration sets for unattended installations provides the following benefits:

* A configuration set is a smaller and more portable version of a distribution share, which can have a size of several gigabytes. You can use configuration sets to install Windows operating systems while you are in the field.
* Configuration sets are completely self-contained and have no references outside the file set.
* You can duplicate a configuration set and then edit it for each computer model that you manufacture and release.

> [!Important]
> If a configuration set is used during Windows Setup, all the contents at the root of the media where the answer file exists are copied to the Windows installation. Having many files and folders at the same level as the answer file might slow down installation. In some cases, you might run out of disk space.

## Security Considerations for Distribution Shares and Configuration Sets

Your distribution shares and configuration sets contain private data. The following are recommendations for improving security for distribution shares and configuration sets:

* Restrict access to the contents of distribution shares. Depending on your environment, you can change the access control lists (**ACLs**) or permissions on a distribution share. Only approved accounts should have access to distribution shares.
* Keep applications and device drivers updated with the latest fixes and patches.

## Related topics

[How to Create or Open a Distribution Share](http://go.microsoft.com/fwlink/?LinkId=225113)

[How to Manage Files and Folders in a Distribution Share](http://go.microsoft.com/fwlink/?LinkId=224963)

[How to Add Packages to a Distribution Share](http://go.microsoft.com/fwlink/?LinkId=225111)

[Windows SIM Technical Reference](http://go.microsoft.com/fwlink/?LinkId=214570)
