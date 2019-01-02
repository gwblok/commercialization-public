---
title: DF - Sleep and PNP (disable and enable) with IO Before and After (Reliability)
description: DF - Sleep and PNP (disable and enable) with IO Before and After (Reliability)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 7b33a2dc-1b41-420e-a02f-b5de0b7a7e1d


ms.date: 11/05/2018
ms.topic: article


---

# <span id="p_hlk_test.6bd51c1b-3dad-4a5e-b46d-98c2fe91d1aa"></span>DF - Sleep and PNP (disable and enable) with IO Before and After (Reliability)


This test cycles the system through various sleep states and performs IO and basic PNP (disable/enable) on devices before and after each sleep state cycle.

## Test details

|||
|---|---|
| **Specifications**  | <ul><li>Device.DevFund.Reliability.BasicReliabilityAndPerformance</li><li>Device.DevFund.Reliability.S3S4SleepStates</li><li>Device.DevFund.DriverFramework.KMDF.Reliability</li><li>Device.DevFund.DriverFramework.UMDF.Reliability</li><li>Device.DevFund.ReliabilityDisk.IOCompletionCancellation</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (x86)</li><li>Windows 10, client editions (x64)</li><li>Windows Server 2016 (x64)</li><li>Windows 10, client editions (ARM64)</li><li>Windows 10, mobile edition (ARM)</li><li>Windows 10, mobile edition (ARM64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 45 |
|**Category**| Scenario |
|**Timeout (in minutes)**| 180 |
|**Requires reboot**| false |
|**Requires special configuration**| true |
|**Type**| automatic |



## <span id="Additional_documentation"></span><span id="additional_documentation"></span><span id="ADDITIONAL_DOCUMENTATION"></span>Additional documentation


Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s):

-   [Device.DevFund additional documentation](device-devfund-additional-documentation.md)

## <span id="More_information"></span><span id="more_information"></span><span id="MORE_INFORMATION"></span>More information


### <span id="Parameters"></span><span id="parameters"></span><span id="PARAMETERS"></span>Parameters

| Parameter name                               | Parameter description                                                                                                                                                                                                                       |
|----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **DQ**                                       | A WDTF SDEL query that is used to identify the target device(s) - http://go.microsoft.com/fwlink/?LinkId=232678                                                                                                                             |
| **Wpa2PskAesSsid**                           | Required ONLY if DUT or one of its child devices is a WiFi adapter. Please provide SSID of a WPA2 AES WiFi network that the test can use to test the WiFi adapter. The default is 'kitstestssid'.                                           |
| **Wpa2PskPassword**                          | Required ONLY if DUT or one of its child devices is a WiFi adapter. Please provide password of the WPA2 AES WiFi network specified using the Wpa2PskAesSsid parameter. The default is 'password'.                                           |
| **ResumeDelay**                              | Delay time in seconds after each sleep cycle                                                                                                                                                                                                |
| **WDTFREMOTESYSTEM**                         | Required ONLY if there is a wired NIC on the test system AND it does not have an IPv6 gateway address. If determined to be required, please provide an IPv6 address that the NIC can ping to test network I/O. Eg: fe80::78b6:810:9c12:46cd |
| **MultiDeviceHardwareIdSdelQueryHardwareID** | Multi Device SDEL                                                                                                                                                                                                                           |
| **MultiDeviceInstanceIdSdelWDKDeviceID**     | Device id of DUT                                                                                                                                                                                                                            |
| **TestCycles**                               | Number of test cycles                                                                                                                                                                                                                       |
| **IOPeriod**                                 | IO period in minutes                                                                                                                                                                                                                        |
| **DriverVerifierAdditionalDrivers**          | Additional drivers that should have Driver Verifier enabled                                                                                                                                                                                 |
| **DriverVerifierExcludedFlags**              | Placeholder for Driver Verifier flags that may be manually excluded for the test run                                                                                                                                                        |
| **DriverVerifierCustomizeConfiguration**     | Specifies that this test may want to automatically update Driver Verifier settings                                                                                                                                                          |



## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures](../user/troubleshooting-windows-hlk-test-failures.md).










