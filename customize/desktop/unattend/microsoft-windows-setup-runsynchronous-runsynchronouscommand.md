---
title: RunSynchronousCommand
description: RunSynchronousCommand
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 21af3c4a-4432-4c88-97c3-2c282bdefc26
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# RunSynchronousCommand

`RunSynchronousCommand` specifies a single command to run during the windowsPE configuration pass.

To start a command that needs to finish before other commands can start, use synchronous commands. To run services or commands that can start at the same time, use [RunAsynchronousCommand](microsoft-windows-setup-runasynchronous-runasynchronouscommand.md) instead.

All `RunSynchronous` commands run in the system context.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Credentials](microsoft-windows-setup-runsynchronous-runsynchronouscommand-credentials.md) | Specifies the credentials used to access the command if the command is on a network share. |
| [Description](microsoft-windows-setup-runsynchronous-runsynchronouscommand-description.md) | Describes the synchronous command to run. |
| [Order](microsoft-windows-setup-runsynchronous-runsynchronouscommand-order.md) | Specifies the order of the command to run. |
| [Path](microsoft-windows-setup-runsynchronous-runsynchronouscommand-path.md) | Specifies the path to the command to run. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | [RunSynchronous](microsoft-windows-setup-runsynchronous.md) | **RunSynchronousCommand**

## Applies To

For the list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output shows how to set synchronous commands.

```XML
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

[RunSynchronous](microsoft-windows-setup-runsynchronous.md)

[RunAsynchronousCommand](microsoft-windows-setup-runasynchronous-runasynchronouscommand.md)
