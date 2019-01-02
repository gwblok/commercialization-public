---
title: GUID
description: GUID
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 8aea7928-13eb-44cc-a9c8-2316097814a0
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# GUID


`GUID` specifies the globally unique identifier (GUID) of an icon to appear in the notification area at the far right of the taskbar.

By setting the [Path](microsoft-windows-shell-setup-notificationarea-promotedicon2-path.md) and GUID elements of the PromotedIcon2 component, you can configure another icon to appear in the notification area. This icon will appear in place of the **Battery** icon.

To select the icon to be visible, you must:

-   Select a signed binary application file that includes a notification icon.

-   Set both the **Path** and **GUID** elements for the file.

The GUID for the icon is contained in the application. The NOTIFYICONDATA shell structure contains the guidItem. For more information, see the MSDN topic: [NOTIFYICONDATA](http://go.microsoft.com/fwlink/?LinkId=120340). For third-party applications, contact your application provider to see if your application uses this structure and to obtain the GUID.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>GUID</p></td>
<td><p>Specifies the GUID of an icon to appear in the notification area.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [NotificationArea](microsoft-windows-shell-setup-notificationarea.md) | [PromotedIcon2](microsoft-windows-shell-setup-notificationarea-promotedicon2.md) | **GUID**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).

## XML Example


The following XML output shows how to promote a new notification icon to appear in place of the **Battery** icon.

```
  <PromotedIcon2>
    <Path>%PROGRAMFILES%\Fabrikam\Application2.exe</Path>
    <GUID>{a1bc23cb-3456-bcde-abcd-feb363cacc88}</GUID>
  </PromotedIcon2>
```

## Related topics


[PromotedIcon2](microsoft-windows-shell-setup-notificationarea-promotedicon2.md)

[Path](microsoft-windows-shell-setup-notificationarea-promotedicon2-path.md)

 

 







