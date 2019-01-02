---
title: PathAndCredentials
description: PathAndCredentials
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 21e2c6c1-1dda-4a94-8fb0-ab3c2980a46e
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# PathAndCredentials

`PathAndCredentials` is a list item type and specifies the local or Universal Naming Convention (UNC) path to an additional location for out-of-box device drivers and, optionally, the credentials used to access that path.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Credentials](microsoft-windows-pnpcustomizationswinpe-driverpaths-pathandcredentials-credentials.md) | Specifies the credentials used to access the path specified by the [Path](microsoft-windows-pnpcustomizationswinpe-driverpaths-pathandcredentials-path.md). (Optional) |
| [Key](microsoft-windows-pnpcustomizationswinpe-driverpaths-pathandcredentials-key.md) | Specifies a unique string identifier for the driver path. |
| [Path](microsoft-windows-pnpcustomizationswinpe-driverpaths-pathandcredentials-path.md) | Specifies a local or UNC path that contains additional out-of-box device drivers that you copy to the Windows image. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-PnpCustomizationsWinPE](microsoft-windows-pnpcustomizationswinpe.md) | [DriverPaths](microsoft-windows-pnpcustomizationswinpe-driverpaths.md) | **PathAndCredentials**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-PnpCustomizationsWinPE](microsoft-windows-pnpcustomizationswinpe.md).

## XML Example

The following XML output specifies the UNC paths to two additional locations for device drivers and the credentials used to access those paths.

```XML
<DriverPaths>
<!-- First PathAndCredentials list item -->
   <PathAndCredentials wcm:action="add" wcm:keyValue="1">
      <Path>\\myFirstDriverPath\DriversFolder</Path>
      <Credentials>
         <Domain>MyDomain</Domain>
         <Username>MyUsername</Username>
         <Password>MyPassword</Password>
      </Credentials>
   </PathAndCredentials>
<!-- Second PathAndCredentials list item -->
   <PathAndCredentials wcm:action="add" wcm:keyValue="2">
      <Path>C:\Drivers</Path>
      <Credentials>
         <Domain>MyComputerName</Domain>
         <Username>MyUsername</Username>
         <Password>MyPassword</Password>
      </Credentials>
   </PathAndCredentials>
</DriverPaths>
```

## Related topics

[DriverPaths](microsoft-windows-pnpcustomizationswinpe-driverpaths.md)
