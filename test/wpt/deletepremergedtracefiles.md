---
title: DeletePreMergedTraceFiles
description: DeletePreMergedTraceFiles
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6c9424dd-6ec3-4835-af18-541cec28da76
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# DeletePreMergedTraceFiles

Indicates whether to delete premerged event trace log (ETL) files.

## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[TraceMergeProperties](tracemergeproperties.md)\>
    * \<[TraceMergeProperty](tracemergeproperty.md)\>
      * \<**DeletePreMergedTraceFiles**\>


## Syntax

```
<DeletePreMergedTraceFiles Value = boolean>
</DeletePreMergedTraceFiles>
```


## Attributes and Elements


### Attributes

| Attribute | Description                                      | Data type | Required | Default |
|:----------|:-------------------------------------------------|:----------|:---------|:--------|
| **Value** | Indicates whether to delete premerged ETL files. | boolean   | No       | true    |


### Child Elements

None.


### Parent Elements

| Element                                     | Description                                                                                 |
|:--------------------------------------------|:--------------------------------------------------------------------------------------------|
| [TraceMergeProperty](tracemergeproperty.md) | Contains configurations that are applied when recordings from multiple profiles are merged. |


## Related topics

[Elements](elements.md)

