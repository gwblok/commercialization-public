---
title: Implementing Web Services on Devices for Printing
description: Information about web services that provide a connection protocol for printing and scanning peripherals. The Web Services technology provides a common framework for describing and sharing information.
ms.assetid: A7585276-FA63-4A5A-B1E9-549A1CD3FC05

ms.date: 04/29/2015
ms.topic: article


---

# Implementing Web Services on Devices for Printing


**Last updated:**

-   April 29, 2015

**Applies to:**

-   Windows Vista
-   Windows 7
-   Windows 8
-   Windows 8.1
-   Windows 10

Information about web services that provide a connection protocol for printing and scanning peripherals. The Web Services technology provides a common framework for describing and sharing information.

Windows Vista was the first Microsoft Windows operating system to provide Web Services on devices as a connection protocol for printing and scanning peripherals. Web Services technology provides a common framework for describing and sharing information. Web Services on devices, part of the Windows Rally program, describes a set of protocols for consuming and controlling services on network-connected devices.

Four Web Services specifications exist for printing and scanning, to help device manufacturers take advantage of the improved customer experience around connecting, installing, and using devices with Windows.

For Windows 8.1, the print service definition for web services on devices has been updated to v1.2.

For Windows 10, the print service definition for web services on devices has been updated to v2.0.

## <span id="Highlights_in_WS-Print_v2.0"></span><span id="highlights_in_ws-print_v2.0"></span><span id="HIGHLIGHTS_IN_WS-PRINT_V2.0"></span>Highlights in WS-Print v2.0


WS-Print V2.0 adds a number of new schema elements and operations that supplements the current WS-Print V1.0 service specification. The basic operation of a WS-Print V1.0 print device has not changed. The new operations and schema elements in WS-Print V2.0 allow a mobile client to print without the aid of a driver, and can be used to enhance the capabilities of a v4 print driver.

WS-Print v2.0 defines the following new operations:

-   **PrepareToPrint** – Informational operation which allows printers to warm up
-   **CreatePrintJob2** – Extension of CreatePrintJob which includes PrintSchema PrintTicket for job configuration
-   **GetPrintDeviceCapabilities** – Allows retrieval of a PrintDeviceCapabilities document
-   **GetPrintDeviceResources** – Allows retrieval of localized resources in ResX
-   **GetBidiSchemaExtensions** – Allows retrieval of Bidi Schema extensions

For more information, see Appendix E in the Print Service Definition v2.0 specification available in the WS-Print v2.0 file download below.

## <span id="Highlights_in_WS-Print_v1.2"></span><span id="highlights_in_ws-print_v1.2"></span><span id="HIGHLIGHTS_IN_WS-PRINT_V1.2"></span>Highlights in WS-Print v1.2


Web Services on Devices for printing (WS-Print) v1.2 adds a number of new schema elements to the current WS-Print V1.1 Service Specification.

WS-Print includes all operations and schema elements used in WS-Print V1.1, but adds support for a new schema element and a new operation. The new schema element “SupportsWSPrintV12” is used to identify support for WS-Print V1.2. The new operation, “SetPrinterElements” enables a client to set the value of a schema element on the printer. For example, the client could set a custom element called “InkHeadAlignmentValue” which the printer would use to realign the inkjet head.

In order to facilitate specification implementation and understanding, the specifications are also available here in complete, stand-alone form, along with their associated Web Services Description Languages (WSDLs) and XML Schema Definitions (XSDs). These four Web Services on devices specifications are covered by the included technical documentation license agreement, which references the WDK.

## <span id="File_downloads"></span><span id="file_downloads"></span><span id="FILE_DOWNLOADS"></span>File downloads


**Download the Specification and Supporting Files for WS-Print v2.0**

![](images/ic13605.gif) [Print Service Definition v2.0 for Web Services on Devices](http://go.microsoft.com/fwlink/p/?LinkId=534008)
(1.55 MB zip file containing Microsoft Word document and supporting files; April 29, 2015)
**Download the Specification and Supporting Files for WS-Print v1.2**

![](images/ic13605.gif) [Print Service Definition v1.2 for Web Services on Devices](http://download.microsoft.com/download/E/9/7/E974CFCB-4B3B-40CC-AF92-4F7F84477F0B/Printer.zip)

(2.64 MB zip file containing Microsoft Word document and supporting files; September 16, 2013)
**Download the Specifications and Supporting Files**

![](images/ic13605.gif) [Print Device Definition V1.0 for Web Services on Devices](http://download.microsoft.com/download/9/c/5/9c5b2167-8017-4bae-9fde-d599bac8184a/PrintDevice.exe)
(76 KB self-extracting file containing Microsoft Word document and supporting file; January 29, 2007)

![](images/ic13605.gif) [Scan Service Definition V1.0 for Web Services on Devices](http://download.microsoft.com/download/9/C/5/9C5B2167-8017-4BAE-9FDE-D599BAC8184A/ScanService.zip)

(1.5 MB self-extracting file containing Microsoft Word document and supporting files; February 9, 2012)

![](images/ic13605.gif) [Scan Device Definition V1.0 for Web Services on Devices](http://download.microsoft.com/download/9/c/5/9c5b2167-8017-4bae-9fde-d599bac8184a/ScanDevice.exe)
(76 KB self-extracting file containing Microsoft Word document and supporting file; January 29, 2007)
 




