---
title: D3D12 - Resource Binding - Shader Resource Visibility
description: D3D12 - Resource Binding - Shader Resource Visibility
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e8d83bc0-3deb-4fd5-a186-9ca239d01bd5


ms.date: 11/05/2018
ms.topic: article


---

# <span id="p_hlk_test.7afeb58f-ab42-4015-b7ce-db5c4ddbce8f"></span>D3D12 - Resource Binding - Shader Resource Visibility


Test that different shader stages can use the same register binding but reference different descriptors through the root signature parameter Shader Visibility functionality. Test uses all 5 3D shader stages, each reading from SRV0 and writting to UAV1. The UAVs are then verified to hold unique data from each stage

## Test details

|||
|---|---|
| **Specifications**  | <ul><li>Device.Graphics.AdapterRender.D3D12Core.CoreRequirement</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (x86)</li><li>Windows 10, client editions (x64)</li><li>Windows Server 2016 (x64)</li><li>Windows 10, client editions (ARM64)</li><li>Windows 10, mobile edition (ARM)</li><li>Windows 10, mobile edition (ARM64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 2 |
|**Category**| Development |
|**Timeout (in minutes)**| 20 |
|**Requires reboot**| false |
|**Requires special configuration**| false |
|**Type**| automatic |



## <span id="Additional_documentation"></span><span id="additional_documentation"></span><span id="ADDITIONAL_DOCUMENTATION"></span>Additional documentation


Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s):

-   [Device.Graphics additional documentation](device-graphics-additional-documentation.md)

## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures](../user/troubleshooting-windows-hlk-test-failures.md).










