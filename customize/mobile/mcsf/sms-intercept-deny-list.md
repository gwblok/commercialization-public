---
title: SMS intercept deny list
description: OEMs can specify one or more filters in order to intercept incoming SMS messages intended for mobile operator partner applications that are not installed on the device.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: ab3718ea-17d4-4203-893e-87479802030c


ms.date: 05/02/2017
ms.topic: article


---

# SMS intercept deny list


OEMs can specify one or more filters in order to intercept incoming SMS messages intended for mobile operator partner applications that are not installed on the device.

Applications from mobile operator partners can receive notifications from incoming SMS messages. Specifically, the Windows 10 Mobile SMS intercept feature takes string filters declared by the partner application in its manifest and matches these with the opening text in the SMS messages. If there is a string match, the message is delivered to the corresponding application instead of the Microsoft messaging application. 

As part of the SMS intercept feature, OEMs can specify one or more filters in a *deny list* to be matched against incoming SMS messages intended for mobile operator partner applications that are not installed on the device. If an SMS message matches a filter on the deny list, the message is dropped and never delivered to the messaging application or shown to the user. If filters are not specified as part of the deny list and the mobile operator application is not installed on the device, the SMS message is delivered to the Microsoft messaging application and displayed to the user.

The SMS intercept deny list follows the following filter and string matching rules:

<a href="" id="filter-rules-"></a>**Filter rules:**  
-   Each filter can only be matched to one application ID. If multiple applications listed the same filter, the first application is used. This is not deterministic across boots.

-   The longest filter strings are matched to ensure that exact matches are made before partial matches.

-   A filter must be at least 3 characters long. If the filter is less than 3 characters long it will be ignored and omitted from the filter match list.

-   A filter can be up to 74 characters long.

-   A filter can only contain valid Unicode characters.

-   Byte by byte comparison is used without consideration for culture.

-   Comparisons are not case sensitive.

<a href="" id="string-match-rules-"></a>**String match rules:**  
-   The string must start as the leading character of the message.

-   The filter string is considered a match if it is an exact match or it is a partial match where the entire filter is contained in the first segment of the body of the message.

The SMS intercept deny list runs after the partner application string matching has been done.

The following examples show the results for the string match based on the preceding rules:

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Filter string</th>
<th>Body of the SMS message</th>
<th>String match result</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>//MOMessagingClient</p></td>
<td><p>//MOMessagingClient</p></td>
<td><p>Yes – exact match</p></td>
</tr>
<tr class="even">
<td><p>MOMessagingClient</p></td>
<td><p>MOMessagingClient</p></td>
<td><p>Yes – exact match</p></td>
</tr>
<tr class="odd">
<td><p>//MOMessagingClient</p></td>
<td><p>//MOMessagingClient12345 You can sign on!</p></td>
<td><p>Yes – partial match</p></td>
</tr>
<tr class="even">
<td><p>//MOMessagingClient</p></td>
<td><p>You can sign on now! //MOMessagingClient</p></td>
<td><p>No – wrong location</p></td>
</tr>
<tr class="odd">
<td><p>//M*MessagingClient</p></td>
<td><p>//MOMessagingClient</p></td>
<td><p>No – no wildcards in the filter string</p></td>
</tr>
<tr class="even">
<td><p>//</p></td>
<td><p>//MOMessagingClient</p></td>
<td><p>No – filter string must be at least 3 characters</p></td>
</tr>
<tr class="odd">
<td><p>//MOMessagingClient</p></td>
<td><p>//MOMessageClient You can sign on!</p></td>
<td><p>No – not an exact match</p></td>
</tr>
<tr class="even">
<td><p>//MOMessagingClient</p></td>
<td><p>_//MOMessagingClient</p></td>
<td><p>No – not a leading string</p></td>
</tr>
<tr class="odd">
<td><p>MOMessagingClient</p></td>
<td><p>MOMessagingClient</p></td>
<td><p>No – leading whitespace or tab</p></td>
</tr>
<tr class="even">
<td><p>//MOMessagingClient</p></td>
<td><p>//momessagingclient</p></td>
<td><p>Case insensitive</p></td>
</tr>
<tr class="odd">
<td><p>//MOMessagingClient</p>
<p>//MO</p></td>
<td><p>//MOMessagingClient</p></td>
<td><p>Exact match (on //MOMessagingClient) over partial (//MO)</p></td>
</tr>
</tbody>
</table>

 

<a href="" id="constraints---none"></a>**Constraints:** None  
This customization supports: **per-SIM** value

<a href="" id="instructions-"></a>**Instructions:**  
1.  Create a customization answer file using the contents shown in the following code sample.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>  
    <ImageCustomizations xmlns="http://schemas.microsoft.com/embedded/2004/10/ImageUpdate"  
                         Name="SMSInterceptDenyList"  
                         Description="Use to specify one or more filters in a deny list to be matched against incoming SMS messages intended for 
                         mobile operator partner applications that are not installed on the device."  
                         Owner=""  
                         OwnerType="OEM"> 
      
      <!-- Define the Targets --> 
      <Targets>
         <Target Id="">
            <TargetState>
               <Condition Name="" Value="" />
               <Condition Name="" Value="" />
            </TargetState>
         </Target>
      </Targets>
      
      <Static>
        <Settings Path="Multivariant">
          <Setting Name="Enable" Value="1" />
        </Settings>
        <Settings Path="AutoDataConfig">
          <Setting Name="Enable" Value="0" />
        </Settings>
      </Static>

      <!-- Specify the Variant -->
      <Variant Name=""> 
        <TargetRefs>
          <TargetRef Id="" /> 
        </TargetRefs>

        <Settings Path="Messaging/PerSimSettings/$(__ICCID)">  
          <!-- Set the value for the ports where the device will accept cellular broadcast messages.
               The value must be in REG_MULTI_SZ format, such as "Prefix1;Prefix2;Prefix3" and so on -->
          <Setting Name="SmsInterceptPrefixes" Value="" />    
        </Settings>  

      </Variant>

    </ImageCustomizations>
    ```

2.  Specify an `Owner`.

3.  Define **Targets** or conditions for when a variant can be applied, such as keying off a SIM's MCC, MNC, and SPN.

4.  Define settings for a **Variant**, which are applied if the associated target's conditions are met.

5.  Set the `SmsInterceptPrefixes` value to one or more filters in a deny list. For example, *Prefix1;Prefix2;Prefix3* and so on.

The following notes apply for this customization:

-   SMS messages that start with the filters (designated by the placeholders *Prefix1*,*Prefix2*, and so on) are dropped and never delivered. Filters are provided by the mobile operators.

-   The number of filters that OEMs can add in the deny list is not limited.

-   The system does not back up the set of settings and values for this feature.

-   The system only reads the deny list at boot time. If setting values are updated at a later time, the device must be restarted for the updated list to take effect.

<a href="" id="testing-steps-"></a>**Testing steps:**  
1.  Flash the build containing this customization to a device.

2.  Send several SMS messages to the device (some that match the filters and others that do not).

3.  Based on the filters that you added, verify if the messages that match the filters were correctly dropped and verify that those that don’t match any filters show up in the messaging app.

## Related topics

[Prepare for Windows mobile development](https://docs.microsoft.com/en-us/windows-hardware/manufacture/mobile/preparing-for-windows-mobile-development)

[Customization answer file overview](https://docs.microsoft.com/en-us/windows-hardware/customize/mobile/mcsf/customization-answer-file)
