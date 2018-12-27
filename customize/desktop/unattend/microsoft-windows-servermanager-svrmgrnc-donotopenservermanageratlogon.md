---
title: DoNotOpenServerManagerAtLogon
description: DoNotOpenServerManagerAtLogon
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c3b13ab4-b5c8-4ce3-a86f-fcf8028fcde7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DoNotOpenServerManagerAtLogon


`DoNotOpenServerManagerAtLogon` specifies whether the Server Manager application opens when the end user logs on for the first time.

**Note**  
End users can specify whether the Initial Configuration Tasks application opens automatically when they log on. If it opens automatically, then the Server Manager will not open until the Initial Configuration Tasks application is closed. To prevent Server Manager from opening when logging on, select **Do not show me this console at logon** in the Server Manager console.

 

This setting has no effect on Server Core installations of Windows Server 2008, Windows Server 2008 R2, and Windows Server 2012.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the Server Manager application does not open when the end user logs on for the first time.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the Server Manager application opens when the end user logs on for the first time. This is the default setting.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-ServerManager-SvrMgrNc](microsoft-windows-servermanager-svrmgrnc.md) | **DoNotOpenServerManagerAtLogon**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-ServerManager-SvrMgrNc](microsoft-windows-servermanager-svrmgrnc.md)

## XML Example


The following XML output shows how to specify that Server Manager opens the first time the end user logs on.

```
<DoNotOpenServerManagerAtLogon>false</DoNotOpenServerManagerAtLogon>
```

## Related topics


[Microsoft-Windows-ServerManager-SvrMgrNc](microsoft-windows-servermanager-svrmgrnc.md)

[DoNotOpenInitialConfigurationTasksAtLogon](microsoft-windows-outofboxexperience-donotopeninitialconfigurationtasksatlogon.md)

[OemExtensionXmlFilePath](microsoft-windows-outofboxexperience-oemextensionxmlfilepath.md)

 

 







