---
title: OEMAppID
description: OEMAppID
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3746c858-bdc2-48a7-9ace-8a7ad169471e
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# OEMAppID


`OEMAppID` enables the OEM to specify app information. If the OEM uses this setting, all information entered by the user in the OEM registration screen is written to a location in the user's profile that can be accessed by the OEM app.

## Values


The `OEMAppID` setting must be a string.

## Valid Configuration Passes


oobeSystem

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OOBE](microsoft-windows-shell-setup-oobe.md) | **OEMAppID**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML example shows how to use the `OEMAppID` setting.

```
<OOBE>
   <OEMAppID>winstore_abc123def!Windows.Store</OEMAppID>
</OOBE>
```

## Related topics


[OOBE](microsoft-windows-shell-setup-oobe.md)

 

 







