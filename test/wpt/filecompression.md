---
title: FileCompression
description: FileCompression
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: fcc2cd71-7246-40f5-ba9c-2ba79b8ffdfc
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---


# FileCompression

Indicates whether the ETL file is compressed. This element is for internal use only.


## Element Hierarchy

* \<[WindowsPerformanceRecorder](windowsperformancerecorder.md)\>
  * \<[TraceMergeProperties](tracemergeproperties.md)\>
    * \<[TraceMergeProperty](tracemergeproperty.md)\>
      * \<**FileCompression**\>


## Syntax

```
<FileCompression = Value boolean>
```


## Attributes and Elements


### Attributes

| Attribute | Description                                   | Data type | Required | Default |
| :-------- | :-------------------------------------------- | :-------- | :------- | :------ |
| **Value** | Indicates whether the ETL file is compressed. | Boolean   | No       |         |


### Child Elements

None.


### Parent Elements

| Element                                     | Description                                                                                                                        |
| :------------------------------------------ | :--------------------------------------------------------------------------------------------------------------------------------- |
| [TraceMergeProperty](tracemergeproperty.md) | Contains configurations that are applied when recordings from multiple profiles are merged. This element is for internal use only. |


## Related topics

[Elements](elements.md)

