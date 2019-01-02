---
title: PrivacyAdvisorMode
description: PrivacyAdvisorMode
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: c9514954-0b31-4f4b-b70f-94f692f3f909
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# PrivacyAdvisorMode


`PrivacyAdvisorMode` specifies whether InPrivate Browsing and InPrivate Blocking are active in Internet Explorer, and when they provide alerts.

InPrivate Browsing prevents Internet Explorer from storing data about your browsing session. This includes cookies, temporary Internet files, history, and other data.

InPrivate Blocking helps prevent the websites you go to from automatically sharing details about your visit with other websites. To help protect your privacy, some website content may be blocked.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>0</p></td>
<td><p>InPrivate Blocking is off.</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>InPrivate Blocking is set to Manually Block. Individual websites to be blocked must be added to the list manually.</p></td>
</tr>
<tr class="odd">
<td><p>2</p></td>
<td><p>InPrivate Blocking is set to Automatic.</p>
<p>This is the default value.</p></td>
</tr>
</tbody>
</table>

 

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md) | **PrivacyAdvisorMode**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md).

## XML Example


The following XML output shows how to configure Internet Explorer to turn off InPrivate Blocking and InPrivate Browsing.

```
<PrivacyAdvisorMode>0</PrivacyAdvisorMode>
```

## Related topics


[Microsoft-Windows-IE-InternetExplorer](microsoft-windows-ie-internetexplorer.md)

 

 







