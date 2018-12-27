---
title: ArchiveFolderName
description: ArchiveFolderName
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 07c9f389-33cc-4a90-87c1-8b5235436e88
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# ArchiveFolderName


`ArchiveFolderName` specifies the folder to which the fax service saves copies of all incoming and outgoing faxes.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>ArchiveFolderName</em></p></td>
<td><p>Specifies the folder name to which copies of incoming and outgoing faxes are saved. The default value is <strong>D:\Program Data\Microsoft\Windows NT\MSFax</strong>. <em>ArchiveFolderName</em> is a string with a maximum length of 259 characters.</p></td>
</tr>
</tbody>
</table>

 

This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


specialize

## Parent Hierarchy


[Microsoft-Windows-Fax-Service](microsoft-windows-fax-service.md) | [Fax](microsoft-windows-fax-service-fax.md) | **ArchiveFolderName**

## Applies To


For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Fax-Service](microsoft-windows-fax-service.md).

## XML Example


The following XML output shows how to set fax settings.

```
<Fax>
   <ArchiveFaxes>false</ArchiveFaxes>
   <IncomingFaxesArePublic>false</IncomingFaxesArePublic>
   <ArchiveFolderName>C:\MyFaxArchives</ArchiveFolderName>
</Fax>
<FaxUnattend>
   <FaxPrinterIsShared>true</FaxPrinterIsShared>
   <ReceiveFaxes>false</ReceiveFaxes>
   <Rings>6</Rings>
   <RouteToFolder>true</RouteToFolder>
   <RouteToPrinter>true</RouteToPrinter>
   <SendFaxes>true</SendFaxes>
   <Csid>Fax1</Csid>
   <Tsid>Fax1</Tsid>
   <RouteFolderName>C:\Router</RouteFolderName>
   <RoutePrinterName>C:\Printer</RoutePrinterName>
</FaxUnattend>
<Receipts>
   <FaxUserName>MyUserName</FaxUserName>
   <FaxUserPassword>MyPassword</FaxUserPassword>
   <SmtpNotificationsEnabled>true</SmtpNotificationsEnabled>
   <SmtpSenderAddress>MyUserName@fabrikam.com</SmtpSenderAddress>
   <SmtpServerAddress>207.46.197.32</SmtpServerAddress>
   <SmtpServerAuthenticationMechanism>1</SmtpServerAuthenticationMechanism>
   <SmtpServerPort>26</SmtpServerPort>
</Receipts>
```

## Related topics


[Fax](microsoft-windows-fax-service-fax.md)

 

 







