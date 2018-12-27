---
title: Thin Provisioning Threshold and Resource Exhaustion Test (LOGO)
description: Thin Provisioning Threshold and Resource Exhaustion Test (LOGO)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1e222537-4b7e-4a75-8b01-09cf49534f3c


ms.date: 11/05/2018
ms.topic: article


---

# <span id="p_hlk_test.ac970c9b-8d76-4cd6-bc8a-3efdd8ec6fb7"></span>Thin Provisioning Threshold and Resource Exhaustion Test (LOGO)


This test verifies that target devices with thin provisioning feature meet Windows requirements.

## Test details

|||
|---|---|
| **Specifications**  | <ul><li>Device.Storage.Hd.ThinProvisioning.BasicFunction</li></ul> |  
| **Platforms**   | <ul><li>Windows Server 2016 (x64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 300 |
|**Category**| Compatibility |
|**Timeout (in minutes)**| 18000 |
|**Requires reboot**| false |
|**Requires special configuration**| false |
|**Type**| automatic |



## <span id="Additional_documentation"></span><span id="additional_documentation"></span><span id="ADDITIONAL_DOCUMENTATION"></span>Additional documentation


Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s):

-   [Device.Storage additional documentation](device-storage-additional-documentation.md)

## <span id="Running_the_test"></span><span id="running_the_test"></span><span id="RUNNING_THE_TEST"></span>Running the test


Before you run the test, complete the test setup as described in the test requirements: [Hard Disk Drive Testing Prerequisites](hard-disk-drive-testing-prerequisites.md).

Before you run the test, please make sure the thin provisioned LUN to be online initialized raw dis. Also, you should set the threshold for the thin provisioned LUN to be 70 percent (default). If the threshold is fixed, you should specify that threshold when running the test.

## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures](../user/troubleshooting-windows-hlk-test-failures.md).

For troubleshooting information, see [Troubleshooting Device.Storage Testing](troubleshooting-devicestorage-testing.md).

## <span id="More_information"></span><span id="more_information"></span><span id="MORE_INFORMATION"></span>More information


The end to end scenario test would do threshold and resource exhaustion test. The main approach is to properly trigger the threshold notification/permanent resource exhaustion and check the sense key. When threshold is hit, we will get the log page to calculate whether the value to be at least no less than the value set for threshold. For temporary resource exhaustion, we just make this scenario to be optional, since some storage device may handle this scenario decently not to return any sense key.

### <span id="Command_syntax"></span><span id="command_syntax"></span><span id="COMMAND_SYNTAX"></span>Command syntax

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
<td><p><strong>Thinprovision.exe /scenario exhaustion /thindisk &quot;[TPDiskDeviceObjLink]&quot; /percent &quot;[TPDiskThresholdPercent]&quot; /logo</strong></p></td>
<td><p>Runs the test.</p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> 
> For command-line help for this test binary, type **/h**.



### <span id="File_list"></span><span id="file_list"></span><span id="FILE_LIST"></span>File list

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
<td><p>Thinprovision.exe</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\driverstest\storage\wdk\thinprovision&lt;/p&gt;</td>
</tr>
</tbody>
</table>



### <span id="Parameters"></span><span id="parameters"></span><span id="PARAMETERS"></span>Parameters

| Parameter name             | Parameter description                  |
|----------------------------|----------------------------------------|
| **WDKDeviceID**            |                                        |
| **TPDiskDeviceObjLink**    | The thin provisioned LUN               |
| **LLU\_NetAccessOnly**     |                                        |
| **LLU\_LclAdminUsr**       |                                        |
| **Destructive**            | (0,1) 0=Passive, 1=Destructive         |
| **TPDiskThresholdPercent** | The percentage of thin provisioned LUN |












