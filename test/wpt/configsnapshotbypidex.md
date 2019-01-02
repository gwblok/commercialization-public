---
title: ConfigSnapshotByPIDEx 
description: ConfigSnapshotByPIDEx

ms.date: 11/15/2018
ms.topic: article
---

## ConfigSnapshotByPIDEx

Configures snapshot using the provided process id. 

## Syntax

```
HRESULT ConfigSnapshotByPIDEx
([in] SnapshotType snapshotType,
[in, out] ULONG* pids,
[in, out] HRESULT* pResults,
[in] ULONG cPids,
[in] VARIANT_BOOL fEnable);
```

## Parameters

*snapshotType* <br/>
[in] SnapshotType. <br/>
**Note** : Currently only available SnapshotType is SnapshotType_Heap <br/>
*pids* <br/>
[in] The pointer to an array of process ids. <br/>
*pResults* <br/>
[in, out] The user allocated buffer which will contain the snapshot configuration hresult code for each specified process id, the array passed in second parameter. <br/>
*cPids* <br/>
[in] The number of process ids in the array. <br/>
*fEnable* <br/>
[in] A Boolean value that indicate whether to enable or disable the snapshot.<br/>


## Return Value

The following table describes possible return values.

| Return Value | Description |
|--------------|-------------|
| S_OK | The configuration was successful for the specified processes. |
| S_FALSE |	The configuration was partially successful. Refer to pResults to further investigate which process failed.|
| E_WPRC_FAILED_TO_CONFIGURE_HEAP_SNAPSHOT_PIDS	| Failed to configure the heap stack control of PID(s). |

## Remarks

When the function returns at least a partial failure (S_FALSE), each element of pResults shows the configuration result of corresponding process id passed in the second parameter. 

For example, if you pass 3 pids, the pResults array will show the configuration result of each pid as shown below. 

|  ||||
|-----------|-------|-------|------|
|Pids [in]	|0x1086	|0x98004|0x12004|
|pResults [out]	|S_OK| E_INVALIDARG	|S_OK |


The snapshot configuration is valid until it is explicitly disabled or the process exits. 


## Related Topics

* [ISnapshotManager3](isnapshotmanager3.md)
* [ConfigSnapshotByPIDEx](configsnapshotbypid.md)
* [ConfigSnapshotByProcess](configsnapshotbyprocess.md)
* [ConfigSnapshotByProcessEx](configsnapshotbyprocessex.md)
* [DisablePeriodicSnapshot](disableperiodicsnapshot.md)
* [EnablePeriodicSnapshot](enableperiodicsnapshot.md)
* [SnapshotOnDemand](snapshotondemand.md)
* [VerifySnapshotSupported](verifysnapshotsupported.md)