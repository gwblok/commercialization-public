---
title: Description
description: Description
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e461bc3a-3382-4937-a2cb-0dbb09f9d6f3
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Description


`Description` describes the synchronous command to run specified by [Path](microsoft-windows-setup-runsynchronous-runsynchronouscommand-path.md).

All [RunSynchronous](microsoft-windows-setup-runsynchronous.md) commands run in the system context.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Command_description</em></p></td>
<td><p>Describes the command to run synchronously during the windowsPE configuration pass. <em>Command_description</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [RunSynchronous](microsoft-windows-setup-runsynchronous.md) | [RunSynchronousCommand](microsoft-windows-setup-runsynchronous-runsynchronouscommand.md) | **Description**

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

 

 







