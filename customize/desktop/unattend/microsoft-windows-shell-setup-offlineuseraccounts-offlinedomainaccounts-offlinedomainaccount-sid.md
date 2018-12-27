---
title: SID
description: SID specifies the security identifier of the domain account.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: D79DBAFD-B570-4C89-8148-AE71EF83D95A
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---

# SID


`SID` specifies the security identifier of the domain account.

## Values


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><em>SID</em></p></td>
<td><p>Specifies the security identifier of the domain account. <em>SID</em> is a string with a maximum length of 256 characters.</p>
<p>For information on how to determine the security identifier for an Active Directory user account using PowerShell, see this <a href="http://go.microsoft.com/fwlink/?LinkId=533300" data-raw-source="[Microsoft Web site](http://go.microsoft.com/fwlink/?LinkId=533300)">Microsoft Web site</a>.</p>
<pre class="syntax" space="preserve"><code>$objUser = New-Object System.Security.Principal.NTAccount(&quot;fabrikam&quot;, &quot;kenmyer&quot;)
$strSID = $objUser.Translate([System.Security.Principal.SecurityIdentifier])
$strSID.Value</code></pre>
<p>The following XML example shows the format for the <code>SID</code> value:</p>
<pre class="syntax" space="preserve"><code>&lt;OfflineUserAccounts&gt;

     &lt;OfflineDomainAccounts&gt;
         &lt;OfflineDomainAccount&gt;
             &lt;SID&gt;S-1-5-21-1454471165-1004335555-1606985555-5555&lt;/SID&gt;
             &lt;Groups&gt;Administrators&lt;/Group&gt;
         &lt;/OfflineDomainAccount&gt;<br/>
         &lt;OfflineDomainAccount&gt;
             &lt;SID&gt;S-1-5-21-1454471165-1004335555-1606985555-5999&lt;/SID&gt;
             &lt;Groups&gt;Administrators;BackupOperators&lt;/Group&gt;
         &lt;/OfflineDomainAccount&gt;
    &lt;/OfflineDomainAccounts&gt;

&lt;/OfflineUserAccounts&gt;</code></pre></td>
</tr>
</tbody>
</table>



This string type does not support empty elements. Do not create an empty value for this setting.

## Valid Configuration Passes


offlineServicing

## Parent Hierarchy


[Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md) | [OfflineUserAccounts](microsoft-windows-shell-setup-offlineuseraccounts.md) | [OfflineDomainAccounts](microsoft-windows-shell-setup-offlineuseraccounts-offlinedomainaccounts.md) | [OfflineDomainAccount](microsoft-windows-shell-setup-offlineuseraccounts-offlinedomainaccounts-offlinedomainaccount.md) | **SID**

## Applies To


Windows 10 for desktop editions (Home, Pro, Enterprise, and Education)

Windows Server 2016

For a list of the supported Windows editions and architectures that this component supports, see [Microsoft-Windows-Shell-Setup](microsoft-windows-shell-setup.md).










