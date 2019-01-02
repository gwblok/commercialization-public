---
title: MPEG2 Stress test 303
description: MPEG2 Stress test 303
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 657a4887-340d-4266-9d7c-4ce81b8e9c89


ms.date: 11/05/2018
ms.topic: article


---

# <span id="p_hlk_test.da4d8eca-1e52-4ae4-b0a4-06bffdcbb526"></span>MPEG2 Stress test 303

> [!IMPORTANT]
> 
> This test requires supplemental content. You can find this content in the 'Windows HLK supplemental test content' section at the following location:

-   <http://go.microsoft.com/fwlink/p/?LinkId=532718>



MPEG2 Stress DXVA Test: InputType MPEG2 - Verify DXVA Decoding for MPEG2

## Test details

|||
|---|---|
| **Specifications**  | <ul><li>Device.Graphics.WDDM12.Render.D3D11VideoDecoding</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (x86)</li><li>Windows 10, client editions (x64)</li><li>Windows 10, client editions (ARM64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 120 |
|**Category**| Development |
|**Timeout (in minutes)**| 120 |
|**Requires reboot**| false |
|**Requires special configuration**| false |
|**Type**| automatic |



## <span id="Additional_documentation"></span><span id="additional_documentation"></span><span id="ADDITIONAL_DOCUMENTATION"></span>Additional documentation


Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s):

-   [Device.Graphics additional documentation](device-graphics-additional-documentation.md)

## <span id="More_information"></span><span id="more_information"></span><span id="MORE_INFORMATION"></span>More information


### <span id="Parameters"></span><span id="parameters"></span><span id="PARAMETERS"></span>Parameters

| Parameter name    | Parameter description                                                                                                               |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| **ContentSource** | Path to source File                                                                                                                 |
| **GUID**          | The GUID of the DXVA Decoder to test - {DETECT} should be used for certification, this can be overridden to test a specific decoder |



## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures](../user/troubleshooting-windows-hlk-test-failures.md).










