---
title: WLAN Association Tests - OPEN_WPA2_AES
description: WLAN Association Tests - OPEN\_WPA2\_AES
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 51290eda-acbe-4b75-852e-e8bc64c5d5b0


ms.date: 11/05/2018
ms.topic: article


---

# WLAN Association Tests - OPEN_WPA2_AES


This test suite validates WLAN associations.

## Test details

|||
|---|---|
| **Specifications**  | <ul><li>Device.Network.WLAN.SupportConnectionToWiFiAP.ConnectionToWiFiAP</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (x64)</li><li>Windows 10, client editions (x86)</li><li>Windows 10, client editions (ARM64)</li><li>Windows 10, mobile edition (ARM)</li><li>Windows 10, mobile edition (ARM64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 20 |
|**Category**| Scenario |
|**Timeout (in minutes)**| 1200 |
|**Requires reboot**| false |
|**Requires special configuration**| true |
|**Type**| automatic |



## <span id="Additional_documentation"></span><span id="additional_documentation"></span><span id="ADDITIONAL_DOCUMENTATION"></span>Additional documentation


Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s):

-   [Device.Network additional documentation](device-network-additional-documentation.md)

## <span id="Running_the_test"></span><span id="running_the_test"></span><span id="RUNNING_THE_TEST"></span>Running the test


Before you run the test, complete the test setup as described in the test requirements: [Wireless LAN (802.11) Testing Prerequisites](wireless-lan--80211--testing-prerequisites.md).

This test suite performs the following actions:

-   Configure two routers, that are named Router 0 and Router 1, as follows:
    -   Router 0 - 2.4Ghz : OPEN/NONE \[Preferred PHY G/Channel 1\]
    -   Router 0 - 5Ghz : WPA2PSK/AES \[Preferred PHY A/Channel 36\]
    -   Router 1 - 2.4Ghz : WPA2PSK/AES \[Preferred PHY G/Channel 11\]
    -   Router 1 - 5Ghz : WPA2PSK/AES \[Preferred N/Channel 36\]
-   Execute the BasicAssociation() test steps as described in WLAN Association Tests - Custom Configuration
-   Execute the AssociationPowerManagementSleep() test steps as described in [WLAN Association Tests - Custom Configuration](41e3400d-08da-424b-becd-fe3e8952bbca.md)
-   Execute the AssociationPowerManagementHibernate() test steps as described in [WLAN Association Tests - Custom Configuration](41e3400d-08da-424b-becd-fe3e8952bbca.md)

## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures](../user/troubleshooting-windows-hlk-test-failures.md).

For troubleshooting information, see [Troubleshooting Wireless LAN (802.11) Tests](troubleshooting-wireless-lan--80211--tests.md).

## <span id="More_information"></span><span id="more_information"></span><span id="MORE_INFORMATION"></span>More information


### <span id="Parameters"></span><span id="parameters"></span><span id="PARAMETERS"></span>Parameters

| Parameter name              | Parameter description                                                                    |
|-----------------------------|------------------------------------------------------------------------------------------|
| **TestDeviceSupports5ghz**  | This should be set to TRUE if the device supports 5ghz networks and FALSE if it does not |
| **APControllerIPAddress**   | Internal Parameter                                                                       |
| **LocalDir**                | Internal Parameter                                                                       |
| **AP1IPAddress**            | IP Address of the first AP connected to the system                                       |
| **AP1Password**             | Root password for the first AP connected to the system                                   |
| **AP2IPAddress**            | IP Address of the second AP connected to the system                                      |
| **AP2Password**             | Root password for the second AP connected to the system                                  |
| **ServiceAPChannelAddress** | Internal Parameter                                                                       |
| **TestDll**                 | Internal Parameter                                                                       |
| **Priority**                | Internal Parameter                                                                       |
| **TestName**                | Internal Parameter                                                                       |
| **EnableTracing**           | Yes or No to enable tracing                                                              |












