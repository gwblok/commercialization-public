---
title: UIVerbosityLevel
description: Disables the Windows status messages during device startup, sign-in, and shut down.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: F866DD34-2A01-46BF-82B1-BFD5E43B2DFE
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 10/11/2017
ms.topic: article


---
# UIVerbosityLevel

Disables the Windows status messages during device startup, sign-in, and shut down.

## Values

| Value                     | Description                                                       |
|:--------------------------|:------------------------------------------------------------------|
| 0                         | Do not suppress the Windows status messages during device startup, sign-in, and shut down. <br/> This is the default value.       |
| 1                         | Suppress the Windows status messages during device startup, sign-in, and shut down. |

## Parent Hierarchy

[Microsoft-Windows-Embedded-EmbeddedLogon](microsoft-windows-embedded-embeddedlogon.md) | **UIVerbosityLevel**

## Valid Configuration Passes

offlineServicing

specialize

## Applies To

For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Embedded-EmbeddedLogon](microsoft-windows-embedded-embeddedlogon.md).

## XML Example

```XML
<settings pass="specialize">
    <component name="Microsoft-Windows-Embedded-EmbeddedLogon" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
      <UIVerbosityLevel>1</UIVerbosityLevel>
    </component>
</settings>
```
