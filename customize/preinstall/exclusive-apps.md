---
title: Exclusive apps
description: OEMs can work with software developers to target OEM devices for apps to appear exclusively on, based on values set in the registry.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 12/6/2017
ms.topic: article


---
# Exclusive apps

By forming relationships with developers, you can work together to publish exclusive apps onto your devices. You have the flexibility based on the contracts you establish with developers to ensure that these apps are available exclusively on your Windows 10-based devices (as identified by OEM Store ID) and don't appear in the general catalog on any other devices.

Your exclusive apps must be submitted to the Microsoft Store by a developer that you are in an exclusive relationship with, as defined in the Microsoft Store OEM Program enrollment form. You may also set up your own exclusive developer account where apps published from that account are automatically designated as exclusive.
<!-- Not sure if this documentation is really available or not. I need access to the platform. -->
<!--
The process to follow to set up your account for submitting exclusive apps to include on your Windows 10 image are in the **Microsoft Store OEM Program Guide**, available for download from the [Device Partner Center](https://devicepartner.microsoft.com/).
-->

> [!Note]
> Exclusive app accounts are only available to OEM developer accounts unless you have been granted an exception.

## Set your OEM Store ID and SCM ID

You must insert a combination of unique identifiers into your images to facilitate exclusive app features. These features rely on the OEM Store ID (previously referred to as the OEM ID) and optionally the Store Content Modifier ID (SCM ID). The OEM Store ID and the Store Content Modifier (SCM) will be provided by the Microsoft Store Partner Operations team at your request.

### OEM Store ID

The OEM Store ID is required for you to create your OEM Store in the Microsoft Store and for app exclusivity. Here are the characteristics of an OEM Store ID:

* Assignment is a one-time operation; each OEM should have one and only one unique OEM Store ID.
* You must populate your OEM Store ID to the registry field specified in the [Registry Field Requirements](#registry-field-requirements) section below.
* OEM Store ID is set during manufacturing and cannot be changed later. For manufacturing guidance, see [OEM Deployment of Windows 10 for desktop editions](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/oem-deployment-of-windows-10-for-desktop-editions).

### SCM ID

The Store Content Modifier ID (SCM ID) is optional. You can use it in addition to your OEM Store ID, but never instead of the OEM Store ID. Here are the characteristics of an SCM ID:

* SCM IDs are used to differentiate between different sub-brands, devices, and/or device groups belonging to a given OEM for specialized OEM Store or exclusive app experiences.
* Each OEM can have multiple SCM IDs; however, each specified segment (devices/brands/devices groups) must be identified by a single, unique SCM ID populated on all devices belonging to the given target segment.
* Each device can have at most one SCM ID.
* You populate the SCM ID to the registry field specified in the [Registry Field Requirements](#registry-field-requirements) section below.
* The SCM ID is set during manufacturing and cannot be changed later. For manufacturing guidance, see [OEM Deployment of Windows 10 for desktop editions](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/oem-deployment-of-windows-10-for-desktop-editions).
* Depending on your business needs and objectives, you decide what level of granularity you want to use for your SCM IDs. However, consider that additional SCM IDs add more complexity and will take more work and resources to support. The table below describes some possible options.

| OEM-ID         | SCM ID                | Description                                                               |
|:---------------|:----------------------|:--------------------------------------------------------------------------|
| FABRIKAM       | Fabrikam_Enterprise   | Device group - segmenting devices geared towards enterprise customers.   |
| FABRIKAM       | Fabrikam_Proseware    | Brand group - grouping of the "Proseware" branded devices.                |
| FABRIKAM       | Fabrikam_ProsewareX2  | Device group - device-specific segment, Fabrikam Proseware model X2.      |

> [!Note]
> If you do not currently have an SCM or chose not to differentiate your OEM Store by using a SCM, contact the Microsoft Store Partner Operations Team for instructions on setting up an OEM Store using only an OEM Store ID. If you have an SCM ID that was created for your Windows 8.1 devices, you can still use that SCM ID for your Windows 10-based device.  If you do so, you will still need to obtain your OEM Store ID from the Microsoft Store Partner Operations Team and insert that into your Windows 10 image.

### Registry field requirements

In order to use exclusive app features, you must set the following fields in the registries of the target devices.

| Key               | Location                                              | Type   | Value                                                                        |
|:------------------|:------------------------------------------------------|:-------|:-----------------------------------------------------------------------------|
| OEMID             | HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Store  | REG_SZ | The OEM Store ID provided by the Microsoft Store Partner Operations team.    |
| StoreContentModifier | HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Store  | REG_SZ | The SCM ID provided by the Microsoft Store Partner Operations team.       |

> [!Note]
> The **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Store\Configuration** key should not be used by OEMs. It is where the Store application writes the values it discovers so that the OS components are using the same settings cross applications.

If you are using Windows Configuration Designer to create an image, you can add a Windows setting: `WindowsStore\ContentModifier`

### Microsoft Store process

The following list shows some of the key tasks and workflows for engaging with the Store. Depending on your needs, the order and importance of each of these tasks and workflows varies:

* OEM works with Microsoft Store Partner Operations on plans for their exclusive Store in Store.
* Microsoft Store Partner Operations creates device identification marker for inclusion in the registry.
* OEM builds device ID into the registry.
* Microsoft Store Partner Operations enables OEM Store merchandising tools.
* OEM curates content and controls publishing of OEM Store content.

## Send SMBIOS information to Microsoft

Because the OEM Store ID is not saved upon migration, including upon upgrade, you must ensure that Microsoft has the correct SMBIOS details of the device to enable it for customized Store experiences. Please contact [partnerops@microsoft.com](mailto:partnerops@microsoft.com) with the **SMBIOS Manufacturer**, and **SMBIOS Product Name**, for your device.

* The SMBIOS Manufacturer value can be found under the registry key `HKLM\System\CurrentControlSet\Control\SystemInformation\Manufacturer`
* The SMBIOS Product Name can be found under the registry key `HKLM\System\CurrentControlSet\Control\SystemInformation\SystemProductName`
