---
title: DoNotOpenInitialConfigurationTasksAtLogon
description: DoNotOpenInitialConfigurationTasksAtLogon
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 804b9196-2212-4095-98de-56080f92b9e5
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# DoNotOpenInitialConfigurationTasksAtLogon


**Warning**  
This setting is deprecated. Use [DoNotOpenServerManagerAtLogon](microsoft-windows-servermanager-svrmgrnc-donotopenservermanageratlogon.md) instead.

 

`DoNotOpenInitialConfigurationTasksAtLogon` specifies whether the Initial Configuration Tasks application opens automatically when the end user logs on for the first time. If it opens automatically, then the Server Manager will not open until the Initial Configuration Tasks application is closed.

**Note**  
To prevent Server Manager from opening when logging on, select **Do not show me this console at logon** in the Server Manager console.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>true</strong></p></td>
<td><p>Specifies that the Initial Configuration Tasks application does not open automatically when the end user logs on for the first time.</p></td>
</tr>
<tr class="even">
<td><p><strong>false</strong></p></td>
<td><p>Specifies that the Initial Configuration Tasks application opens automatically when the end user logs on for the first time. This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


generalize

specialize

## Parent Hierarchy


[Microsoft-Windows-OutOfBoxExperience](microsoft-windows-outofboxexperience.md) | **DoNotOpenInitialConfigurationTasksAtLogon**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-OutOfBoxExperience](microsoft-windows-outofboxexperience.md).

## XML Example


The following XML output specifies that the Initial Configuration Tasks application opens automatically when the end user logs on for the first time.

```
<DoNotOpenInitialConfigurationTasksAtLogon>false</DoNotOpenInitialConfigurationTasksAtLogon>
```

## Related topics


[Microsoft-Windows-OutOfBoxExperience](microsoft-windows-outofboxexperience.md)

[DoNotOpenServerManagerAtLogon](microsoft-windows-servermanager-svrmgrnc-donotopenservermanageratlogon.md)

 

 







