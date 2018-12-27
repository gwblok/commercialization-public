---
title: drvdelay
description: drvdelay
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: bddf3860-873b-470d-8f41-a678f48e04b5
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# drvdelay


This action produces a text report that summarizes the metrics regarding drivers.

```
-a drvdelay [-min [t]] [-name <driver>] [-range T1 T2]
```

## Options


<a href="" id="-min-t-"></a>**-min**<em>\[t\]</em>  
Show only delays longer than *n*, in microseconds.

<a href="" id="-name-driver-"></a>**-name**<em>&lt;driver&gt;</em>  
Show only delays by the specified driver.

<a href="" id="-ranget1-t2"></a>**-range***T1 T2*  
Show delays between *T1* and *T2*, in microseconds.

## Related topics


[Xperf Actions](xperf-actions.md)

[Time and Timestamp Formats](time-and-timestamp-formats.md)

 

 







