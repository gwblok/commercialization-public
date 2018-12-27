---

Description: 'Sets a value indicating whether the phone speaker should be used, as opposed to the handset earphone.'
ms.assetid: ae0382d0-01fc-40eb-ae3d-72242ac4aede
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: MfgPhoneSetSpeaker function
ms.author: themar
ms.date: 05/02/2017
ms.topic: article


---

# MfgPhoneSetSpeaker function


Sets a value indicating whether the phone speaker should be used, as opposed to the handset earphone.

**MfgPhoneSetSpeaker** is for phone manufacturers and can only be called in Manufacturing Mode.

**Syntax**

```ManagedCPlusPlus
HRESULT APIENTRY MfgPhoneSetSpeaker(
  _In_ BOOL bSpeakerOn
);
```

**Parameters**

*bSpeakerOn* \[in\]  
TRUE if the speaker should be used, otherwise false.

**Return value**

S\_OK is returned upon success and an error code is returned otherwise.

**Requirements**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>Header</p></td>
<td align="left">Mfgphone.h (include Mfgphone.h)</td>
</tr>
<tr class="even">
<td align="left"><p>DLL</p></td>
<td align="left">MFGPHONE.DLL</td>
</tr>
</tbody>
</table>

 

 





