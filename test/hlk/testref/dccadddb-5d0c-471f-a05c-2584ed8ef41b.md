---
title: DE OOBE_EOW Sequence Tests
description: DE OOBE\_EOW Sequence Tests
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b7567c09-e039-41a9-818d-feb98f6b0451


ms.date: 11/05/2018
ms.topic: article


---

# DE OOBE_EOW Sequence Tests


This test verifies that Encryption On Write (EOW) of the volumes is started after completion of OOBE. It also tests if Device Encryption is not blocked by the OEM by setting registry key PreventDeviceEncryption.

## Test details

|||
|---|---|
| **Specifications**  | <ul><li>System.Fundamentals.TPM.CS.ConnectedStandby</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (x86)</li><li>Windows 10, client editions (x64)</li><li>Windows 10, client editions (ARM64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 15 |
|**Category**| Scenario |
|**Timeout (in minutes)**| 900 |
|**Requires reboot**| false |
|**Requires special configuration**| false |
|**Type**| automatic |



## <span id="Additional_documentation"></span><span id="additional_documentation"></span><span id="ADDITIONAL_DOCUMENTATION"></span>Additional documentation


Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s):

-   [System.Fundamentals additional documentation](system-fundamentals-additional-documentation.md)

## <span id="Running_the_test"></span><span id="running_the_test"></span><span id="RUNNING_THE_TEST"></span>Running the test


Before you run the test, complete the test setup as described in the test requirements: [WDTF System Fundamentals Testing Prerequisites](wdtf-system-fundamentals-testing-prerequisites.md).

Secure boot should be enabled.

This test returns Pass or Fail.

## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures](../user/troubleshooting-windows-hlk-test-failures.md).

For troubleshooting information, see [Troubleshooting System Fundamentals Testing](troubleshooting-system-fundamentals-testing.md).

If this test fails, review the test log from Windows Hardware Lab Kit (Windows HLK) Studio.

1.  Check test output directly from command prompt when the test runs or open te.wtl in the HLK Manager.

2.  If a test script fails, check the BitLocker status:

    -   Manage-bde -status \[volume\]

3.  Collect BitLocker event logs from event viewer at two locations:

    -   Filter \\Windows logs\\System logs by event sources started with BitLocker

    -   Applications and Services Logs\\Microsoft\\Windows\\BitLocker-API\\Management

4.  Check TCG logs

    -   Collect TCG log (\*.txt).

    -   Compare multiple copies of the TCG log and see whether PCR \[7, 11\] are consistent across reboot and hibernate.

    -   Make sure WHLK tests with TPM in the name pass.










