---
title: Visual voicemail
description: Visual voicemail supports both traditional voicemail (retrieved through a phone call) and visual voicemail.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 1cc2c4ef-4c16-455b-8e70-ef181a04a394


ms.date: 05/02/2017
ms.topic: article


---
# Visual voicemail

**Visual voicemail** supports both traditional voicemail (retrieved through a phone call) and visual voicemail. Users can select between traditional voicemail and visual voicemail when they first attempt to access voicemail. If the mobile operator does not support this visual voicemail implementation, the user will only see the traditional voicemail option. For mobile operators that have their own particular brand that they want to use instead of visual voicemail, partners can rebrand all instances of **visual voicemail** in the Windows 10 Mobile UI to use the operator's brand.

The mobile operator visual voicemail system must be an OMTP-compliant system that meets the following requirements.

* Uses the AMR-NB codec for incoming voicemail messages.
* Sends all SMS-MT as port-directed SMS.
* Sends all SMS-MT with 7-bit default or UCS2 encoding.
* Supports enabling and disabling the visual voicemail feature on the phone by using ACTIVATE and DEACTIVATE SMS-MO messages.

The visual voicemail implementation on the phone is based on the [OMTP visual voice mail interface specification](http://go.microsoft.com/fwlink/p/?LinkId=212770). Visual voicemail support on Windows Phone 8.1 was tested on OMTP-based protocols by Comverse and Alcatel Lucent. Other OMTP-based protocols like Streamwide may also be supported, although tests were performed only on Comverse and Alcatel Lucent. Variations from the OMTP standard may result in unsupported scenarios.

The following table shows the extent of support for the features recommended by OMTP. The features marked "Partially supported" provide a button to enable the user to call in to the voicemail system and change the settings over the phone.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Feature recommended by OMTP</th>
<th>Support in Windows Phone</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IMAP4 message retrieval</p></td>
<td><p>Supported</p></td>
</tr>
<tr class="even">
<td><p>Local visual voicemail store creation</p></td>
<td><p>Supported</p></td>
</tr>
<tr class="odd">
<td><p>Hide visual voicemail store from user</p></td>
<td><p>Supported</p></td>
</tr>
<tr class="even">
<td><p>Display non-audio messages</p></td>
<td><p>Not supported</p></td>
</tr>
<tr class="odd">
<td><p>Codec support: AMR 12.2k</p></td>
<td><p>Supported</p></td>
</tr>
<tr class="even">
<td><p>Codec support: WAV g711a</p></td>
<td><p>Not supported</p></td>
</tr>
<tr class="odd">
<td><p>Codec support: WAV g711u</p></td>
<td><p>Not supported</p></td>
</tr>
<tr class="even">
<td><p>Codec support: QCELP 13.3k</p></td>
<td><p>Not supported</p></td>
</tr>
<tr class="odd">
<td><p>Codec support: EVRC 13.3k</p></td>
<td><p>Not supported</p></td>
</tr>
<tr class="even">
<td><p>Mark incoming visual voicemail messages as \Seen, \Deleted</p></td>
<td><p>Supported</p></td>
</tr>
<tr class="odd">
<td><p>Deposit visual voicemail messages</p></td>
<td><p>Not supported</p></td>
</tr>
<tr class="even">
<td><p>Forward visual voicemail messages</p></td>
<td><p>Not supported</p></td>
</tr>
<tr class="odd">
<td><p>Set/Change TUI password</p></td>
<td><p>Partially supported</p></td>
</tr>
<tr class="even">
<td><p>Change TUI language</p></td>
<td><p>Partially supported</p></td>
</tr>
<tr class="odd">
<td><p>Close New User tutorial</p></td>
<td><p>Supported</p></td>
</tr>
<tr class="even">
<td><p>Query for storage quota status</p></td>
<td><p>Not supported</p></td>
</tr>
<tr class="odd">
<td><p>Enable/disable on-demand audio message transcription</p></td>
<td><p>Not supported</p></td>
</tr>
<tr class="even">
<td><p>Store a custom personal greeting</p></td>
<td><p>Not supported</p></td>
</tr>
<tr class="odd">
<td><p>Delete a stored custom personal greeting</p></td>
<td><p>Not supported</p></td>
</tr>
<tr class="even">
<td><p>Store a voice signature</p></td>
<td><p>Not supported</p></td>
</tr>
<tr class="odd">
<td><p>Enable/disable custom personal greeting</p></td>
<td><p>Not supported</p></td>
</tr>
<tr class="even">
<td><p>Retrieve and store provisioning status and credentials</p></td>
<td><p>Supported</p></td>
</tr>
<tr class="odd">
<td><p>Activate and deactivate visual voicemail</p></td>
<td><p>Supported</p></td>
</tr>
</tbody>
</table>

<a href="" id="constraints---none"></a>**Constraints:** None

## Instructions

To configure visual voicemail for a mobile operator, the OEM must add setting several settings depending on the OMTP-based protocol being used by the operator.

> [!Note]
> Visual voicemail settings have already been set for AT&T, T-Mobile USA, and Deutsche Telekom AG (DTAG), and no further configuration is required for these three mobile operators.

1. Create a customization answer file using the contents shown in the following code sample.

   ```XML
   <?xml version="1.0" encoding="utf-8" ?>
   <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"
                        Name="VisualVoicemail"
                        Description="Use to configure visual voicemail settings in the phone image."
                        Owner=""
                        OwnerType="OEM">
     <Static>
       <Settings Path="Phone/VoicemailRegistrationTable">
          <!-- The MCCMNC macro allows you to set multiple MCCMNC\VVMMMO pairs.
              The Value stored here will be the key for the Table. -->
         <Setting Name="ProviderRegistration/$(MCCMNC)" Value="" />
         <Setting Name="ProviderRegistration/$(MCCMNC)" Value="" />
       </Settings>
        <!-- The VVMMO is the value stored in the MCCMNC setting. This macro allows you to create multiple table entries. -->
       <Settings Path="Phone/VoicemailRegistrationTable/$(VVMMO)">
         <Setting Name="CLSIDProvider" Value="" />
         <Setting Name="CLSIDAccessor" Value="" />
         <Setting Name="ProtocolVariant" Value="" />
         <Setting Name="IncomingPort" Value="" />
         <Setting Name="ClientType" Value="" />
         <Setting Name="DeviceType" Value="" />
         <Setting Name="InitialSmsDestinationNumber" Value="" />
         <Setting Name="EncryptedSmsSupported" Value="" />
         <Setting Name="KeyData" Value="" />
         <Setting Name="ImapPortOverride" Value="" />
         <Setting Name="TokenLogin" Value="" />
         <Setting Name="SuppressSsl" Value="" />
         <Setting Name="IgnoreLegacyNotifications" Value="" />
         <Setting Name="Branding" Value="" />
       </Settings>  
       <Settings Path="Phone/VoicemailRegistrationTable/$(VVMMO)">
         <Setting Name="CLSIDProvider" Value="" />
         <Setting Name="CLSIDAccessor" Value="" />
         <Setting Name="ProtocolVariant" Value="" />
         <Setting Name="IncomingPort" Value="" />
         <Setting Name="ClientType" Value="" />
         <Setting Name="DeviceType" Value="" />
         <Setting Name="InitialSmsDestinationNumber" Value="" />
         <Setting Name="EncryptedSmsSupported" Value="" />
         <Setting Name="KeyData" Value="" />
         <Setting Name="ImapPortOverride" Value="" />
         <Setting Name="TokenLogin" Value="" />
         <Setting Name="SuppressSsl" Value="" />
         <Setting Name="IgnoreLegacyNotifications" Value="" />
         <Setting Name="Branding" Value="" />
       </Settings>
     </Static>
   </ImageCustomizations>
   ```

1. Specify an `Owner`.
1. Set multiple MCCMNC\\VVMMO pairs by adding the following entry in your customization answer file.

   ```XML
       <Settings Path="Phone/VoicemailRegistrationTable">
         <Setting Name="ProviderRegistration/$(MCCMNC)" Value="" /> 
       </Settings>
   ```

   1. Replace *$(MCCMNC)* with the MCCMNC for the mobile operator. For example, *99999*.
   1. Set the corresponding `Value` to the name of the VVMMO. For example, *Contoso*.
   1. Add and set as many MCCMNC\\VVMMO pairs as you need for each mobile operator ID. For example, if you are adding another VVMMO called Fabrikam with MCC/MNC of 999/10, your entries will look like this:

      ```XML
          <Settings Path="Phone/VoicemailRegistrationTable">
            <Setting Name="ProviderRegistration/99999" Value="Contoso" />
            <Setting Name="ProviderRegistration/99910" Value="Fabrikam" />
          </Settings>
      ```

1. For each mobile operator ID defined in the previous step, you must define the applicable settings for that mobile operator by adding the following settings in your customization answer file.

   ```XML
       <Settings Path="Phone/VoicemailRegistrationTable/$(VVMMO)">
         <Setting Name="CLSIDProvider" Value="" />
         <Setting Name="CLSIDAccessor" Value="" />
         <Setting Name="ProtocolVariant" Value="" />
         <Setting Name="IncomingPort" Value="" />
         <Setting Name="ClientType" Value="" />
         <Setting Name="DeviceType" Value="" />
         <Setting Name="InitialSmsDestinationNumber" Value="" />
         <Setting Name="EncryptedSmsSupported" Value="" />
         <Setting Name="KeyData" Value="" />
         <Setting Name="ImapPortOverride" Value="" />
         <Setting Name="TokenLogin" Value="" />
         <Setting Name="SuppressSsl" Value="" />
         <Setting Name="IgnoreLegacyNotifications" Value="" />
       </Settings>
   ```

1. Replace *$(VVMMO)* with the name of the VVMMO. For example, *Contoso*.
1. Set only the applicable settings that apply to the VVMMO and are required depending on the OMTP-based protocol being used. Note that you do not have to set all of these if they are not supported. The following table describes the values to use and indicates if the keys are required depending on the OMTP-based protocol being used.

| Key name                    | Type       | Generic OMTP   | Comverse     | Alcatel Lucent | Details                                                    |
|:----------------------------|:-----------|:---------------|:-------------|:---------------|:-----------------------------------------------------------|
| CLSIDProvider               | REG_SZ     | Required       | Required     | Required       | Use {039B8E0E-EA5E-4801-96CD-71E7B343F03F} for an OMTP visual voicemail server or Comverse visual voicemail server.<br/>Use {C9804AB2-60B0-4AFF-8205-E30E591F145B} for an Alcatel Lucent visual voicemail server.      |
| CLSIDAccessor               | REG_SZ     | Required       | Required     | Required       | Use the value {BC371B86-031F-4BD7-9E7D-FB5DF7D1D8C3}       |
| ProtocolVariant             | REG_SZ     | Required       | Required     | --             | OMTP protocol version (“pv”). Use &quot;ProtocolVariant&quot;=&quot;omtp&quot; for generic OMTP systems, or &quot;ProtocolVariant&quot;=&quot;comverse&quot; for implementations that use Comverse systems.             |
| IncomingPort                | REG_DWORD  | Required       | Required     | Required       | SMS-MT application port (“pt”)                             |
| ClientType                  | REG_SZ     | Required       | Required     | --             | An identifier for the category of devices, which can be set to any string. (“ct”)            |
| DeviceType                  | REG_SZ     | Required       | Required     | --             | A second–level Comverse-specific device type identifier.   |
| InitialSmsDestinationNumber | REG_SZ     | Required       | Required     | --             | Phone number to use for SMS-MO messages for visual voicemail such as ACTIVATE or DEACTIVATE (“dn”).     |
| EncryptedSmsSupported       | REG_DWORD  | Not required   | Not required |--              | Specifies whether 3DES encrypted SMS is supported.<br/>Use a value of 0 to indicate it is not supported. Use 1 to indicate this feature is supported.    |
| KeyData                     | REG_BINARY | Required if EncryptedSmsSupported is set to 1. | Required if EncryptedSmsSupported is set to 1.  | --  | The binary key to use for encrypted SMS.       |
| ImapPortOverride            | REG_DWORD  | --             | --           | Not required   | Specifies the IMAP port to use regardless of the message contents. This feature should be turned on only for mobile operators that require it.       |
| TokenLogin                  | REG_DWORD  | --             | --           | Not required   | Enables the use of token-based login instead of traditional username and password.<br/>This feature should be turned on only for mobile operators that require it.  |
| SuppressSsl                 | REG_DWORD  | --             | --           | Not required   | Ignores any directive in the message payload to use SSL and forces non-SSL IMAP. This feature should be turned on only for mobile operators that require it.<br/>Use a value of 0 to indicate the feature is off; use 1 to indicate it is turned on.  |
| IgnoreLegacyNotifications   | REG_DWORD  | Not required   | Not required | Not required   | Specifies whether legacy voicemail notifications should be ignored when visual voicemail is enabled. If the ignore legacy voicemail notification feature is enabled, legacy message waiting indicator SMS messages are ignored (i.e. these will not trigger a visual voicemail sync). If this feature is absent or not enabled, legacy voicemail MWI messages will cause a visual voicemail sync to be initiated.<br/>This feature should be turned on only for mobile operators that require it. This feature is not enabled by default.<br/>Use a value of 0 to indicate the feature is off; use 1 to indicate it is turned on. |

1. For mobile operators that have their own particular brand that they want to use instead of visual voicemail, partners can rebrand all instances of **Visual voicemail** in the Windows device UI to use the operator's brand.

   To do this, set the value for `Branding` to the specific name that the mobile operator is using for visual voicemail. For example, you can set the value to *Contoso Voice Inbox*.

   > [!Note]
   > This setting does not support a resource-only DLL for localized strings so you need to set the new string directly as the value.

## Testing

Work with your mobile operator to obtain the settings and values that you need to configure visual voicemail and the value to use for `Branding`.

Once you have configured the visual voicemail settings and the branding, work with the mobile operator to test this customization on their network and verify that all instances of **Visual voicemail** in the Windows device UI have been replaced with the custom brand that you specified.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
