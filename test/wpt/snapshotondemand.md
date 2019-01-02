---
title: SnapshotOnDemand 
description: SnapshotOnDemand

ms.date: 11/15/2018
ms.topic: article
---

## SnapshotOnDemand

Takes one time snapshot for the given **SnapshotType** for the specified processes then exports to the trace buffers. The snapshot has to be configured before calling this API.

## Syntax

```
HRESULT SnapshotOnDemand
([in] SnapshotType snapshotType,
[in] ULONG* pids,
[in] ULONG cPids);
```


## Parameters

*snapshotType* <br/>
[in] SnapshotType. <br/>
**Note**: Currently only available [SnapshotType](snapshottype.md) is **SnapshotType_Heap**.  <br/>
*pids*  <br/>
[in] The pointer to an array of process ids. Up to 8 process ids can be specified.  <br/>
*cPids*  <br/>
[in] The number of process ids in the array. Maximum number is 8. <br/>

## Return Value

The following table describes possible return values.

|Return Value	| Description |
|---------------|-------------|
|S_OK	|The snapshot is successfully taken for the specified processes. |
| E_WPRC_EXCEEDED_HEAP_SNAPSHOT_PIDS |	The number of PIDs exceeded the maximum allowable limit. Up to 8 pids may be specified.|

## Related Topics

* [ISnapshotManager3](isnapshotmanager3.md)
* [ConfigSnapshotByPID](configsnapshotbypid.md)
* [ConfigSnapshotByPIDEx](configsnapshotbypidex.md)
* [ConfigSnapshotByProcess](configsnapshotbyprocess.md)
* [ConfigSnapshotByProcessEx](configsnapshotbyprocessex.md)
* [DisablePeriodicSnapshot](disableperiodicsnapshot.md)
* [EnablePeriodicSnapshot](enableperiodicsnapshot.md)
* [VerifySnapshotSupported](verifysnapshotsupported.md)