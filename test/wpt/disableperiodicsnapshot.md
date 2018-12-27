---
title: DisablePeriodicSnapshot 
description: DisablePeriodicSnapshot

ms.date: 11/15/2018
ms.topic: article
---

# DisablePeriodicSnapshot

Disables periodic snapshot of SnapshotType.

## Syntax

```
HRESULT DisablePeriodicSnapshot
([in] SnapshotType snapshotType);
```

## Parameters

*snapshotType* <br/>
[in] SnapshotType. <br/>
Note : Currently the only available SnapshotType is SnapshotType_Heap. 

<br/>

## Return Value

|Return Value | Description|
|-------------|------------|
|S_OK	| The configuration was successful for the specified process, otherwise an error code. |

## Related Topics

* [ISnapshotManager3](isnapshotmanager3.md)
* [ConfigSnapshotByPID](configsnapshotbypid.md)
* [ConfigSnapshotByPIDEx](configsnapshotbypidex.md)
* [ConfigSnapshotByProcess](configsnapshotbyprocess.md)
* [ConfigSnapshotByProcessEx](configsnapshotbyprocessex.md)
* [EnablePeriodicSnapshot](enableperiodicsnapshot.md)
* [SnapshotOnDemand](snapshotondemand.md)
* [VerifySnapshotSupported](verifysnapshotsupported.md)