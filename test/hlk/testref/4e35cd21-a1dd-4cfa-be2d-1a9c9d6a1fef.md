---
title: USB Device Connection S3+S4+Connected Standby
description: USB Device Connection S3+S4+Connected Standby
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ce83822f-7664-438d-985a-e4d429d6872c


ms.date: 11/05/2018
ms.topic: article


---

# <span id="p_hlk_test.4e35cd21-a1dd-4cfa-be2d-1a9c9d6a1fef"></span>USB Device Connection S3+S4+Connected Standby


This test verifies that a USB-based device becomes available within 500 milliseconds after the test system exits the S3 or S4 power state or connected standby. The test also confirms that there were not any errant device disconnects during system resume.

## Test details

|||
|---|---|
| **Specifications**  | <ul><li>Device.Connectivity.UsbDevices.DeviceAttachLessThan100ms</li><li>Device.Connectivity.UsbDevices.MustBeFunctionalAfterResume</li><li>Device.Connectivity.UsbDevices.MustResumeWithoutForcedReset</li><li>Device.Connectivity.UsbDevices.MustSignalAttachWithin500ms</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (x86)</li><li>Windows 10, client editions (x64)</li><li>Windows Server 2016 (x64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 10 |
|**Category**| Compatibility |
|**Timeout (in minutes)**| 15 |
|**Requires reboot**| false |
|**Requires special configuration**| false |
|**Type**| automatic |



## <span id="Additional_documentation"></span><span id="additional_documentation"></span><span id="ADDITIONAL_DOCUMENTATION"></span>Additional documentation


Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s):

-   [Device.Connectivity additional documentation](device-connectivity-additional-documentation.md)

## <span id="More_information"></span><span id="more_information"></span><span id="MORE_INFORMATION"></span>More information


### <span id="Parameters"></span><span id="parameters"></span><span id="PARAMETERS"></span>Parameters

| Parameter name  | Parameter description                   |
|-----------------|-----------------------------------------|
| **WDKDeviceID** | Device ID of the device under test      |
| **queryIsUsb3** | QueryIsUsb3 of device under test        |
| **DFUDevice**   | Uses DFU to reflash firmware on connect |



## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures](../user/troubleshooting-windows-hlk-test-failures.md).










