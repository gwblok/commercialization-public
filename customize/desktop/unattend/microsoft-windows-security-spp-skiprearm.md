---
title: SkipRearm
description: SkipRearm
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: b004f48b-4947-49e7-9116-398fd917b087
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SkipRearm


`SkipRearm` specifies whether to reset the Windows licensing state when you generalize a computer.

Resetting the Windows licensing state means that all licensing and registry data related to activation is either removed or reset.

**Note**  
For most deployment scenarios, this setting is no longer needed. In Windows 8, the Windows licensing state can be reset repeatedly.

For more information, see [Work with Product Keys and Activation](http://go.microsoft.com/fwlink/?LinkId=206615).

 

## Using SkipRearm with the Windows Activation Timer


The activation grace period is typically 30 days. It begins after Windows Setup finishes and the computer boots for the first time.

While there is no limit to the number of times that the Sysprep command can run on a computer, in Windows 7 and Windows Vista, there is a limit to the number of times Windows can be rearmed. Typically, a system can be rearmed only 3 times. Using this setting enables you to run the Sysprep command multiple times without resetting the activation clock.

To ensure that an installation of an image receives the full activation grace period:

1.  Set `SkipRearm` to **1** while customizing your computer.

2.  Before running the **Sysprep** command the final time before deploying an image, rearm the computer by setting the `SkipRearm` setting to **0**. This resets the Activation grace-period timer.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>0</strong></p></td>
<td><p>Specifies that the Windows licensing state will be restored to the original, out-of-box licensing state, and that licensing settings are restored to their defaults.</p>
<p>This is the default value.</p></td>
</tr>
<tr class="even">
<td><p><strong>1</strong></p></td>
<td><p>Specifies that the Windows licensing state will not be changed.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


generalize

## Parent Hierarchy


[Microsoft-Windows-Security-SPP](microsoft-windows-security-spp.md) | **SkipRearm**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Security-SPP](microsoft-windows-security-spp.md).

## XML Example


The following example XML output specifies that the Windows licensing state will not be changed.

```
<SkipRearm>1</SkipRearm>
```

## Related topics


[Microsoft-Windows-Security-SPP](microsoft-windows-security-spp.md)

 

 







