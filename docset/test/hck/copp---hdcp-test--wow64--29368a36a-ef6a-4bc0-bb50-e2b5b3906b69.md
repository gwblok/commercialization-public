---
author: joshbax-msft
title: COPP - HDCP Test (WoW64) 2
description: COPP - HDCP Test (WoW64) 2
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8a23304d-4fee-46c0-aef0-09c0514e6d43
---

# COPP - HDCP Test (WoW64) 2


This automated test runs Certified Output Protection Protocol (COPP) commands to test display drivers for COPP compatibility.

There are three assertions for this test. The display driver must support:

-   COPP driver interfaces.

-   Content Generation Management System Analog (CGMS-A) and analog protection support (APS)

-   High-Bandwidth Digital Content Protection (HDCP).

The test attempts the COPP initialization protocol. If initialization fails, all of the assertions will fail. The tests will not actually verify each protection schema. They only query the driver for the availability.

This topic applies to the following test jobs:

-   COPP - HDCP Test

-   COPP - HDCP Test (WoW64)

-   COPP - Protocol Test

-   COPP - Protocol Test (WoW64)

## Test details


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Associated requirements</strong></p></td>
<td><p>Device.Graphics.WDDM.DisplayRender.OutputProtection Device.Graphics.WDDM.DisplayRender.OutputProtection.Windows7 Device.Graphics.WDDM11.DisplayRender.Base</p>
<p>[See the device hardware requirements.](http://go.microsoft.com/fwlink/p/?linkid=254483)</p></td>
</tr>
<tr class="even">
<td><p><strong>Platforms</strong></p></td>
<td><p>Windows 7 (x64) Windows 8 (x64) Windows Server 2012 (x64) Windows Server 2008 R2 (x64) Windows 8.1 x64 Windows Server 2012 R2</p></td>
</tr>
<tr class="odd">
<td><p><strong>Expected run time</strong></p></td>
<td><p>~10 minutes</p></td>
</tr>
<tr class="even">
<td><p><strong>Categories</strong></p></td>
<td><p>Certification</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type</strong></p></td>
<td><p>Automated</p></td>
</tr>
</tbody>
</table>

 

## Running the test


For information about requirements, see [Graphic Adapter or Chipset Testing Prerequisites](graphic-adapter-or-chipset-testing-prerequisites.md).

In addition, this test requires the following hardware and actions:

-   On Windows Vista and Windows 7, if the graphics card supports a digital connector (DVI or HDMI), you must connect and enable an HDCP-enabled monitor.

-   On Windows Vista, if the graphics card supports an analog connector (component, composite, or S-Video), you must connect and enable the connector.

## Troubleshooting


For troubleshooting information, see [Troubleshooting Device.Graphics Testing](troubleshooting-devicegraphics-testing.md).

## More information


### Command syntax

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Command option</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ShellRunner.exe -x basic -c COPP_ACPandCGMSA_Test.pro -l &quot;[WTTRunWorkingDir]\s98wtt_u.dll&quot;</strong></p></td>
<td><p>This command runs the COPP - ACP and CGMSA test job.</p></td>
</tr>
<tr class="even">
<td><p><strong>ShellRunner.exe -x basic -c COPP_ACPandCGMSA_Test.pro -l &quot;[WTTRunWorkingDir]\s98wtt_u.dll&quot;</strong></p></td>
<td><p>This command runs the COPP - ACP and CGMSA (WoW64) test job.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ShellRunner.exe -x basic -c COPP_HDCP_Test.pro -l &quot;[WTTRunWorkingDir]\s98wtt_u.dll&quot;</strong></p></td>
<td><p>This command runs the COPP - HDCP test job.</p></td>
</tr>
<tr class="even">
<td><p><strong>ShellRunner.exe -x basic -c COPP_HDCP_Test.pro -l &quot;[WTTRunWorkingDir]\s98wtt_u.dll</strong>&quot;</p></td>
<td><p>This command runs the COPP - HDCP (WoW64) test job.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ShellRunner.exe -x basic -c COPP_Protocol_Test.pro -l &quot;[WTTRunWorkingDir]\s98wtt_u.dll&quot;</strong></p></td>
<td><p>This command runs the COPP - Protocol test job.</p></td>
</tr>
<tr class="even">
<td><p><strong>ShellRunner.exe -x basic -c COPP_Protocol_Test.pro -l &quot;[WTTRunWorkingDir]\s98wtt_u.dll&quot;</strong></p></td>
<td><p>This command runs the COPP - Protocol (WoW64) test job.</p></td>
</tr>
</tbody>
</table>

 

**Note**  
For command line help for this test binary, type **/h**.

 

### File list

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>File</th>
<th>Location</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Configdisplay.exe</em></p></td>
<td><p><em>[WTT\TestBinRoot]\nttest\windowstest\tools\</em></p></td>
</tr>
<tr class="even">
<td><p><em>COPP_Protocol_Test.pro</em></p></td>
<td><p><em>[testbinroot]\nttest\multimediatest\streaming\</em></p></td>
</tr>
<tr class="odd">
<td><p><em>COPPTest.dll</em></p></td>
<td><p><em>[testbinroot]\nttest\multimediatest\streaming\</em></p></td>
</tr>
<tr class="even">
<td><p><em>s98wtt_u.dll</em></p></td>
<td><p><em>[testbinroot]\nttest\multimediatest\common\</em></p></td>
</tr>
<tr class="odd">
<td><p><em>shellrunner.exe</em></p></td>
<td><p><em>[testbinroot]\nttest\multimediatest\common\wdk\</em></p></td>
</tr>
<tr class="even">
<td><p><em>Smallboat.avi</em></p></td>
<td><p><em>[testbinroot]\nttest\multimediatest\streaming\</em></p></td>
</tr>
<tr class="odd">
<td><p><em>TDRWatch.exe</em></p></td>
<td><p><em>[WTT\TestBinRoot]\nttest\windowstest\graphics\</em></p></td>
</tr>
</tbody>
</table>

 

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bp_hck\p_hck%5D:%20COPP%20-%20HDCP%20Test%20%28WoW64%29%202%20%20RELEASE:%20%284/27/2016%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")



