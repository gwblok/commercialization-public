---
title: MaxCryptoRequestsPerIo
description: MaxCryptoRequestsPerIo
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: f779636a-7924-449a-94b8-d76d13ee790c
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# MaxCryptoRequestsPerIo


The `MaxCryptoRequestsPerIo` setting works with other settings in the [microsoft-windows-securestartup-filterdriver-](microsoft-windows-securestartup-filterdriver.md) component to optimize BitLocker settings for PCs with hardware architectures such as System on a Chip (SoC). Do not use these settings for standard 32-bit or 64-bit hardware architectures.

These settings are intended for OEM manufacturing only. For specific guidance on using these settings, contact Microsoft.

**Note**  
These settings only apply to Windows 8.

 

## Values


`MaxCryptoRequestsPerIo` is an integer.

The default value is `5`.

## Valid Configuration Passes


offlineServicing

specialize

auditSystem

oobeSystem

## Parent Hierarchy


[microsoft-windows-securestartup-filterdriver-](microsoft-windows-securestartup-filterdriver.md) | **MaxCryptoRequestsPerIo**

## Applies To


For a list of the Windows editions and architectures that this component supports, see [microsoft-windows-securestartup-filterdriver-](microsoft-windows-securestartup-filterdriver.md).

## XML Example


The following example specifies recommended values for Bitlocker optimizations on an x86 System on a Chip.

```
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


[microsoft-windows-securestartup-filterdriver-](microsoft-windows-securestartup-filterdriver.md)

 

 







