---
title: Credentials
description: Credentials
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e8bb03c3-b591-49f8-9db1-1d37b3bb2651
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Credentials

`Credentials` specifies the credentials to use when accessing the [Path](microsoft-windows-deployment-runsynchronous-runsynchronouscommand-path.md).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Domain](microsoft-windows-deployment-runsynchronous-runsynchronouscommand-credentials-domain.md) | Specifies the domain of the account to use for authentication. |
| [Password](microsoft-windows-deployment-runsynchronous-runsynchronouscommand-credentials-password.md) | Specifies the password of the account to use for authentication. |
| [Username](microsoft-windows-deployment-runsynchronous-runsynchronouscommand-credentials-username.md) | Specifies the user name of the account to use for authentication. |

## Valid Configuration Passes

auditUser

specialize

## Parent Hierarchy

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [RunSynchronous](microsoft-windows-deployment-runsynchronous.md) | [RunSynchronousCommand](microsoft-windows-deployment-runsynchronous-runsynchronouscommand.md) | **Credentials**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

## XML Example

The following XML output shows how to set synchronous commands.

```XML
<RunSynchronous>
   <RunSynchronousCommand wcm:action="add">
      <Credentials>
         <Domain>MyDomain</Domain>
         <Password>MyPassword</Password>
         <Username>MyUsername</Username>
      </Credentials>
      <Description>MySynchCommand1</Description>
      <Order>1</Order>
      <Path>\\network\server\share\filename</Path>
      <WillReboot>OnRequest</WillReboot>
   </RunSynchronousCommand>
   <RunSynchronousCommand wcm:action="add">
      <Credentials>
         <Domain>MyDomain</Domain>
         <Password>MyPassword</Password>
         <Username>MyUsername</Username>
      </Credentials>
      <Description>MySynchCommand2</Description>
      <Order>2</Order>
      <Path>\\network\server\share\filename</Path>
      <WillReboot>OnRequest</WillReboot>
   </RunSynchronousCommand>
</RunSynchronous>
```

## Related topics

[RunSynchronousCommand](microsoft-windows-deployment-runsynchronous-runsynchronouscommand.md)
