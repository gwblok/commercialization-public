---
title: Win6_4.MB.GSM.Data.TestSlot
Description: Win6_4.MB.GSM.Data.TestSlot
ms.assetid: 


ms.date: 11/05/2018
ms.topic: article


---

# Win6_4.MB.GSM.Data.TestSlot

The test includes two parts: 1. Query modem slot information. 2. Query/set the mapping between modem slots and executors.

## Test details

|||
|---|---|
| **Specifications**  | <ul><li>Device.Network.MobileBroadband.GSM.Discretional</li><li>Device.Network.MobileBroadband.DSSA.Discretional</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (x86)</li><li>Windows 10, client editions (x64)</li><li>Windows 10, client editions (ARM64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 10 |
|**Category**| Development |
|**Timeout (in minutes)**| 10 |
|**Requires reboot**| false |
|**Requires special configuration**| true |
|**Type**| automatic |

## More Information
### Parameters

| Parameter Name | Parameter Description |
| --- | --- |
| **SlotMappingIndexList** | Executor to slot mapping: The slot with i-th index will be mapped to Executor i. Format: [index,index,...] Example: 1,0 which means Slot 1 will be mapped to Executor 0, Slot 0 will be mapped to Executor 1. |
| **SlotIndex** | Specifies the 0-based slot index whose information is requested |



## Additional Documentation
Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s): <ul><li>[Device.Network additional documentation](https:///docs.microsoft.com/en-us/windows-hardware/test/hlk/testref/device-network-additional-documentation.md)</li></ul>

## Troubleshooting
For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures.](https://docs.microsoft.com/en-us/windows-hardware/HLK/troubleshooting.html)