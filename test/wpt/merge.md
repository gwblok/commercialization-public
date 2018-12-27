---
title: merge
description: merge
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d450807c-ad86-4d1d-a089-0b3cfa86219c
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# merge


Displays trace merge options.

```
xperf -merge trace1.etl trace2.etl … merged.etl
```

## Example


The following example merges individual trace files into merged.etl and adds image identification information and event manifest information that is required for safe symbol decoding.

```
-merge trace1.etl trace2.etl … merged.etl
```

## Related topics


[Xperf Options](xperf-options.md)

 

 







