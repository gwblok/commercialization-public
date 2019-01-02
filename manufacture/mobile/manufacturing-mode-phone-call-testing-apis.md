---

Description: 'These APIs are used by phone manufacturers to test phone call functionality while the device is booted into Manufacturing Mode.'
ms.assetid: 3a1bdf3e-e95d-4277-bad7-1063a138f473
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: Manufacturing Mode Phone Call Testing APIs
ms.author: themar
ms.date: 05/02/2017
ms.topic: article


---

# Manufacturing Mode Phone Call Testing APIs

These APIs are used by phone manufacturers to test phone call functionality while the device is booted into Manufacturing Mode.

## <span id="in_this_section"></span>In this section


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Topic</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="mfgphonedial.md" data-raw-source="[&lt;strong&gt;MfgPhoneDial&lt;/strong&gt;](mfgphonedial.md)"><strong>MfgPhoneDial</strong></a></p></td>
<td align="left"><p>Causes the phone to dial a call.</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="mfgphoneendcall.md" data-raw-source="[&lt;strong&gt;MfgPhoneEndCall&lt;/strong&gt;](mfgphoneendcall.md)"><strong>MfgPhoneEndCall</strong></a></p></td>
<td align="left"><p>Ends a phone call.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="mfgphonegetsimlinecount.md" data-raw-source="[&lt;strong&gt;MfgPhoneGetSimLineCount&lt;/strong&gt;](mfgphonegetsimlinecount.md)"><strong>MfgPhoneGetSimLineCount</strong></a></p></td>
<td align="left"><p>Gets the number of currently detected SIM slots.</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="mfgphonegetsimlinedetail.md" data-raw-source="[&lt;strong&gt;MfgPhoneGetSimLineDetail&lt;/strong&gt;](mfgphonegetsimlinedetail.md)"><strong>MfgPhoneGetSimLineDetail</strong></a></p></td>
<td align="left"><p>Retrieves a struct that contains the current details for a given SIM-based phone line.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="mfgphonegetspeaker.md" data-raw-source="[&lt;strong&gt;MfgPhoneGetSpeaker&lt;/strong&gt;](mfgphonegetspeaker.md)"><strong>MfgPhoneGetSpeaker</strong></a></p></td>
<td align="left"><p>Returns a boolean indicating whether the phone speaker is being used, as opposed to the handset earphone.</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="mfgphoneinitialize.md" data-raw-source="[&lt;strong&gt;MfgPhoneInitialize&lt;/strong&gt;](mfgphoneinitialize.md)"><strong>MfgPhoneInitialize</strong></a></p></td>
<td align="left"><p>Initializes the phone system and the internal state of the API implemented by DLL.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="mfgphonesetsimlineeventnotifycallback.md" data-raw-source="[&lt;strong&gt;MfgPhoneSetSimLineEventNotifyCallback&lt;/strong&gt;](mfgphonesetsimlineeventnotifycallback.md)"><strong>MfgPhoneSetSimLineEventNotifyCallback</strong></a></p></td>
<td align="left"><p>Callback-based notification mechanism for receiving events on SIM-based phone lines.</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="mfgphonesetspeaker.md" data-raw-source="[&lt;strong&gt;MfgPhoneSetSpeaker&lt;/strong&gt;](mfgphonesetspeaker.md)"><strong>MfgPhoneSetSpeaker</strong></a></p></td>
<td align="left"><p>Sets a value indicating whether the phone speaker should be used, as opposed to the handset earphone.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="mfgphoneuninitialize.md" data-raw-source="[&lt;strong&gt;MfgPhoneUninitialize&lt;/strong&gt;](mfgphoneuninitialize.md)"><strong>MfgPhoneUninitialize</strong></a></p></td>
<td align="left"><p>Uninitializes the phone system and the internal state of the API implemented by DLL.</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="mfgphone-callstatus.md" data-raw-source="[&lt;strong&gt;MFGPHONE_CALLSTATUS&lt;/strong&gt;](mfgphone-callstatus.md)"><strong>MFGPHONE_CALLSTATUS</strong></a></p></td>
<td align="left"><p>Provides information about the status of the call.</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="mfgphone-linesystemtype.md" data-raw-source="[&lt;strong&gt;MFGPHONE_LINESYSTEMTYPE&lt;/strong&gt;](mfgphone-linesystemtype.md)"><strong>MFGPHONE_LINESYSTEMTYPE</strong></a></p></td>
<td align="left"><p>Provides information about the type of line system.</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="mfgphone-registrationstate.md" data-raw-source="[&lt;strong&gt;MFGPHONE_REGISTRATIONSTATE&lt;/strong&gt;](mfgphone-registrationstate.md)"><strong>MFGPHONE_REGISTRATIONSTATE</strong></a></p></td>
<td align="left"><p>Provides information about the state of the phone line? call?</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="mfgphone-simlinedetail.md" data-raw-source="[&lt;strong&gt;MFGPHONE_SIMLINEDETAIL&lt;/strong&gt;](mfgphone-simlinedetail.md)"><strong>MFGPHONE_SIMLINEDETAIL</strong></a></p></td>
<td align="left"><p>Provides information about a particular SIM-based phone line.</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="mfgphone-simstate.md" data-raw-source="[&lt;strong&gt;MFGPHONE_SIMSTATE&lt;/strong&gt;](mfgphone-simstate.md)"><strong>MFGPHONE_SIMSTATE</strong></a></p></td>
<td align="left"><p>Provides information about the state of the SIM.</p></td>
</tr>
</tbody>
</table>

 

 

 





