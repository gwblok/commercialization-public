---
title: Password
description: Password
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: acdfc820-dcee-4912-b886-ba87c511588c
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Password


`Password` specifies the password of the user account used to authenticate access to the location specified by [Path](microsoft-windows-setup-runasynchronous-runasynchronouscommand-path.md).

All [RunAsynchronous](microsoft-windows-setup-runasynchronous.md) commands run in the system context.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Password</em></p></td>
<td><p>Specifies the password of the user account used for authentication. <em>Password</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


windowsPE

## Parent Hierarchy


[microsoft-windows-setup-](microsoft-windows-setup.md) | [RunAsynchronous](microsoft-windows-setup-runasynchronous.md) | [RunAsynchronousCommand](microsoft-windows-setup-runasynchronous-runasynchronouscommand.md) | [Credentials](microsoft-windows-setup-runasynchronous-runasynchronouscommand-credentials.md) | **Password**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-setup-](microsoft-windows-setup.md).

## XML Example


The following XML output shows how to configure asynchronous commands to run.

```
<RunAsynchronous>
   <RunAsynchronousCommand>
      <Order>1</Order>
      <Path>\\MyNetworkShare\MyApplication.exe</Path>
      <Description>DescriptionOfMyApplication</Description>
      <Credentials>
         <Domain>FabrikamDomain</Domain>
         <UserName>MyUserName</UserName>
         <Password>MyPassword</Password>
      </Credentials>
   </RunAsynchronousCommand>
   <RunAsynchronousCommand>
      <Order>2</Order>
      <Path>C:\AnotherApplication.exe</Path>
      <Description>DescriptionOfMyApplication</Description>
   </RunAsynchronousCommand>
</RunAsynchronous>
```

## Related topics


[Credentials](microsoft-windows-setup-runasynchronous-runasynchronouscommand-credentials.md)

 

 







