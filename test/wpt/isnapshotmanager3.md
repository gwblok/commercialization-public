---
title: ISnapshotManager3
description: ISnapshotManager3

ms.date: 11/15/2018
ms.topic: article
---

# ISnapshotManager3

Represents a snapshot object that the client controls. The interface provides functions that enable, disables, and takes the snapshot.
 
## Syntax

```
[id(1), helpstring("EnablePeriodicSnapshot")] HRESULT EnablePeriodicSnapshot([in] SnapshotType snapshotType, [in] ULONG interval, [in] ULONG* pids, [in] ULONG cPids);
[id(2), helpstring("DisablePeriodicSnapshot")] HRESULT DisablePeriodicSnapshot([in] SnapshotType snapshotType);
[id(3), helpstring("SnapshotOnDemand")] HRESULT SnapshotOnDemand([in] SnapshotType snapshotType, [in] ULONG* pids, [in] ULONG cPids);
[id(4), helpstring("VerifySnapshotSupported")] HRESULT VerifySnapshotSupported([in] TRACEHANDLE traceHandle, [in, out] ULONG* frequencyInSeconds, [in, out] ULONG* cProviders);
[id(5), helpstring("ConfigSnapshotByPID")] HRESULT ConfigSnapshotByPID([in] ULONG* pids, [in] ULONG cPids, [in] VARIANT_BOOL fEnable);
[id(6), helpstring("ConfigSnapshotByProcess")] HRESULT ConfigSnapshotByProcess([in] BSTR bstrProcName, [in] VARIANT_BOOL fEnable);
[id(7), helpstring("ConfigSnapshotByPIDEx")] HRESULT ConfigSnapshotByPIDEx([in] SnapshotType snapshotType, [in] ULONG* pids, [in, out] HRESULT* pResults, [in] ULONG cPids, [in] VARIANT_BOOL fEnable);
[id(8), helpstring("ConfigSnapshotByProcessEx")] HRESULT ConfigSnapshotByProcessEx([in] SnapshotType snapshotType, [in] BSTR bstrProcName, [in] VARIANT_BOOL fEnable);
```

## Functions

The following table describes the functions that this interface provides.



|Function|Description|
|--|--|
| [ConfigSnapshotByPID](configsnapshotbypid.md)|Configures snapshot using the provided process id.|
|[ConfigSnapshotByPIDEx](configsnapshotbypidex.md)|Configures snapshot using the provided process id.|
|[ConfigSnapshotByProcess](configsnapshotbyprocess.md)|Configures snapshot using the provided process name.|
|[ConfigSnapshotByProcessEx](configsnapshotbyprocessex.md)|Configures snapshot using the provided process name.|
|[DisablePeriodicSnapshot](disableperiodicsnapshot.md)|Disables periodic snapshot.|
|[EnablePeriodicSnapshot](enableperiodicsnapshot.md)|Enables periodic snapshot with the given interval.|
|[SnapshotOnDemand](snapshotondemand.md)|Takes snapshot of Snapshot type and exports to the trace buffers.|
|[VerifySnapshotSupported](verifysnapshotsupported.md)|Queries periodic capture state limits.|

## Remarks

Most functions require administrator privileges.

## Related topics

* [Interfaces](interfaces-wprcontrol.md)