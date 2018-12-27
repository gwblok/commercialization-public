---
title: Credentials
description: Credentials
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1a426bee-9333-414c-825e-731aab59eacc
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Credentials

`Credentials` specifies the credentials to use when accessing the [Path](microsoft-windows-deployment-runasynchronous-runasynchronouscommand-path.md).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Domain](microsoft-windows-deployment-runasynchronous-runasynchronouscommand-credentials-domain.md) | Specifies the domain of the account to use for authentication. |
| [Password](microsoft-windows-deployment-runasynchronous-runasynchronouscommand-credentials-password.md) | Specifies the password of the account to use for authentication. |
| [Username](microsoft-windows-deployment-runasynchronous-runasynchronouscommand-credentials-username.md) | Specifies the user name of the account to use for authentication. |

## Valid Configuration Passes

auditUser

specialize

## Parent Hierarchy

[Microsoft-Windows-Deployment](microsoft-windows-deployment.md) | [RunAsynchronous](microsoft-windows-deployment-runasynchronous.md) | [RunAsynchronousCommand](microsoft-windows-deployment-runasynchronous-runasynchronouscommand.md) | **Credentials**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Deployment](microsoft-windows-deployment.md).

## XML Example

The following XML output shows how to set asynchronous commands.

```XML
<RunAsynchronous>
   <RunAsynchronousCommand wcm:action="add">
      <Credentials>
         <Domain>MyDomain</Domain>
         <Password>MyPassword</Password>
         <Username>MyUsername</Username>
      </Credentials>
      <Description>AsynchCommand1</Description>
      <Order>1</Order>
      <Path>\\network\server\share\filename</Path>
   </RunAsynchronousCommand>
   <RunAsynchronousCommand wcm:action="add">
      <Credentials>
         <Domain>MyDomain</Domain>
         <Password>MyPassword</Password>
         <Username>MyUsername</Username>
      </Credentials>
      <Description>AsynchCommand2</Description>
      <Order>2</Order>
      <Path>\\network\server\share\filename</Path>
   </RunAsynchronousCommand>
</RunAsynchronous>
```

## Related topics

[RunAsynchronousCommand](microsoft-windows-deployment-runasynchronous-runasynchronouscommand.md)
