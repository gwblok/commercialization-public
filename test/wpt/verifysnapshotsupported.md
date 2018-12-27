---
title: VerifySnapshotSupported 
description: VerifySnapshotSupported

ms.date: 11/15/2018
ms.topic: article
---

## VerifySnapshotSupported

Queries event tracing session the periodic capture state limits. 

## Syntax

```
HRESULT VerifySnapshotSupported
([in] TRACEHANDLE traceHandle,
[in, out] ULONG* frequencyInSeconds,
  [in, out] ULONG cProviders);
  ```

## Parameters

*traceHandle* <br/>
[in] A handle of the event tracing session that wants to capture the specified information. The [StartTrace](https://docs.microsoft.com/en-us/windows/desktop/etw/starttrace) function returns this handle. <br/>
*frequencyInSeconds* <br/>
[in] The frequency of state captures in seconds.<br/>
*cProviders* <br/>
[in] The number of providers.<br/>

## Return Value
The following table describes possible return values.

|Return Value	| Description |
|---------------|-------------|
|S_OK	|The given frequency and providers are within limits.|
|E_WPRC_BELOW_FREQUENCY_THRESHOLD	|Frequency is below minimum threshold, increase frequency.|
|E_WPRC_EXCEEDED_PROVIDER_COUNT_LIMIT	|Provider count limit exceeded, reduce number of providers.|


## Related Topics

* [TRACE_PERIODIC_CAPTURE_STATE_INFO](https://docs.microsoft.com/en-us/windows/desktop/ETW/trace-periodic-capture-state-info)
* [ISnapshotManager3](isnapshotmanager3.md)
* [ConfigSnapshotByPID](configsnapshotbypid.md)
* [ConfigSnapshotByPIDEx](configsnapshotbypidex.md)
* [ConfigSnapshotByProcess](configsnapshotbyprocess.md)
* [ConfigSnapshotByProcessEx](configsnapshotbyprocessex.md)
* [DisablePeriodicSnapshot](disableperiodicsnapshot.md)
* [EnablePeriodicSnapshot](enableperiodicsnapshot.md)
* [SnapshotOnDemand](snapshotondemand.md)