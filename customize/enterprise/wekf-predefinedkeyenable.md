---
title: WEKF\_PredefinedKey.Enable
description: WEKF\_PredefinedKey.Enable
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 4ea8c6c4-3bf6-475f-b9e1-38e1a971eda5


ms.date: 05/02/2017
ms.topic: article


---
# WEKF\_PredefinedKey.Enable

This method blocks the specified predefined key combination.

## Syntax

```powershell
[Static] uint32 Enable(
    [In] string PredefinedKey
);
```

## Parameters

<a href="" id="predefinedkey"></a>*PredefinedKey*
The predefined key combination to block. For a list of predefined keys, see [Predefined key combinations](predefined-key-combinations.md).

## Return Value

Returns an HRESULT value that indicates [WMI non-error constant](http://go.microsoft.com/fwlink/p/?LinkID=208318) or a [WMI error constant](http://go.microsoft.com/fwlink/p/?LinkID=208317).

## Requirements

| Windows Edition       | Supported |
|:----------------------|:----------|
| Windows 10 Home       | No        |
| Windows 10 Pro        | No        |
| Windows 10 Enterprise | Yes       |
| Windows 10 Education  | Yes       |

## Related topics

[WEKF\_PredefinedKey](wekf-predefinedkey.md)

[Keyboard Filter](keyboardfilter.md)
