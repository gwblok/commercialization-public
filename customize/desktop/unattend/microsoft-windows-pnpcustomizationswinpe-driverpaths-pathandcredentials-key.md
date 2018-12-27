---
title: Key
description: Key
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f939dc72-1f6e-4329-8d67-1886bc2d5d1a
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# Key


`Key` specifies the unique string to identify the device-driver path.

**Note**  
The value for `Key` is added to the answer file as an attribute of the [PathAndCredentials](microsoft-windows-pnpcustomizationswinpe-driverpaths-pathandcredentials.md) element. The attribute `wcm:keyValue` is used to identify each unique device-driver path. For example, you can specify three different device-driver paths by using the `Key` values of **Path1**, **Path2**, and **Path3**.

 

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Key</em></p></td>
<td><p>Specifies the unique string used to identify the device-driver path. <em>Key</em> is a string.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


auditSystem

offlineServicing

## Parent Hierarchy


[microsoft-windows-pnpcustomizationswinpe-](microsoft-windows-pnpcustomizationswinpe.md) | [DriverPaths](microsoft-windows-pnpcustomizationswinpe-driverpaths.md) | [PathAndCredentials](microsoft-windows-pnpcustomizationswinpe-driverpaths-pathandcredentials.md) | **Key**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [microsoft-windows-pnpcustomizationswinpe-](microsoft-windows-pnpcustomizationswinpe.md).

## XML Example


The following XML output specifies the UNC paths to two additional locations for device drivers and the credentials used to access those paths.

```
<DriverPaths>
<!-- First PathAndCredentials list item -->
   <PathAndCredentials wcm:action="add" wcm:keyValue="Path1">
      <Path>\\myFirstDriverPath\DriversFolder</Path>
      <Credentials>
         <Domain>MyDomain</Domain>
         <Username>MyUsername</Username>
         <Password>MyPassword</Password>
      </Credentials>
   </PathAndCredentials>
<!-- Second PathAndCredentials list item -->
   <PathAndCredentials wcm:action="add" wcm:keyValue="Path2">
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

 

 







