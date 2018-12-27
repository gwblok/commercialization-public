---
title: Diagnostics
description: Diagnostics
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: abe9889c-5b3e-4b60-9667-b7afc9957634
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Diagnostics

`Diagnostics` specifies whether installation statistics, such as status reports and failures, are sent to Microsoft.

## Child Elements

| Setting                 | Description                                                                           |
|:------------------------|:--------------------------------------------------------------------------------------|
| [OptIn](microsoft-windows-setup-diagnostics-optin.md) | Specifies whether to send installation statistic information to Microsoft. |

## Valid Configuration Passes

windowsPE

## Parent Hierarchy

[Microsoft-Windows-Setup](microsoft-windows-setup.md) | **Diagnostics**

## Applies To

For the list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Setup](microsoft-windows-setup.md).

## XML Example

The following XML output shows how to change this setting so that no information is sent.

```XML
<Diagnostics>
   <OptIn>false</OptIn>
</Diagnostics>
```

## Related topics

[Microsoft-Windows-Setup](microsoft-windows-setup.md)
