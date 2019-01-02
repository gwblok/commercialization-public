---
title: LinearityData
description: LinearityData
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9731a8c6-22c7-4a60-93b3-1996c4a8f7a7
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# LinearityData

`LinearityData` is a container for one or more instances of [DeviceElement](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md). This key is the parent key for calibration data for particular devices. You can create subkeys under this key to include calibration data for a particular digitizer. Run `tabcal.exe -export` to produce a device ID and a hexadecimal string containing calibration data. Insert the device ID and hexadecimal string under linearity data as a new subkey, using the device ID as a name and the calibration data as the value.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [DeviceElement](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement.md) | Specifies a device. |

## Parent Hierarchy

[Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md) | **LinearityData**

## Valid Configuration Passes

offlineServicing

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md).

## XML Example

The following XML output shows two devices specified, by using `LinearityData`.

```XML
<LinearityData>
<DeviceElement wcm:action="modify" wcm:keyValue="MyKey">11</DeviceElement>
<DeviceElement wcm:action="add" wcm:keyValue="MyKey1">12</DeviceElement>
</LinearityData>
```

## Related topics

[Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md)
