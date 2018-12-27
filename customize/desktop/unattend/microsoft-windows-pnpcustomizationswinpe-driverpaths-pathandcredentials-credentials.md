---
title: Credentials
description: Credentials
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1ecbaae7-0509-4f5d-918f-610332730109
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Credentials

`Credentials` is an optional setting used to access the Universal Naming Convention (UNC) path specified by the [Path](microsoft-windows-pnpcustomizationswinpe-driverpaths-pathandcredentials-path.md).

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Domain](microsoft-windows-pnpcustomizationswinpe-driverpaths-pathandcredentials-credentials-domain.md) | Specifies the domain of the account used for authentication. If the account is not a domain account, then the computer name should be used instead of the domain name. |
| [Password](microsoft-windows-pnpcustomizationswinpe-driverpaths-pathandcredentials-credentials-password.md) | Specifies the password of the account used for authentication. |
| [Username](microsoft-windows-pnpcustomizationswinpe-driverpaths-pathandcredentials-credentials-username.md) | Specifies the user name of the account. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-PnpCustomizationsWinPE](microsoft-windows-pnpcustomizationswinpe.md) | [DriverPaths](microsoft-windows-pnpcustomizationswinpe-driverpaths.md) | [PathAndCredentials](microsoft-windows-pnpcustomizationswinpe-driverpaths-pathandcredentials.md) | **Credentials**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-PnpCustomizationsWinPE](microsoft-windows-pnpcustomizationswinpe.md).

## XML Example

The following XML output specifies the UNC paths to additional locations for device drivers and the credentials used to access those paths.

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

[PathAndCredentials](microsoft-windows-pnpcustomizationswinpe-driverpaths-pathandcredentials.md)
