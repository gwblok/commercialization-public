---
title: Path
description: Path
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3e26c13f-b2b3-49f9-bd8d-b32e04cf3b64
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Path


`Path` specifies the path and the name of the command to run.

All [RunSynchronous](microsoft-windows-setup-runsynchronous.md) commands run in the system context.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Path_to_command</em></p></td>
<td><p>Specifies the path and the file name of the command to run synchronously. The path can be a local path or a Universal Naming Convention (UNC) path. If the path is a UNC path, <a href="microsoft-windows-setup-runsynchronous-runsynchronouscommand-credentials.md" data-raw-source="[Credentials](microsoft-windows-setup-runsynchronous-runsynchronouscommand-credentials.md)">Credentials</a> must be specified.</p>
<p><em>Path_to_command</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [RunSynchronous](microsoft-windows-setup-runsynchronous.md) | [RunSynchronousCommand](microsoft-windows-setup-runsynchronous-runsynchronouscommand.md) | **Path**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows how to set synchronous commands.

```
<RunSynchronous>
   <!-- First synchronous command to run -->
   <RunSynchronousCommand>
      <Order>1</Order>
      <Path>\\MyNetworkShare\MyApplication.exe</Path>
      <Description>DescriptionOfMyApplication</Description>
      <Credentials>
         <Domain>FabrikamDomain</Domain>
         <UserName>MyUserName</UserName>
         <Password>MyPassword</Password>
      </Credentials>
   </RunSynchronousCommand>
<!-- Second synchronous command to run -->
   <RunSynchronousCommand>
      <Order>2</Order>
      <Path>C:\AnotherApplication.exe</Path>
      <Description>DescriptionOfMyApplication</Description>
   </RunSynchronousCommand>
</RunSynchronous>
```

## Related topics


[RunSynchronousCommand](microsoft-windows-setup-runsynchronous-runsynchronouscommand.md)

 

 







