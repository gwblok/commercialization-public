---
title: UWF\_Filter.Enable
description: UWF\_Filter.Enable
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 12b8c976-c032-43f4-98d2-a237befd3ed5


ms.date: 05/02/2017
ms.topic: article


---
# UWF\_Filter.Enable

Enables Unified Write Filter (UWF) on the next restart.

## Syntax

```powershell
UInt32 Enable();
```

## Parameters

None.

## Return Value

Returns an HRESULT value that indicates [WMI status](http://go.microsoft.com/fwlink/p/?LinkID=208318) or a [WMI error](http://go.microsoft.com/fwlink/p/?LinkID=208317).

## Remarks

You must use an administrator account to enable UWF.

You must restart your device after you enable or disable UWF before the change takes effect.

The first time you enable UWF on your device, UWF makes the following changes to your system to improve the performance of UWF:

* Paging files are disabled.
* System restore is disabled.
* SuperFetch is disabled.
* File indexing service is turned off.
* Defragmentation service is turned off.
* Fast boot is disabled.
* BCD setting **bootstatuspolicy** is set to **ignoreallfailures**.

You can change these settings after you enable UWF if you want to. For example, you can move the page file location to an unprotected volume and re-enable paging files.

## Requirements

| Windows Edition       | Supported |
|:----------------------|:----------|
| Windows 10 Home       | No        |
| Windows 10 Pro        | No        |
| Windows 10 Enterprise | Yes       |
| Windows 10 Education  | Yes       |

## Related topics

[UWF\_Filter](uwf-filter.md)

[Unified Write Filter](unified-write-filter.md)
