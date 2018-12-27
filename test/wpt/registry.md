---
title: registry
description: registry
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 522285e9-49ec-42b6-bc7d-f90e473ccc70
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# registry


This action produces a text file that summarizes metrics related to registry accesses and changes.

```
-a registry [-counts [n]] [-tree] [-unknown] [-range T1 T2]
```

## Options


<a href="" id="-counts-n-"></a>**-counts**<em>\[n\]</em>  
Prints registry access statistics for *n* use intervals. The default is 1.

<a href="" id="-tree"></a>**-tree**  

<a href="" id="-unknown"></a>**-unknown**  

<a href="" id="-ranget1-t2"></a>**-range***T1 T2*  
Shows delays between *T1* and *T2*, in microseconds.

## Related topics


[Xperf Actions](xperf-actions.md)

[Time and Timestamp Formats](time-and-timestamp-formats.md)

 

 







