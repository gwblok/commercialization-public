---
title: Customize a Specific Absorption Rate (SAR) table
description: Customize and enable a SAR mapping table
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 10/17/2017
ms.topic: article


---
# Customize a Specific Absorption Rate (SAR) mapping table

You can configure and store a Specific Absorption Rate (SAR) table for mobile broadband modems in the registry. When a mobile broadband modem is connected to the Windows device, Windows automatically uses the table to map the mobile country code (MCC) of the modem's registered mobile operator (MO) to its appropriate SAR back-off index, and configure the modem with it.

You may choose to configure the registry settings at imaging time, or run-time. If you build the registry settings into the image at image deployment time within a package, the SAR mapping table will be ready for any OS component as soon as it starts. If you use a run-time component to configure the registry settings after device bootup, you ensure that the static SAR configuration will not be changed and/or wiped out by Windows installation or upgrade, and that it stays consistent to the device and independent of OS installation.

For more details on SAR support for mobile broadband modems, please see [Mobile Broadband Specific Absorption Rate Platform Support](https://docs.microsoft.com/en-us/windows-hardware/drivers/network/mb-sar-platform-support).

Here is an overview of how Windows will read and configure the modem based on your customized SAR mapping table:

1. Create a package that contains your registry settings, including those for the [SARMappingTable](#sar-mapping-table) and [SARConfiguration](#sar-configuration).

1. Build the package into the image for the device.

1. Windows (the WWAN service, in particular) will read the registry at start-up and store the settings for later usage when an embedded, SAR-capable modem registers with a particular MO.

1. Windows also listens to registry change notifications to know if the registry for the settings is changed. This means you may use your own way of adding and changing the settings at run-time, and Windows will accept the changes immediately.

1. When a modem is registered with an MO at run-time, Windows takes the MCC of the MO and finds the corresponding SAR back-off index(es) from the SAR mapping table.

1. Windows will then send the SAR back-off index to the modem using the MBIM interface defined in [Mobile Broadband Specific Absorption Rate Platform Support](https://docs.microsoft.com/en-us/windows-hardware/drivers/network/mb-sar-platform-support).

1. When the modem roams to another country, the MCC for the new MO will change. Windows will again find the corresponding SAR back-off index(es) from the SAR mapping table using the MCC of the new MO and send it to modem.

## Registry location and syntax

The registry settings to build and configure the SAR mapping table reside exclusively under the base registry key: 

`HKLM\OEM\Cellular\DeviceSpecific`

Under the base key, there are two subkeys:

* [SARMappingTable](#sar-mapping-table): contains the SAR back-off index mapping table.

* [SARConfiguration](#sar-configuration): contains control settings.

Setting these subkeys is entirely optional. You may supply static SAR configuration settings at image-time or update any static settings at run-time. 

> [!Note]
> If you have components update the settings at run-time, you must increment the configuration version number in the registry value `ConfigurationVersion` as the last write to the registry. Whenever the `ConfigurationVersion` registry value is changed, Windows will read all configuration settings and put them into effect.

## <a name="sar-mapping-table"></a>SARMappingTable subkey

The `SARMappingTable` subkey may have up to 1000 registry values. The SAR back-off index(es) is per country. The SAR back-off table will be able to support one entry per country. A country in this context is identified by the standard MCC (Mobile Country Code).

> [!Note]
> The value name must consist of three decimal-digit characters that represents the MCC. There may be up to 1000 registry value names, "000" through "999".

| Value name                                 | Type                        | Data                                                                               |
|:-------------------------------------------|:----------------------------|:-----------------------------------------------------------------------------------|
| *Three-decimal-digit representing the MCC* | WCHAR string                | Comma-separated decimal number in WCHAR string, such as `0,2,5,8`. The numbers represent the SAR back-off indexes for the MCC. The sequence of back-off indexes corresponds to an array of antennas in modem, with the first back-off index for the antenna at index 0, the second back-off index for the antenna at index 1, and so on. For a simple modem with only one antenna, there needs to be only one index in the string, such as “2”, for the first and only antenna.          |

If a registry value for a particular MCC is absent, the data in the special reg value `000` will be used. You may use this default value for countries that do not need specific back-off indexes. If both a registry value for the MCC and the special reg value `000` are absent, no SAR index will be used for the MCC.

## <a name="sar-configuration"></a>SARConfiguration subkey

The `SARConfiguration` settings do not affect your ability to use modem DSI messages to pass through. For example, SAR proxy may implement a custom design for SAR control and mapping using the existing API (the WWAN service API and/or the corresponding WinRT APIs).

For the `BackOffEnabled` and `ControlMode` settings, the value in modem DSI messages will take precedence. If a modem DSI message passes through the WWAN service, the values of these two settings will be saved and will be used next time they are needed, regardless what values the registry settings for those are. If the `BackOffEnabled` and `ControlMode` settings in registry contain `0xFFFFFFFF` (no change) and no modem DSI message ever passes through, the WWAN service will use the value currently in the modem. The WWAN service queries the modem at start to obtain and remember the values in the modem.

| Value name                                 | Type                        | Data                                                                               |
|:-------------------------------------------|:----------------------------|:-----------------------------------------------------------------------------------|
| SARMappingTableEnabled                     | DWORD                       | `0` - SAR mapping table is disabled. <br/> `1` - SAR mapping table is enabled. <br/> If the data is absent or invalid, the default value of `0` is applied.                                                                                             |
| BackoffEnabled                             | DWORD                       | `0` - SAR back-off is disabled <br/> `1` - SAR-backoff is enabled. <br/> `0xFFFFFFFF` – modem should retain its current back-off state. <br/> If the data is absent or invalid, the default value of `0xFFFFFFFF` is applied.                           |
| ControlMode                                | DWORD                       | `0` - SAR back-off mechanism is controlled by the modem device directly. <br/> `1` - SAR-backoff mechanism is controlled and managed by the operating system. <br/> `0xFFFFFFFF` – modem should retain its current control mode. <br/> If the data is absent or invalid, the default value of `0xFFFFFFFF` is applied.                                                                                                |
| ConfigurationVersion                       | DWORD                       | This registry value is designed for OEM run-time components to inform Windows that the SAR mapping table and other parameters are updated. An OEM run-time component must increment the `ConfigurationVersion` registry value every time it completes updating the SAR mapping table, or other parameters in the registry.<br/> If the data is absent or invalid, the run-time component will not configure any SAR registry settings.                                                                                                                                                       |
