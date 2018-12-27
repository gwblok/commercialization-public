---
title: ConfigSnapshotByPID 
description: ConfigSnapshotByPID

ms.date: 11/15/2018
ms.topic: article
---

## ConfigSnapshotByPID
Configures snapshot using the provided process id. 

## Syntax

```
HRESULT ConfigSnapshotByPID
([in, out] ULONG* pids,
 [in] ULONG cPids,
[in] VARIANT_BOOL fEnable);
```

## Parameters

*pids* <br/>
[in] The pointer to an array of process ids. <br/>
*cPids* <br/>
[in] The number of process ids in the array. <br/>
*fEnable* <br/>
[in] A Boolean value that indicate whether to enable or disable the snapshot.


## Return Value
The following table describes possible return values.

| Return Value | Description |
|--------------|-------------|
| S_OK	| The configuration was successful for the specified processes. |
| S_FALSE | The configuration was partially successful. Refer to **pResults** to further investigate which process failed.|
| E_WPRC_FAILED_TO_CONFIGURE_HEAP_SNAPSHOT_PIDS	 | Failed to configure the heap stack control of PID(s).|


## Remarks

When the function returns a partial failure (S_FALSE), that means not all processes in the process id array are configured successfully. In order to find what process(es) failed, use the [ConfigSnapshotByPIDEx](configsnapshotbypidex.md) function.

The snapshot configuration is valid until it is explicitly disabled or the process exits. 

## Related Topics

* [ISnapshotManager3](isnapshotmanager3.md)
* [ConfigSnapshotByPIDEx](configsnapshotbypidex.md)
* [ConfigSnapshotByProcess](configsnapshotbyprocess.md)
* [ConfigSnapshotByProcessEx](configsnapshotbyprocessex.md)
* [DisablePeriodicSnapshot](disableperiodicsnapshot.md)
* [EnablePeriodicSnapshot](enableperiodicsnapshot.md)
* [SnapshotOnDemand](snapshotondemand.md)
* [VerifySnapshotSupported](verifysnapshotsupported.md)