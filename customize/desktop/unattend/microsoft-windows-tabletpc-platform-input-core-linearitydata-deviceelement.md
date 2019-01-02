---
title: DeviceElement
description: DeviceElement
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4591d9e3-d6a4-4161-bedf-690e95446ede
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# DeviceElement

`DeviceElement` specifies calibration data for particular devices. The setting enables you to include calibration data for a particular digitizer. Run `tabcal.exe -export` and produce a device ID and a hexadecimal string containing calibration data. Insert the device ID and hexadecimal string under `LinearityData` as a new subkey. Use the device ID as a name and the calibration data as the value.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [Key](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement-key.md) | Specifies a unique key for the <code>DeviceElement</code>. |
| [Value](microsoft-windows-tabletpc-platform-input-core-linearitydata-deviceelement-value.md) | Specifies the value of the <code>DeviceElement</code>. |

## Parent Hierarchy

[Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md) | [LinearityData](microsoft-windows-tabletpc-platform-input-core-linearitydata.md) | **DeviceElement**

## Valid Configuration Passes

offlineServicing

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md).

## XML Example

The following XML output shows how to configure `DeviceElement`.

```XML
<LinearityData>
<DeviceElement wcm:action="add" wcm:keyValue="MyKey">11</DeviceElement>
</LinearityData>
```

## Related topics

[Microsoft-Windows-TabletPC-Platform-Input-Core](microsoft-windows-tabletpc-platform-input-core.md)
