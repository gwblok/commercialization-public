---
title: NDISTest 6.5 - \2 Machine\ - Stats
description: NDISTest 6.5 - \ 2 Machine\ - Stats
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: dc816554-cfb8-4408-b68b-b2f1831231c9


ms.date: 11/05/2018
ms.topic: article


---

# NDISTest 6.5 - \[2 Machine\] - Stats


For NDIS 6.0 miniports, this test verifies that miniport maintains and report statistics from OID\_GEN\_STATISTICS correctly. The test also verifies that the miniport correctly supports statistics OIDs OID\_GEN\_RCV\_OK OID\_GEN\_RCV\_NO\_BUFFER OID\_GEN\_RCV\_ERROR. It sends a bunch of packets to the test adapter and checks that the statistics get incremented. It expects the OID\_GEN\_RCV\_NO\_BUFFER to incremented exactly by the number of packets that were dropped.

## Test details

|||
|---|---|
| **Specifications**  | <ul><li>Device.Network.LAN.Base.NDISRequirements</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (x86)</li><li>Windows 10, client editions (x64)</li><li>Windows Server 2016 (x64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 10 |
|**Category**| Development |
|**Timeout (in minutes)**| 600 |
|**Requires reboot**| false |
|**Requires special configuration**| false |
|**Type**| automatic |



## <span id="Additional_documentation"></span><span id="additional_documentation"></span><span id="ADDITIONAL_DOCUMENTATION"></span>Additional documentation


Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s):

-   [Device.Network additional documentation](device-network-additional-documentation.md)

## <span id="Running_the_test"></span><span id="running_the_test"></span><span id="RUNNING_THE_TEST"></span>Running the test


Before you run the test, complete the test setup as described in the test requirements: [LAN Testing Prerequisites](lan-testing-prerequisites.md).

## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures](../user/troubleshooting-windows-hlk-test-failures.md).

For troubleshooting information, see [Troubleshooting LAN Testing](troubleshooting-lan-testing.md).

## <span id="More_information"></span><span id="more_information"></span><span id="MORE_INFORMATION"></span>More information


### <span id="Parameters"></span><span id="parameters"></span><span id="PARAMETERS"></span>Parameters

| Parameter name              | Parameter description                    |
|-----------------------------|------------------------------------------|
| **queryTestDeviceID**       |                                          |
| **SupportDeviceGuid0**      |                                          |
| **ClientMessageDeviceGuid** |                                          |
| **ServerMessageDeviceGuid** |                                          |
| **TestScript**              | comma separated list of test jobs to run |












