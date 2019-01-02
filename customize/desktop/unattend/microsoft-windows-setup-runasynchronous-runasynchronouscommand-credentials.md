---
title: Credentials
description: Credentials
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d3dca721-9f14-4566-a1cb-f9273cae9813
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Credentials

`Credentials` specifies the credentials to use when accessing a data image file specified by [Path](microsoft-windows-setup-runasynchronous-runasynchronouscommand-path.md).

All [RunAsynchronous](microsoft-windows-setup-runasynchronous.md) commands run in the system context.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Domain](microsoft-windows-setup-runasynchronous-runasynchronouscommand-credentials-domain.md) | Specifies the domain of the account used for authentication. |
| [Password](microsoft-windows-setup-runasynchronous-runasynchronouscommand-credentials-password.md) | Specifies the password of the account used for authentication. |
| [Username](microsoft-windows-setup-runasynchronous-runasynchronouscommand-credentials-username.md) | Specifies the user name of the account used for authentication. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | [RunAsynchronous](microsoft-windows-setup-runasynchronous.md) | [RunAsynchronousCommand](microsoft-windows-setup-runasynchronous-runasynchronouscommand.md) | **Credentials**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output shows how to configure asynchronous commands to run.

```XML
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

[RunAsynchronousCommand](microsoft-windows-setup-runasynchronous-runasynchronouscommand.md)
