---
title: IgnoreCsComplianceCheck
description: Use to disable the default OS requirement of having non-rotational media in a Modern Standby system.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'


ms.date: 04/30/2018
ms.topic: article
ms.custom: RS5
---
# IgnoreCsComplianceCheck

Use to disable the default OS requirement of having non-rotational media in a Modern Standby system.

## Aliases and setting visibility

* **Windows Provisioning:** `IgnoreCsComplianceCheck`
* **Hidden setting:** Yes

## Values

| Value                 | Description                                    |
|:----------------------|:-----------------------------------------------|
| 1                     | Disable the check requiring non-rotational media in a Modern Standby system. |
| 0                     | Enable the check requiring non-rotational media in a Modern Standby system (default). |

## Remarks

Enabling Modern Standby on a system with rotational storage media is not recommended, as this may result in increased power consumption due to the tradeoff between power cycling and hard drive reliability. It may also result in higher exit latency upon resume from Modern Standby (compared to the latency with SSDs). Please refer to the [Modern Standby rotational storage guidelines](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/part-selection#rotational-storage) for more information.

## Applies to

Available in Windows 10, version 1803 and later versions of Windows.
