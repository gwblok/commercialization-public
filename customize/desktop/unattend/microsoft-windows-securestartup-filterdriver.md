---
title: Microsoft-Windows-SecureStartup-FilterDriver
description: Microsoft-Windows-SecureStartup-FilterDriver
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: d64c8dad-d2a2-4786-a811-2a03b6d53607
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Microsoft-Windows-SecureStartup-FilterDriver

The Microsoft-Windows-SecureStartup-FilterDriver component contains settings to optimize BitLocker settings for PCs with hardware architectures such as System on a Chip (SoC).

These settings are intended for OEM manufacturing only. For specific guidance on using these settings, contact Microsoft.

> [!Warning]
> Do not use these settings for standard 32-bit or 64-bit hardware architectures.

These settings only apply to Windows 8.

## In This Section

<table>
<colgroup>
<col width="100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="microsoft-windows-securestartup-filterdriver-bytesdecryptedindiskrequestoverhead.md" data-raw-source="[BytesDecryptedInDiskRequestOverhead](microsoft-windows-securestartup-filterdriver-bytesdecryptedindiskrequestoverhead.md)">BytesDecryptedInDiskRequestOverhead</a></p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-securestartup-filterdriver-maxcryptorequestsperio.md" data-raw-source="[MaxCryptoRequestsPerIo](microsoft-windows-securestartup-filterdriver-maxcryptorequestsperio.md)">MaxCryptoRequestsPerIo</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-securestartup-filterdriver-maxdecryptrequests.md" data-raw-source="[MaxDecryptRequests](microsoft-windows-securestartup-filterdriver-maxdecryptrequests.md)">MaxDecryptRequests</a></p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-securestartup-filterdriver-maxencryptrequests.md" data-raw-source="[MaxEncryptRequests](microsoft-windows-securestartup-filterdriver-maxencryptrequests.md)">MaxEncryptRequests</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-securestartup-filterdriver-preventdeviceencryption.md" data-raw-source="[PreventDeviceEncryption](microsoft-windows-securestartup-filterdriver-preventdeviceencryption.md)">PreventDeviceEncryption</a></p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-securestartup-filterdriver-slicedencryptioninplace.md" data-raw-source="[SlicedEncryptionInPlace](microsoft-windows-securestartup-filterdriver-slicedencryptioninplace.md)">SlicedEncryptionInPlace</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-securestartup-filterdriver-slicedencryptionminsize.md" data-raw-source="[SlicedEncryptionMinSize](microsoft-windows-securestartup-filterdriver-slicedencryptionminsize.md)">SlicedEncryptionMinSize</a></p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-securestartup-filterdriver-slicedencryptionrequestsmax.md" data-raw-source="[SlicedEncryptionRequestsMax](microsoft-windows-securestartup-filterdriver-slicedencryptionrequestsmax.md)">SlicedEncryptionRequestsMax</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-securestartup-filterdriver-writeioaggregatemaxsize.md" data-raw-source="[WriteIoAggregateMaxSize](microsoft-windows-securestartup-filterdriver-writeioaggregatemaxsize.md)">WriteIoAggregateMaxSize</a></p></td>
</tr>
<tr class="even">
<td><p><a href="microsoft-windows-securestartup-filterdriver-writeioaggregateminsize.md" data-raw-source="[WriteIoAggregateMinSize](microsoft-windows-securestartup-filterdriver-writeioaggregateminsize.md)">WriteIoAggregateMinSize</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="microsoft-windows-securestartup-filterdriver-writesubrequestlength.md" data-raw-source="[WriteSubrequestLength](microsoft-windows-securestartup-filterdriver-writesubrequestlength.md)">WriteSubrequestLength</a></p></td>
</tr>
</tbody>
</table>

## Applies To

To determine whether a component applies to the image you’re building, load your image into Windows SIM and search for the component or setting name. For information on how to view components and settings, see [Configure Components and Settings in an Answer File](https://docs.microsoft.com/en-us/windows-hardware/customize/desktop/wsim/configure-components-and-settings-in-an-answer-file).

> [!Note]
> Although this component is available in x86 hardware architectures, these settings should not be used for standard x86 hardware architectures.

## XML Example

The following example specifies recommended values for Bitlocker optimizations on an x86 System on a Chip.

```XML
<component name="microsoft-windows-securestartup-filterdriver-" processorArchitecture="x86" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="http://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <BytesDecryptedInDiskRequestOverhead>524288</BytesDecryptedInDiskRequestOverhead>
  <InPlaceCrypto>0</InPlaceCrypto>
  <MaxCryptoRequestsPerIo>5</MaxCryptoRequestsPerIo>
  <MaxDecryptRequests>0</MaxDecryptRequests>
  <MaxEncryptRequests>2</MaxEncryptRequests>
  <ModifiedWriteMaximum>4</ModifiedWriteMaximum>
  <ReadDoubleBuffering>0</ReadDoubleBuffering>
  <SlicedEncryptionInPlace>1</SlicedEncryptionInPlace>
  <SlicedEncryptionMinSize>524288</SlicedEncryptionMinSize>
  <SlicedEncryptionRequestsMax>1</SlicedEncryptionRequestsMax>
  <WriteIoAggregateMaxSize>1048576</WriteIoAggregateMaxSize>
  <WriteIoAggregateMinSize>1048576</WriteIoAggregateMinSize>
  <WriteSubrequestLength>524288</WriteSubrequestLength>
 </component>
```

## Related topics

[Components](components-b-unattend.md)
