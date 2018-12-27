---
title: Credentials
description: Credentials
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 37dbfd09-f3c1-4ac7-ab4f-c864e3616cbe
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Credentials

`Credentials` is an optional setting that is used to access the Universal Naming Convention (UNC) path specified by the [Path](microsoft-windows-pnpcustomizationsnonwinpe-driverpaths-pathandcredentials-path.md).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Domain](microsoft-windows-pnpcustomizationsnonwinpe-driverpaths-pathandcredentials-credentials-domain.md) | Specifies the domain of the account used for authentication. Can optionally be used to specify the name of the computer. |
| [Password](microsoft-windows-pnpcustomizationsnonwinpe-driverpaths-pathandcredentials-credentials-password.md) | Specifies the password of the account to use for authentication. |
| [Username](microsoft-windows-pnpcustomizationsnonwinpe-driverpaths-pathandcredentials-credentials-username.md) | Specifies the user name of the account to use for authentication. |

## Valid Configuration Passes

auditSystem

offlineServicing

## Parent Hierarchy

[Microsoft-Windows-PnpCustomizationsNonWinPE](microsoft-windows-pnpcustomizationsnonwinpe.md) | [DriverPaths](microsoft-windows-pnpcustomizationsnonwinpe-driverpaths.md) | [PathAndCredentials](microsoft-windows-pnpcustomizationsnonwinpe-driverpaths-pathandcredentials.md) | **Credentials**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-PnpCustomizationsNonWinPE](microsoft-windows-pnpcustomizationsnonwinpe.md).

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

[PathAndCredentials](microsoft-windows-pnpcustomizationsnonwinpe-driverpaths-pathandcredentials.md)
