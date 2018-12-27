---
title: Domain
description: Domain
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: fa26b6d2-2903-47cb-a974-52eade0c8ea2
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Domain


`Domain` specifies the domain name of the account to use for authentication. If the account is not a domain account, then the computer name should be used instead of the domain name. For example, if a computer named SYSTEM1 is connected to the FABRIKAM domain, then you can specify credentials in one of the following ways:

-   FABRIKAM\\*User\_Name* and the account password. In this case, the value for the `Domain` setting is **FABRIKAM**.

-   SYSTEM1\\*User\_Name* and the user name password on the SYSTEM1 computer. You can use any account on the computer. In this case, the value for the `Domain` setting is **SYSTEM1**.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Domain_name</em></p></td>
<td><p>Specifies the domain name or the computer name of the account used to authenticate the <a href="microsoft-windows-pnpcustomizationsnonwinpe-driverpaths-pathandcredentials-path.md" data-raw-source="[Path](microsoft-windows-pnpcustomizationsnonwinpe-driverpaths-pathandcredentials-path.md)">Path</a>.</p>
<p><em>Domain_name</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type supports empty elements.

## Valid Configuration Passes


auditSystem

offlineServicing

## Parent Hierarchy


[Microsoft-Windows-PnpCustomizationsNonWinPE](microsoft-windows-pnpcustomizationsnonwinpe.md) | [DriverPaths](microsoft-windows-pnpcustomizationsnonwinpe-driverpaths.md) | [PathAndCredentials](microsoft-windows-pnpcustomizationsnonwinpe-driverpaths-pathandcredentials.md) | [Credentials](microsoft-windows-pnpcustomizationsnonwinpe-driverpaths-pathandcredentials-credentials.md) | **Domain**

## Applies To


For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-PnpCustomizationsNonWinPE](microsoft-windows-pnpcustomizationsnonwinpe.md).

## XML Example


The following XML output specifies the Universal Naming Convention (UNC) paths to two additional locations for device drivers and the credentials used to access those paths.

```
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


[Credentials](microsoft-windows-pnpcustomizationsnonwinpe-driverpaths-pathandcredentials-credentials.md)

 

 







