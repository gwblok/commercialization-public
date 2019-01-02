---
title: OemExtensionXmlFilePath
description: OemExtensionXmlFilePath
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4f507e62-de65-4937-80fc-3d20fb826788
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# OemExtensionXmlFilePath


**Warning**  
This setting is deprecated. By default, the Initial Configurations Tasks application does not appear in Windows Server 2012. Use [Microsoft-Windows-ServerManager-SvrMgrNc](microsoft-windows-servermanager-svrmgrnc.md) instead.

 

`OemExtensionXmlFilePath` specifies the path to the OEM XML file that contains the OEM resources and tasks that are displayed in the Initial Configuration Tasks and Server applications. OEMs are able to add information and links to Help topics and their own applications that need to be started.

The OEM XML file must be located in either the `%WINDIR%\system32` directory or in one of its subdirectories. For example, `C:\windows\system32\OEM\OEMExtension.xml`

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>File_path</em></p></td>
<td><p>Specifies the path to the OEM XML file that contains the OEM resources and tasks that are displayed in the Initial Configuration Tasks and Server applications. <em>File_path</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-OutOfBoxExperience](microsoft-windows-outofboxexperience.md) | **OemExtensionXmlFilePath**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-OutOfBoxExperience](microsoft-windows-outofboxexperience.md).

## XML Example


The following XML output specifies the path to the OEM XML file that contains the OEM resources and tasks that are displayed in the Initial Configuration Tasks and Server applications.

```
<OemExtensionXmlFilePath>C:\windows\system32\OEM\OEMExtension.xml</OemExtensionXmlFilePath>
```

## Related topics


[Microsoft-Windows-OutOfBoxExperience](microsoft-windows-outofboxexperience.md)

 

 







