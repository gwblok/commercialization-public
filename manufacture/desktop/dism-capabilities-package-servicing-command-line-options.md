---

Description: 'Windows 10 for desktop editions (Home, Pro, Enterprise, and Education) only.'
ms.assetid: b5f9740e-070c-48c0-9f79-42b25dfeb219
MSHAttr: 'PreferredLib:/library/windows/hardware'
title: 'DISM Capabilities Package Servicing Command-Line Options'

ms.date: 05/02/2017
ms.topic: article


---

# <span id="dism_capabilities_package_servicing_command-line_options"></span>DISM Capabilities Package Servicing Command-Line Options


Windows 10 for desktop editions (Home, Pro, Enterprise, and Education) only. Use Deployment Image Servicing and Management (DISM.exe) to service Windows capabilities. Capabilities are a Windows package type allows you to request services like .NET or languages without specifying the version. Use DISM to search multiple sources like Windows Update or your corporate servers to find and install the latest version.

To see the available capabilities, go to [Features On Demand](features-on-demand-v2--capabilities.md).

## <span id="DISM_Command-Line_Options"></span><span id="dism_command-line_options"></span><span id="DISM_COMMAND-LINE_OPTIONS"></span>DISM Command-Line Options


Here's how each DISM option can be used. These options are not case sensitive.

Note, each of these commands requires either the **/Online** or **/Image:**&lt;*path\_to\_offline\_image\_file*&gt; argument.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Options</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>/Add-Capability</strong></p>
<p><strong>/CapabilityName:</strong>&lt;<em>capability_name</em>&gt; <strong>[/Source:</strong>&lt;<em>source</em>&gt;<strong>] [/LimitAccess]</strong></p></td>
<td align="left">Adds a capability to an image.
<p>Example:</p><p><strong>Dism /Online /Add-Capability /CapabilityName:Language.Basic~~~en-US~0.0.1.0</strong></p>
<div class="alert">
<strong>Note</strong>  DISM checks for the source files in the following order:
<ol>
<li>If <strong>/Source</strong> is specified, DISM looks in the specified locations first.</li>
<li>If <strong>/Source</strong> is not specified, or if the source files are not found in the specified locations, DISM checks to see if a group policy is set. If it is, DISM checks the locations specified by the group policy.</li>
<li>If the files still aren&#39;t found, and if DISM is working against an online image, and if <strong>/LimitAccess</strong> is not specified, it looks for the files on Windows Update.</li>
</ol>
</div>
<div>
 
</div>
<p><strong>/Source</strong>: Allows you to choose a location, such as a server, where the capability source files are located. You can use multiple <strong>/Source</strong> arguments.</p>
<p>Example:</p><p><strong>Dism /Online /Add-Capability /CapabilityName:Language.Basic~~~en-US~0.0.1.0 /Source:\server\share /Source:\server2\share</strong></p>
<p><strong>/LimitAccess</strong>: Tells DISM to not check Windows Update or Windows Server Update Services for the capability source files.</p>
<p>Example:</p><p><strong>Dism /Online /Add-Capability /CapabilityName:Language.Basic~~~en-US~0.0.1.0 /Source:\server\share /LimitAccess</strong></p></td>
</tr>
<tr class="even">
<td align="left"><strong>/Get-Capabilities</strong></td>
<td align="left"><p>Get capabilities in the image.</p><p>Example:</p>
<p><strong>DISM /Online /Get-Capabilities</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>/Get-CapabilityInfo</strong></p> 
<p><Strong>/CapabilityName:</strong>&lt;<em>capability_name</em>&gt;</p></td>
<td align="left"><p>Get information about a specific capability.</p><p>Example:</p>
<p><strong>DISM /Online /Get-CapabilityInfo
 /CapabilityName:Language.Basic</del>~en-US~0.0.1.0</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>/Remove-Capability</strong></p>
<p><strong>/CapabilityName:</strong>&lt;<em>capability_name</em>&gt;</p></td>
<td align="left"><p>Example:</p><p><strong>Dism /Online /Remove-Capability /CapabilityName:Language.Basic~~~en-US~0.0.1.0</strong></p><p>Example:</p>
<p><strong>Dism /Image:C:\test\offline /Remove-Capability /CapabilityName:Language.Basic</del>~en-US~0.0.1.0</strong></p></td>
</tr>
</tbody>
</table>

 

## <span id="related_topics"></span>Related topics


[Features On Demand](features-on-demand-v2--capabilities.md)

[DISM - Deployment Image Servicing and Management Technical Reference for Windows](dism---deployment-image-servicing-and-management-technical-reference-for-windows.md)

[What is DISM?](what-is-dism.md)

[DISM Global Options for Command-Line Syntax](dism-global-options-for-command-line-syntax.md)

[DISM Operating System Package Servicing Command-Line Options](dism-operating-system-package-servicing-command-line-options.md)

[DISM Languages and International Servicing Command-Line Options](dism-languages-and-international-servicing-command-line-options.md)

 

 






