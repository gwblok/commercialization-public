---
title: PrintTicket Test
description: PrintTicket Test
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: e2312247-b001-4ffa-83c4-a4c92f5f47b2


ms.date: 11/05/2018
ms.topic: article


---

# <span id="p_hlk_test.59c36ef2-9ec8-494e-bbaa-8fed2dacd376"></span>PrintTicket Test


This automated test exercises the unmanaged **PrintTicket** and **PrintCapabilities** APIs that are part of Windows Vista and newer version of Windows.

If you have the Windows Driver Kit (WDK) test suite at the command line, the test tool sequentially runs the test cases that the TestSuite.xml file mentions. For the WDK test suite, the test cases call all of the native **PrintTicket** and **PrintCapabilities** APIs sequentially by using valid input parameters and expect valid output.

You can use this test to evaluate:

-   A driver's implementation of the **PrintTicket** and **PrintCapabilities** COM callable interface: **IPrintTicketProvider**.

-   A driver plugin's implementation of the **PrintTicket** and **PrintCapabilities** COM callable interface: **IPrintOEMPrintTicketProvider**.

-   A legacy driver's **PrintTicket** and **PrintCapabilities** shim layer. You can test the **PrintTicket** and **PrintCapabilities** API calls for legacy printers that do not support the **IPrintTicketProvider** interface.

## Test details
|||
|---|---|
| **Specifications**  | <ul><li>Device.Imaging.Printer.Base.printTicket</li><li>Device.Imaging.3DPrinter.Base.PrintTicket</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (x86)</li><li>Windows 10, client editions (x64)</li><li>Windows Server 2016 (x64)</li><li>Windows 10, client editions (ARM64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 2 |
|**Category**| Scenario |
|**Timeout (in minutes)**| 120 |
|**Requires reboot**| false |
|**Requires special configuration**| false |
|**Type**| automatic |

 

## <span id="Additional_documentation"></span><span id="additional_documentation"></span><span id="ADDITIONAL_DOCUMENTATION"></span>Additional documentation


Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s):

-   [Device.Imaging additional documentation](device-imaging-additional-documentation.md)

## <span id="Running_the_test"></span><span id="running_the_test"></span><span id="RUNNING_THE_TEST"></span>Running the test


Before you run the test, complete the test setup as described in the test requirements: [Printer Testing Prerequisites](printer-testing-prerequisites.md).

## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


For generic troubleshooting of HLK test failures, see <a href="https://docs.microsoft.com/en-us/windows-hardware/test/hlk/user/troubleshooting-windows-hlk-test-failures" >Troubleshooting Windows HLK Test Failures.</a>

For troubleshooting information, see [Troubleshooting Device.Imaging Testing](troubleshooting-deviceimaging-testing.md).

>[!WARNING]
>  
Any attempt to change the system default printer while the test is running might lead to inconsistent results.

 

## <span id="More_information"></span><span id="more_information"></span><span id="MORE_INFORMATION"></span>More information


### <span id="Parameters"></span><span id="parameters"></span><span id="PARAMETERS"></span>Parameters

| Parameter name         | Parameter description                    |
|------------------------|------------------------------------------|
| **LLU\_LAU**           | Logical Local User.                      |
| **LLU\_NetAccessOnly** | Logical Local User: Network Access only. |
| **TestExecutableName** | Test Executable name.                    |
| **WDKPrinterName**     | Printer name.                            |

