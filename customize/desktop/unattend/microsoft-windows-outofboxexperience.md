---
title: Microsoft-Windows-OutOfBoxExperience
description: Microsoft-Windows-OutOfBoxExperience
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: bef5769c-d0b8-4f63-8910-7e355203d2ec
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-OutOfBoxExperience

> [!Warning]
> This setting is deprecated. The Initial Configurations Tasks application is not available in Windows Server 2012.

The Microsoft-Windows-OutOfBoxExperience component specifies details about the Initial Configuration Tasks for end users in Windows Server 2008 R2 and Windows Server 2008. To configure the Out of Box Experience, see the topic [Automate Windows OOBE](http://go.microsoft.com/fwlink/p/?linkid=206674).

## In This Section

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [DoNotOpenInitialConfigurationTasksAtLogon](microsoft-windows-outofboxexperience-donotopeninitialconfigurationtasksatlogon.md) | Specifies whether the <strong>Initial Configuration Tasks</strong> application opens automatically when the end user logs on for the first time. |
| [OemExtensionXmlFilePath](microsoft-windows-outofboxexperience-oemextensionxmlfilepath.md) | Specifies the path to the OEM XML file that contains the OEM resources and tasks that are displayed in the <strong>Initial Configuration Tasks</strong> and <strong>Server Manager</strong> applications. |

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

## Related topics

[Components](components-b-unattend.md)
