---
title: WDDM Scheduler Stress (AlwaysRepatch)
description: WDDM Scheduler Stress (AlwaysRepatch)
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 555f033a-db84-42c2-883b-3fc7dd76b64c


ms.date: 11/05/2018
ms.topic: article


---

# <span id="p_hlk_test.18c9ab8b-ee67-47c4-950c-20eafd9ffbdc"></span>WDDM Scheduler Stress (AlwaysRepatch)


This automated test verifies system stability while running many GPU-bound memory intensive applications when all patch locations are always repatched via the Patch DDI.

This test creates many processes that do D3D9 rendering with a large video memory working set. This causes preemption and paging to occur on the GPU. The test puts the operating system into a mode that causes it to repatch all patch locations via the Patch DDI. Display drivers must not cause the system to crash or stop responding (hang) while running this test.

## Test details

|||
|---|---|
| **Specifications**  | <ul><li>Device.Graphics.WDDM.DisplayRender.Base</li></ul> |  
| **Platforms**   | <ul><li>Windows 10, client editions (x86)</li><li>Windows 10, client editions (x64)</li><li>Windows Server 2016 (x64)</li><li>Windows 10, client editions (ARM64)</li></ul> |
| **Supported Releases** | <ul><li>Windows 10</li><li>Windows 10, version 1511</li><li>Windows 10, version 1607</li><li>Windows 10, version 1703</li><li>Windows 10, version 1709</li><li>Windows 10, version 1803</li><li>Next update to Windows 10</li></ul> |
|**Expected run time (in minutes)**| 30 |
|**Category**| Compatibility |
|**Timeout (in minutes)**| 1800 |
|**Requires reboot**| false |
|**Requires special configuration**| false |
|**Type**| automatic |



## <span id="Additional_documentation"></span><span id="additional_documentation"></span><span id="ADDITIONAL_DOCUMENTATION"></span>Additional documentation


Tests in this feature area might have additional documentation, including prerequisites, setup, and troubleshooting information, that can be found in the following topic(s):

-   [Device.Graphics additional documentation](device-graphics-additional-documentation.md)

## <span id="Running_the_test"></span><span id="running_the_test"></span><span id="RUNNING_THE_TEST"></span>Running the test


Before you run the test, complete the test setup as described in the test requirements: [Graphic Adapter or Chipset Testing Prerequisites](graphic-adapter-or-chipset-testing-prerequisites.md).

## <span id="Troubleshooting"></span><span id="troubleshooting"></span><span id="TROUBLESHOOTING"></span>Troubleshooting


For generic troubleshooting of HLK test failures, see [Troubleshooting Windows HLK Test Failures](../user/troubleshooting-windows-hlk-test-failures.md).

For troubleshooting information, see [Troubleshooting Device.Graphics Testing](troubleshooting-devicegraphics-testing.md).

## <span id="More_information"></span><span id="more_information"></span><span id="MORE_INFORMATION"></span>More information


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
<td><p><strong>Sch_Stress.exe</strong></p></td>
<td><p>Runs the test job.</p></td>
</tr>
</tbody>
</table>



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
<td><p>Configdisplay.exe</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\tools&lt;/p&gt;</td>
</tr>
<tr class="even">
<td><p>Sch_Stress.exe</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest&lt;/p&gt;</td>
</tr>
<tr class="odd">
<td><p>TDRWatch.exe</p></td>
<td><p><em>&lt;[testbinroot]&gt;</em>\nttest\windowstest\graphics&lt;/p&gt;</td>
</tr>
</tbody>
</table>



### <span id="Parameters"></span><span id="parameters"></span><span id="PARAMETERS"></span>Parameters

| Parameter name               | Parameter description                                |
|------------------------------|------------------------------------------------------|
| **LLU\_NetAccessOnly**       | Domain User who is local admin                       |
| **ConfigDisplayCommandLine** | Custom Command Line for ConfigDisplay. Default: logo |
| **TDRArgs**                  | /get or /set                                         |












