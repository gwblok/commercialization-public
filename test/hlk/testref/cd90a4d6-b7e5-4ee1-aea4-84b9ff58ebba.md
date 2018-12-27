---
title: Mobile Print - Rendering Tests (Device Processed)
description: Mobile Print - Rendering Tests (Device Processed)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4addd258-39ba-45bb-b52b-43a1925abbdc


ms.date: 10/11/2018
ms.topic: article


---

# <span id="p_hlk_test.cd90a4d6-b7e5-4ee1-aea4-84b9ff58ebba"></span>Mobile Print - Rendering Tests (Device Processed)


The Mobile Print Rendering Tests test printing to PWG-Raster, PCLm, XPS, and OXPS compatible printers. The tests produce numerous pages of output at different DPI sizes, page sizes, page orientations, page orderings, and color formats suported by the printer (as defined by the PrintDeviceCapabilities).

## Test details

|||
|---|---|
| **Specifications**  | <ul><li>Device.Imaging.Printer.Mobile.PDL</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (x86)</li><li>Windows 10, client editions (x64)</li><li>Windows Server 2016 (x64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 10 |
|**Category**| Compatibility |
|**Timeout (in minutes)**| 30 |
|**Requires reboot**| false |
|**Requires special configuration**| false |
|**Type**| manual |



## <span id="Additional_documentation"></span><span id="additional_documentation"></span><span id="ADDITIONAL_DOCUMENTATION"></span>Additional documentation


Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s):

-   [Device.Imaging additional documentation](device-imaging-additional-documentation.md)

## <span id="More_information"></span><span id="more_information"></span><span id="MORE_INFORMATION"></span>More information


### <span id="Parameters"></span><span id="parameters"></span><span id="PARAMETERS"></span>Parameters

| Parameter name       | Parameter description   |
|----------------------|-------------------------|
| **WDKWSDServiceURL** | WSD Printer Service URL |
| **WDKWSDServiceID**  | WSD Printer Service Id  |
| **WDKWSDDeviceID**   | WSD Printer Device Id   |



## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures](../user/troubleshooting-windows-hlk-test-failures.md).










