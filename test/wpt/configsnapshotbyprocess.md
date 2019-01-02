---
title: ConfigSnapshotByProcess 
description: ConfigSnapshotByProcess

ms.date: 11/15/2018
ms.topic: article
---

## ConfigSnapshotByProcess

Configures snapshot using the provided process name. This function uses Image File Execution Options(IFEO) to set snapshot tracing flag in the registry. 

## Syntax
```
HRESULT ConfigSnapshotByProcess
([in] BSTR bstrProcName,
 [in] VARIANT_BOOL fEnable);
```

## Parameters

*bstrProcName* <br/>
[in] A string that contains the process name. <br/>
*fEnable* <br/>
[in] A Boolean value that indicate whether to enable or disable the snapshot. <br/>

## Return Value
The following table describes possible return values.

|Return Value | Description|
|-------------|------------|
|S_OK	| The configuration was successful for the specified process, otherwise an error code. |

## Remarks
This function is useful to configure the snapshot with the process name. Once enabled, the config will apply to all new instances of the process with specified name. The user should disable snapshot when the testing has finished. 

## Related Topics

* [ISnapshotManager3](isnapshotmanager3.md)
* [ConfigSnapshotByPID](configsnapshotbypid.md)
* [ConfigSnapshotByPIDEx](configsnapshotbypidex.md)
* [ConfigSnapshotByProcessEx](configsnapshotbyprocessex.md)
* [DisablePeriodicSnapshot](disableperiodicsnapshot.md)
* [EnablePeriodicSnapshot](enableperiodicsnapshot.md)
* [SnapshotOnDemand](snapshotondemand.md)
* [VerifySnapshotSupported](verifysnapshotsupported.md)