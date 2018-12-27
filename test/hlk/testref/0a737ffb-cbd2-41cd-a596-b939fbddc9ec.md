---
title: Wlan Test - Connect to a WPA2 PSK AES AP with Sleep cycle - (WoW64 for ARM64)
description: Wlan Test - Connect to a WPA2 PSK AES AP with Sleep cycle - (WoW64 for ARM64)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8598ae3b-1731-4cbc-8c2f-3e2a1b31951d


ms.date: 11/05/2018
ms.topic: article


---

# <span id="p_hlk_test.0a737ffb-cbd2-41cd-a596-b939fbddc9ec"></span>Wlan Test - Connect to a WPA2 PSK AES AP with Sleep cycle - (WoW64 for ARM64)


Connect to a specified WPA2PSK AES network with sleep resume (Defaults: SSID=kitstestssid Passphrase=password SleepDurationInSec=20, SleepCycleIterations=2) - This test is a WoW64 for ARM64 version of test guid 2ae2cb26-ea04-4def-8e07-ae7b92e61e1b

## Test details

|||
|---|---|
| **Specifications**  | <ul><li>Device.Network.WLAN.SupportConnectionToAP.ConnectionToAP</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (ARM64)</li><li>Windows 10, mobile edition (ARM64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 5 |
|**Category**| Scenario |
|**Timeout (in minutes)**| 15 |
|**Requires reboot**| false |
|**Requires special configuration**| true |
|**Type**| automatic |



## <span id="Additional_documentation"></span><span id="additional_documentation"></span><span id="ADDITIONAL_DOCUMENTATION"></span>Additional documentation


Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s):

-   [Device.Network additional documentation](device-network-additional-documentation.md)

## <span id="More_information"></span><span id="more_information"></span><span id="MORE_INFORMATION"></span>More information


### <span id="Parameters"></span><span id="parameters"></span><span id="PARAMETERS"></span>Parameters

| Parameter name           | Parameter description                                                 |
|--------------------------|-----------------------------------------------------------------------|
| **EnableTracing**        | Enable Tracing                                                        |
| **WPA2\_PSK\_AES\_SSID** | SSID of a WPA2\_PSK\_AES network to connect to (MUST be WPA2 PSK AES) |
| **WPA2\_PSK\_Password**  | Password for WPA2\_PSK network                                        |
| **SleepDurationInSec**   | The amount of time in seconds the device will asleep                  |
| **SleepCycleIterations** | The number of sleep/wake cycles to do                                 |
| **queryTestDeviceID**    | Device id of device under test                                        |



## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures](../user/troubleshooting-windows-hlk-test-failures.md).










