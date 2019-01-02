---
title: Interfaces
description: Interfaces
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d986953c-cadf-4c6e-a204-12a29e0b672e
ms.mktglfcycl: operate
ms.sitesec: msdn

ms.date: 05/05/2017
ms.topic: article


---

# Interfaces


This section documents the interfaces that the WPRControl API provides.

## In This Section

|Function|Description|
|--|--|
|[IControlErrorInfo](icontrolerrorinfo.md) |Provides functions that obtain information about errors that occur when the control manager performs an operation. |
| [IControlManager](icontrolmanager.md)| Represents the Windows Performance Recorder (WPR) manager, which controls ETW sessions.|
|[IControlProgressHandler](icontrolprogresshandler.md) |Represents a client-side handler that receives updates when the library performs an operation. |
| [IEnumControlWarningInfo](ienumcontrolwarninginfo.md)| Provides a standard COM enumeration method for enumerating a collection of [IControlErrorInfo](icontrolerrorinfo.md)" interfaces.|
| [IEnumProfile](ienumprofile.md)| Provides a standard COM enumeration method for enumerating a collection of [IProfile](iprofile.md) interfaces.|
| [IOnOffTransitionManager](ionofftransitionmanager.md)| Enables the client to store the profiles of the [IProfileCollection](iprofilecollection.md)" to the registry for boot tracing.|
| [IProfile](iprofile.md)| Represents an individual profile that the client controls.|
| [IProfileCollection](iprofilecollection.md)| Represents a collection of profiles that the library runs as a unit.|
| [ISnapshotManager3](isnapshotmanager3.md)| Represents a snapshot object that the client controls to enable, disable, and take the snapshot.|
| [ITraceMergeProperties](itracemergeproperties.md)| Enables the client to specify policies for merging multiple event trace log (ETL) files using XML.|
| [ITraceMergeTextHandler](itracemergetexthandler.md)| Obtains the text and other metadata that was added by the user.|

## Related topics


[WPRControl API Reference](wprcontrol-api-reference.md)

 

 







