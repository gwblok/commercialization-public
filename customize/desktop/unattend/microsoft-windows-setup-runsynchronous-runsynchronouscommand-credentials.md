---
title: Credentials
description: Credentials
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 941c68bd-08e1-46ea-8036-2dd1d4d865b1
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Credentials

`Credentials` specifies the credentials used when accessing an application over a network. `Credentials` is used to authenticate access to a location specified by [Path](microsoft-windows-setup-runsynchronous-runsynchronouscommand-path.md).

All [RunSynchronous](microsoft-windows-setup-runsynchronous.md) commands run in the system context.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Domain](microsoft-windows-setup-runsynchronous-runsynchronouscommand-credentials-domain.md) | Specifies the domain of the account used for authentication. |
| [Password](microsoft-windows-setup-runsynchronous-runsynchronouscommand-credentials-password.md) | Specifies the password of the account used for authentication. |
| [UserName](microsoft-windows-setup-runsynchronous-runsynchronouscommand-credentials-username.md) | Specifies the user name of the account used for authentication. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | [RunSynchronous](microsoft-windows-setup-runsynchronous.md) | [RunSynchronousCommand](microsoft-windows-setup-runsynchronous-runsynchronouscommand.md) | **Credentials**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output shows how to set synchronous commands.

```XML
<RunSynchronous>
   <!-- First synchronous command to execute -->
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
<!-- Second synchronous command to execute -->
   <RunSynchronousCommand>
      <Order>2</Order>
      <Path>C:\AnotherApplication.exe</Path>
      <Description>DescriptionOfMyApplication</Description>
   </RunSynchronousCommand>
</RunSynchronous>
```

## Related topics

[RunSynchronousCommand](microsoft-windows-setup-runsynchronous-runsynchronouscommand.md)
