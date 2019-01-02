---
title: TimeZone
description: TimeZone
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d71a5a92-c3ab-4960-a117-a4e05698bd31
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# TimeZone


`TimeZone` specifies the time zone of the computer.

For a list of available time zones, use the `tzutil /l` command to view the available time zones in Windows 8. For more information, see [Tzutil Command-Line Options](http://go.microsoft.com/fwlink/?LinkId=247423).

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>Time_zone</em></p></td>
<td><p>Specifies the time zone of the computer. <em>Time_zone</em> is a string that has a maximum length of 256 characters.</p></td>
</tr>
</tbody>
</table>

 

If the time zone is not specified, Windows creates a default time zone value that is based on the installed language and region that are specified in an answer file.

If a region has more than one time zone, the default time zone for that region is specified by the location of a capital or a major city. For example, if en-AU is specified, `AUS Eastern Standard Time` is used as the default time zone because the Australian capital, Canberra, uses Australian Eastern Standard Time. If en-US is specified as the `UserLocale`, the time zone of the Windows installation defaults to `Pacific Standard Time`.

**Note**  
-   The time zones that are specified in Windows System Image Manager (Windows SIM) are not localized.

-   Greenwich Mean Time (GMT) is now known as Coordinated Universal Time (UTC).

 

## Valid Configuration Passes


auditSystem

oobeSystem

specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | **TimeZone**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following example shows how to set the time zone to China Standard Time (UTC+08:00).

```
<TimeZone>China Standard Time</TimeZone>
```

The following example shows how to set the time zone to Pacific Standard Time (UTC-08:00) without observing daylight savings time (UTC+01:00).

```
<TimeZone>Pacific Standard Time_dstoff</TimeZone>
```

## Related topics


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md)

[Tzutil Command-Line Options](http://go.microsoft.com/fwlink/?LinkId=247423)

 

 







