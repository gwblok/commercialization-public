---
title: Powercfg command-line options
description: You can use the powercfg.exe tool to control power schemes (also named power plans) to use the available sleep states, to control the power states of individual devices, and to analyze the system for common energy-efficiency and battery-life problems.
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 6A6E2E98-2B6B-4C58-B0F9-A28B650383CF

ms.date: 10/27/2017
ms.topic: article


---

# Powercfg command-line options

Use powercfg.exe to control *power plans*&mdash;also called *power schemes*&mdash;to use the available sleep states, to control the power states of individual devices, and to analyze the system for common energy-efficiency and battery-life problems.


## Syntax

Powercfg command lines use the following syntax:

<p style="margin: .8em 0 0 1.5em;"><strong>powercfg</strong>&nbsp;&nbsp;<strong>/</strong><em>option</em>&nbsp; [<em>arguments</em>&nbsp;]&nbsp; [&nbsp;<strong>/?</strong>]</p>

where <em>option</em> is one of the options listed in the following table, and <em>arguments</em> is one or more arguments that apply to the selected option. Including <strong>/?</strong> in a command line displays help for the specified option. Options and arguments are described in more detail later in this topic.<br/><br/>

<a id="options_table"/>
## List of command-line options

<table>
<thead>
<tr>
<th bgcolor="EEEEEE">Option</th>
<th bgcolor="EEEEEE">Description</th>
</thead>
<tbody>
<tr>
<td><a href="#option_help">/?, -help</a></td>
<td>Displays information about command-line parameters.</td>
</tr>
<tr>
<td><a href="#option_list">/list, /L</a></td>
<td>Lists all power schemes.</td>
</tr>
<tr>
<td><a href="#option_query">/query, /Q</a></td>
<td>Displays the contents of a power scheme.</td>
</tr>
<tr>
<td><a href="#option_change">/change, /X</a></td>
<td>Modifies a setting value in the current power scheme.</td>
</tr>
<tr>
<td><a href="#option_changename">/changename</a></td>
<td>Modifies the name and description of a power scheme.</td>
</tr>
<tr>
<td><a href="#option_duplicatescheme">/duplicatescheme</a></td>
<td>Duplicates a power scheme.</td>
</tr>
<tr>
<td><a href="#option_delete">/delete, /D</a></td>
<td>Deletes a power scheme.</td>
</tr>
<tr>
<td><a href="#option_deletesetting">/deletesetting</a></td>
<td>Deletes a power setting.</td>
</tr>
<tr>
<td><a href="#option_setactive">/setactive, /S</a></td>
<td>Makes a power scheme active on the system.</td>
</tr>
<tr>
<td><a href="#option_getactivescheme">/getactivescheme</a></td>
<td>Retrieves the currently active power scheme.</td>
</tr>
<tr>
<td><a href="#option_setacvalueindex">/setacvalueindex</a></td>
<td>Sets the value associated with a power setting while the system is powered by AC power.</td>
</tr>
<tr>
<td><a href="#option_setdcvalueindex">/setdcvalueindex</a></td>
<td>Sets the value associated with a power setting while the system is powered by DC power.</td>
</tr>
<tr>
<td><a href="#option_import">/import</a></td>
<td>Imports all power settings from a file.</td>
</tr>
<tr>
<td><a href="#option_export">/export</a></td>
<td>Exports a power scheme to a file.</td>
</tr>
<tr>
<td><a href="#option_aliases">/aliases</a></td>
<td>Displays all aliases and their corresponding GUIDs.</td>
</tr>
<tr>
<td><a href="#option_getsecuritydescriptor">/getsecuritydescriptor</a></td>
<td>Gets a security descriptor associated with a specified power setting, power scheme, or action.</td>
</tr>
<tr>
<td><a href="#option_setsecuritydescriptor">/setsecuritydescriptor</a></td>
<td>Sets a security descriptor associated with a power setting, power scheme, or action.</td>
</tr>
<tr>
<td><a href="#option_hibernate">/hibernate, /H</a></td>
<td>Enables and disables the hibernate feature.</td>
</tr>
<tr>
<td><a href="#option_availablesleepstates">/availablesleepstates, /A</a></td>
<td>Reports the sleep states available on the system.</td>
</tr>
<tr>
<td><a href="#option_devicequery">/devicequery</a></td>
<td>Returns a list of devices that meet specified criteria.</td>
</tr>
<tr>
<td><a href="#option_deviceenablewake">/deviceenableawake</a></td>
<td>Enables a device to wake the system from a sleep state.</td>
</tr>
<tr>
<td><a href="#option_devicedisablewake">/devicedisablewake</a></td>
<td>Disables a device from waking the system from a sleep state.</td>
</tr>
<tr>
<td><a href="#option_lastwake">/lastwake</a></td>
<td>Reports information about what woke the system from the last sleep transition.</td>
</tr>
<tr>
<td><a href="#option_waketimers">/waketimers</a></td>
<td>Enumerates active wake timers.</td>
</tr>
<tr>
<td><a href="#option_requests">/requests</a></td>
<td>Enumerates application and driver Power Requests.</td>
</tr>
<tr>
<td><a href="#option_requestsoverride">/requestsoverride</a></td>
<td>Sets a Power Request override for a particular Process, Service, or Driver.</td>
</tr>
<tr>
<td><a href="#option_energy">/energy</a></td>
<td>Analyzes the system for common energy-efficiency and battery life problems.</td>
</tr>
<tr>
<td><a href="#option_batteryreport">/batteryreport</td>
<td>Generates a report of battery usage.</td>
</tr>
<tr>
<td><a href="#option_sleepstudy">/sleepstudy</a></td>
<td>Generates a diagnostic system power transition report.</td>
</tr>
<tr>
<td><a href="#option_srumutil">/srumutil</a></td>
<td>Dumps Energy Estimation data from System Resource Usage Monitor (SRUM).</td>
</tr>
<tr>
<td><a href="#option_systemsleepdiagnostics">/systemsleepdiagnostics</a></td>
<td>Generates a diagnostic report of system sleep transitions.</td>
</tr>
<tr>
<td><a href="#option_systempowerreport">/systempowerreport</a></td>
<td>Generates a diagnostic system power transition report.</td>
</tr>
</tbody>
</table>
<br/>


## Descriptions of command-line options

<p>The following sections describe Powercfg command-line options and arguments.</p>

<br/>
<h3 id="option_help"><strong>-help</strong> or <strong>/?</strong></h3>
<p>Displays information about command-line parameters.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/?</strong></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_list"><strong>/list</strong> or <strong>/L</strong></h3>
<p>Lists all power schemes.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/list</strong></p>
<!--<p>Examples:</p>
<code>powercfg /list</code>-->
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_query"><strong>/query</strong> or <strong>/Q</strong></h3>
<p>Displays the contents of the specified power scheme.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/query</strong>&nbsp; [<em>scheme_GUID</em>&nbsp; [<em>sub_GUID</em>&nbsp;]]</p>
<p>If neither the parameter <em>scheme_GUID</em> or <em>sub_GUID</em> are provided, the settings of the current active power scheme are displayed. If the parameter <em>sub_GUID</em> is not specified, all settings in the specified power scheme are displayed.</p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>scheme_GUID</em></dt>
<dd>Specifies a power scheme GUID. Running <strong>powercfg /list</strong> returns a power scheme GUID.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>sub_GUID</em></dt>
<dd>Specifies a power-setting subgroup GUID. A power setting subgroup GUID is returned by running <strong>powercfg /query</strong>.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /query<br/>
powercfg /query 381b4222-f694-41f0-9685-ff5bb260df2e 238c9fa8-0aad-41ed-83f4-97be242c8f20</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_change"><strong>/change</strong> or <strong> /X</strong></h3>
<p>Modifies a setting value in the current power scheme.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>/change</strong>&nbsp; <em>setting</em>&nbsp; <em>value</em>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>setting</em></dt>
<dd>Specifies one of the following options:
<ul>
<li><strong>monitor-timeout-ac</strong></li>
<li><strong>monitor-timeout-dc</strong></li>
<li><strong>disk-timeout-ac</strong></li>
<li><strong>disk-timeout-dc</strong></li>
<li><strong>standby-timeout-ac</strong></li>
<li><strong>standby-timeout-dc</strong></li>
<li><strong>hibernate-timeout-ac</strong></li>
<li><strong>hibernate-timeout-dc</strong></li>
</ul>
</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>value</em></dt>
<dd>Specifies the new value, in minutes.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /change monitor-timeout-ac 5</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_changename"><strong>/changename</strong></h3>
<p>Modifies the name of a power scheme and optionally its description.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/changename</strong>&nbsp; <em>scheme_GUID</em>&nbsp; <em>name</em>&nbsp; [<em>description</em>&nbsp;]</p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>scheme_GUID</em></dt>
<dd>Specifies a power scheme GUID. Running <strong>powercfg /list</strong> returns a power scheme GUID.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>name</em></dt>
<dd>Specifies the power scheme&#39;s new name.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>description</em></dt>
<dd>Specifies the power scheme&#39;s new description. If no description is specified, only the name is changed.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /changename 381b4222-f694-41f0-9685-ff5bb260df2e &quot;Customized Balanced&quot;</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_duplicatescheme"><strong>/duplicatescheme</strong></h3>
<p>Duplicates the specified power scheme. The resulting GUID which represents the new scheme is displayed.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/duplicatescheme</strong>&nbsp; <em>scheme_GUID</em>&nbsp; [<em>destination_GUID</em>&nbsp;]</p>
<p>Arguments:</p>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>scheme_GUID</em></dt>
<dd>Specifies a power scheme GUID. A power scheme GUID is returned by running <strong>powercfg /list</strong>.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>destination_GUID</em></dt>
<dd>Specifies the new power scheme&#39;s GUID. If no GUID is specified, a new GUID is created.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /duplicatescheme 381b4222-f694-41f0-9685-ff5bb260df2e</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_delete"><strong>/delete</strong> or <strong>/D</strong></h3>
<p>Deletes the power scheme with the specified GUID.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/delete</strong>&nbsp; <em>scheme_GUID</em></p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>scheme_GUID</em></dt>
<dd>Specifies a power scheme GUID. A power scheme GUID is returned by running <strong>powercfg /list</strong>.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /delete 381b4222-f694-41f0-9685-ff5bb260df2e</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_deletesetting"><strong>/deletesetting</strong></h3>
<p>Deletes a power setting.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/deletesetting</strong>&nbsp; <em>sub_GUID</em>&nbsp; <em>setting_GUID</em></p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>sub_GUID</em></dt>
<dd>Specifies a power setting subgroup GUID. A power setting subgroup GUID is returned by running <strong>powercfg /query</strong>.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>setting_GUID</em></dt>
<dd>Specifies a power setting GUID. A power setting GUID is returned by running <strong>powercfg /query</strong>.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /deletesetting 238c9fa8-0aad-41ed-83f4-97be242c8f20 29f6c1db-86da-48c5-9fdb-f2b67b1f44da</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_setactive"><strong>/setactive</strong> or <strong>/S</strong></h3>
<p>Makes the specified power scheme active on the system.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/setactive</strong>&nbsp; <em>scheme_GUID</em></p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>scheme_GUID</em></dt>
<dd>Specifies a power scheme GUID. A power scheme GUID is returned by running <strong>powercfg /list</strong>.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /setactive 381b4222-f694-41f0-9685-ff5bb260df2e</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_getactivescheme"><strong>/getactivescheme</strong></h3>
<p>Retrieves the currently active power scheme.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/getactivescheme</strong></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_setacvalueindex"><strong>/setacvalueindex</strong></h3>
<p>Sets the value associated with a specified power setting while the system is powered by AC power.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/setacvalueindex</strong>&nbsp; <em>scheme_GUID</em>&nbsp; <em>sub_GUID</em>&nbsp; <em>setting_GUID</em>&nbsp; <em>setting_index</em></p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>scheme_GUID</em></dt>
<dd>Specifies a power scheme GUID. A power scheme GUID is returned by running <strong>powercfg /list</strong>.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>sub_GUID</em></dt>
<dd>Specifies a power setting subgroup GUID. Running <strong>powercfg /query</strong> returns a power setting subgroup GUID.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>setting_GUID</em></dt>
<dd>Specifies a power setting GUID. A power setting GUID is returned by running <strong>powercfg /query</strong>.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>setting_index</em></dt>
<dd>Specifies which possible value this setting is set to. A list of possible values is returned by running <strong>powercfg /query</strong>.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /setacvalueindex 381b4222-f694-41f0-9685-ff5bb260df2e 238c9fa8-0aad-41ed-83f4-97be242c8f20 29f6c1db-86da-48c5-9fdb-f2b67b1f44da 0</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_setdcvalueindex"><strong>/setdcvalueindex</strong></h3>
<p>Sets the value associated with a specified power setting while the system is powered by DC power.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/setdcvalueindex</strong>&nbsp; <em>scheme_GUID</em>&nbsp; <em>sub_GUID</em>&nbsp; <em>setting_GUID</em>&nbsp; <em>setting_index</em></p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>scheme_GUID</em></dt>
<dd>Specifies a power scheme GUID. A power scheme GUID is returned by running <strong>powercfg /list</strong>.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>sub_GUID</em></dt>
<dd>Specifies a power setting subgroup GUID. A power setting subgroup GUID is returned by running <strong>powercfg /query</strong>.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>setting_GUID</em></dt>
<dd>Specifies a power setting GUID. A power setting GUID is returned by running <strong>powercfg /query</strong>.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>setting_index</em></dt>
<dd>Specifies which possible value this setting is set to. A list of possible values is returned by running <strong>powercfg /query</strong>.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /setdcvalueindex 381b4222-f694-41f0-9685-ff5bb260df2e 238c9fa8-0aad-41ed-83f4-97be242c8f20 29f6c1db-86da-48c5-9fdb-f2b67b1f44da 300</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_import"><strong>/import</strong></h3>
<p>Imports a power scheme from the specified file.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/import</strong>&nbsp; <em>file_name</em>&nbsp; [<em>GUID</em>&nbsp;]</p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>file_name</em></dt>
<dd>Specifies a fully-qualified path to a file returned by running <strong>powercfg /export</strong>.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>GUID</em></dt>
<dd>Specifies the GUID for the imported scheme. If no GUID is specified, a new GUID is created.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /import c:\scheme.pow</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_export"><strong>/export</strong></h3>
<p>Exports a power scheme, represented by the specified GUID, to the specified file.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/export</strong>&nbsp; <em>file_name</em>&nbsp; <em>GUID</em></p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>file_name</em></dt>
<dd>Specifies a fully-qualified path to a destination file.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>GUID</em></dt>
<dd>Specifies a power scheme GUID. A power scheme GUID is returned by running <strong>powercfg /list</strong>.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /export c:\scheme.pow 381b4222-f694-41f0-9685-ff5bb260df2e</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_aliases"><strong>/aliases</strong></h3>
<p>Displays a list of aliases and their corresponding GUIDs. These aliases may be used instead of a GUID in any command.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/aliases</strong></p>
<!--<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /aliases</code></p>-->
<div class="alert"><strong>Note</strong>&nbsp;&nbsp;
<p>Some settings do not contain aliases. For a full list of GUIDs, use <strong>powercfg /query</strong>.</p>
</div>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_getsecuritydescriptor"><strong>/getsecuritydescriptor</strong></h3>
<p>Gets the security descriptor associated with the specified power setting, power scheme, or action.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/getsecuritydescriptor</strong>&nbsp; <em>GUID</em>&nbsp;|&nbsp;<em>action</em></p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>GUID</em></dt>
<dd>Specifies a power scheme or a power setting GUID. A power scheme GUID is returned by running <strong>powercfg /list</strong>. A power setting GUID is returned by running <strong>powercfg /query</strong>.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>action</em></dt>
<dd>Specifies one of the following actions:
<ul>
<li><strong>ActionSetActive</strong></li>
<li><strong>ActionCreate</strong></li>
<li><strong>ActionDefault</strong></li>
</ul>
</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /getsecuritydescriptor 381b4222-f694-41f0-9685-ff5bb260df2e<br />
powercfg /getsecuritydescriptor ActionSetActive</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_setsecuritydescriptor"><strong>/setsecuritydescriptor</strong></h3>
<p>Sets a security descriptor associated with the specified power setting, power scheme, or action.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/setsecuritydescriptor</strong>&nbsp; <em>GUID</em>&nbsp;|&nbsp;<em>action</em>&nbsp; <em>SDDL</em></p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>GUID</em></dd>
<dd>Specifies a power scheme or a power setting GUID. A power scheme GUID is returned by running <strong>powercfg /list</strong>. A power setting GUID is returned by running <strong>powercfg /query</strong>.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>action</em></dt>
<dd>Specifies one of the following actions:
<ul>
<li><strong>ActionSetActive</strong></li>
<li><strong>ActionCreate</strong></li>
<li><strong>ActionDefault</strong></li>
</ul>
</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>SDDL</em></dd>
<dd>Specifies a valid security descriptor string in SDDL format. An example SDDL string can be obtained by running <strong>powercfg /getsecuritydescriptor</strong>.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /setsecuritydescriptor 381b4222-f694-41f0-9685-ff5bb260df2e O:BAG:SYD:P(A;CI;KRKW;;;BU)(A;CI;KA;;;BA)(A;CI;KA;;;SY)(A;CI;KA;;;CO)<br />
<br />
powercfg /setsecuritydescriptor ActionSetActive O:BAG:SYD:P(A;CI;KR;;;BU)(A;CI;KA;;;BA)(A;CI;KA;;;SY)(A;CI;KA;;;CO)</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_hibernate"><strong>/hibernate</strong> or <strong>/h</strong></h3>
<p>Enables or disables the hibernate feature; also, sets the hiberfile size.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/hibernate</strong></p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/hibernate</strong>&nbsp; [<strong>on</strong>&nbsp;|&nbsp;<strong>off</strong>]</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/hibernate</strong>&nbsp; [&nbsp;<strong>/size</strong>&nbsp; <em>percent_size</em>&nbsp;]</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/hibernate</strong>&nbsp; [&nbsp;<strong>/type</strong>&nbsp; <em>reduced</em>&nbsp;|&nbsp;<em>full</em>&nbsp;]</p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>On</strong></dt>
<dd>Enables the hibernate feature.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>Off</strong></dt>
<dd>Disables the hibernate feature.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/size</strong> <em>percent_size</em></dt>
<dd>Specifies the desired hiberfile size as a percentage of the total memory size. The default size cannot be smaller than 50. This parameter also causes hibernation to be enabled.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/type</strong> <em>reduced</em>&nbsp;|&nbsp;<em>full</em></dt>
<dd>Specifies the desired hiberfile type. A reduced hiberfile only supports hiberboot.
<div class="alert"><strong>Note</strong>&nbsp;&nbsp;&nbsp;A hiberfile that has a custom default size, or HiberFileSizePercent &gt;= 40, is considered as a full hiberfile. HiberFileSizePercent is set in the registry in HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power.
<p>To change the hiberfile type to reduced, the OS has to manage the default hiberfile size. To do this, run the following commands:</p>
<p><strong>powercfg /hibernate /size 0</strong></p>
<p><strong>powercfg /hibernate /type reduced</strong></p>
</div>
</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /hibernate off<br /> powercfg /hibernate /size 100<br /> powercfg /hibernate /type reduced</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_availablesleepstates"><strong>/availablesleepstates</strong> or <strong>/A</strong></h3>
<p>Reports the sleep states available on the system. Attempts to report reasons why sleep states are unavailable.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/availablesleepstates</strong></p>
<!--<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /availablesleepstates</code></p>-->
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_devicequery"><strong>/devicequery</strong></h3>
<p>Returns a list of devices that meet the specified criteria.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/devicequery</strong>&nbsp; <em>query_flag</em></p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>query_flag</em></dt>
<dd>Specifies one of the following criteria:
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>wake_from_S1_supported</strong></dt>
<dd>Returns all devices that support waking the system from a light sleep state.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>wake_from_S2_supported</strong></dt>
<dd>Returns all devices that support waking the system from a deeper sleep state.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>wake_from_S3_supported</strong></dt>
<dd>Returns all devices that support waking the system from the deepest sleep state.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>wake_from_any</strong></dt>
<dd>Returns all devices that support waking the system from any sleep state.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>S1_supported</strong></dt>
<dd>Lists devices supporting light sleep.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>S2_supported</strong></dt>
<dd>Lists devices supporting deeper sleep.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>S3_supported</strong></dt>
<dd>Lists devices supporting deepest sleep. S4_supported List devices supporting hibernation.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>wake_programmable</strong></dt>
<dd>Lists devices that are user-configurable to wake the system from a sleep state.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>wake_armed</strong></dt>
<dd>Lists devices that are currently configured to wake the system from any sleep state.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>all_devices</strong></dt>
<dd>Returns all devices present in the system.</dd>
</dl>
</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /devicequery wake_armed</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_deviceenablewake"><strong>/deviceenableawake</strong></h3>
<p>Enables the specified device to wake the system from a sleep state.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/deviceenableawake</strong>&nbsp; <em>device_name</em></p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>device_name</em></dt>
<dd>Specifies a device. This device name may be retrieved using <strong>powercfg /devicequery wake_programmable</strong>.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /deviceenableawake &quot;Microsoft USB IntelliMouse Optical&quot;</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_devicedisablewake"><strong>/devicedisablewake</strong></h3>
<p>Disables the specified device from waking the system from a sleep state.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/devicedisablewake</strong>&nbsp; <em>device_name</em></p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>device_name</em></dt>
<dd>Specifies a device. This device name may be retrieved using <strong>powercfg /devicequery wake_armed</strong>.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /devicedisablewake &quot;Microsoft USB IntelliMouse Optical&quot;</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_lastwake"><strong>/lastwake</strong></h3>
<p>Reports information about what woke the system from the last sleep transition.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/lastwake</strong></p>
<!--
<p>Examples:</p>
<code>powercfg /lastwake</code>
-->
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_waketimers"><strong>/waketimers</strong></h3>
<p>Enumerates the active wake timers. If enabled, the expiration of a wake timer wakes the system from sleep and hibernate states.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/waketimers</strong></p>
<!--
<p>Examples:</p>
<code>powercfg /waketimers</code>
-->
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_requests"><strong>/requests</strong></h3>
<p>Enumerates application and driver Power Requests. Power Requests prevent the computer from automatically powering off the display or entering a low-power sleep mode.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/requests</strong></p>
<!--
<p>Examples:</p>
<code>powercfg /requests</code>
-->
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_requestsoverride"><strong>/requestsoverride</strong></h3>
<p>Sets a Power Request override for a particular process, service, or driver. If no parameters are specified, this command displays the current list of Power Request overrides.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/requestsoverride</strong>&nbsp; [<em>caller_type</em>&nbsp; <em>name</em>&nbsp; <em>request</em>&nbsp;]</p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>Caller_type</em></dt>
<dd>Specifies one of the following caller types: <strong>process</strong>, <strong>service</strong>, <strong>driver</strong>. This is obtained by running <strong>powercfg /requests</strong>.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>name</em></dt>
<dd>Specifies the caller name. This is the name returned by running <strong>powercfg /requests</strong>.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><em>request</em></dt>
<dd>Specifies one or more of the following Power Request types:
<ul>
<li><strong>Display</strong></li>
<li><strong>System</strong></li>
<li><strong>Awaymode</strong></li>
</ul>
</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /requestsoverride process wmplayer.exe display system</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_energy"><strong>/energy</strong></h3>
<p>Analyzes the system for common energy-efficiency and battery-life problems and generates a report, an HTML file, in the current path.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/energy</strong>&nbsp; [&nbsp;<strong>/output</strong>&nbsp; <em>file_name</em>&nbsp;]&nbsp; [&nbsp;<strong>/xml</strong>]&nbsp; [&nbsp;<strong>/duration</strong>&nbsp; <em>seconds</em>&nbsp;]</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/energy</strong>&nbsp; <strong>/trace</strong>&nbsp; [&nbsp;<strong>/d</strong>&nbsp; <em>file_path</em>&nbsp;]&nbsp; [&nbsp;<strong>/xml</strong>]&nbsp; [&nbsp;<strong>/duration</strong>&nbsp; <em>seconds</em>&nbsp;]</p>
<p>The <strong>/energy</strong> option should be used when the computer is idle and has no open programs or documents.</p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/output</strong> <em>file_name</em></dt>
<dd>Specify the path and file name to store the energy report HTML or XML file.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/xml</strong></dt>
<dd>Formats the report file as XML.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/duration</strong> <em>seconds</em></dt>
<dd>Specifies the number of seconds to observe system behavior. Default is 60 seconds.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/trace</strong></dt>
<dd>Records system behavior and does not perform analysis. Trace files are generated in the current path unless the <strong>/D</strong> parameter is specified.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/d</strong> <em>file_path</em></dt>
<dd>Specify the directory to store trace data. May only be used with the <strong>/trace</strong> parameter.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /energy<br />
powercfg /energy /output &quot;longtrace.html&quot; /duration 120</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_batteryreport"><strong>/batteryreport</strong></h3>
<p>Generates a report of battery usage characteristics over the lifetime of the system. Running <strong>powercfg /batteryreport</strong> generates an HTML report file in the current path.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/batteryreport</strong>&nbsp; [&nbsp;<strong>/output</strong>&nbsp; <em>file_name</em>&nbsp;]&nbsp; [&nbsp;<strong>/xml</strong>]</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/batteryreport</strong>&nbsp; [&nbsp;<strong>/duration</strong>&nbsp; <em>days</em>&nbsp;]</p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/output</strong> <em>file_name</em></dt>
<dd>Specify the path and file name to store the battery report HTML.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/output</strong> <em>file_name</em> <strong>/xml</strong></dt>
<dd>Formats the battery report file as XML.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/duration</strong> <em>days</em></dt>
<dd>Specifies the number of days to analyze for the report.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /batteryreport /output &quot;batteryreport.html&quot;<br />
powercfg /batteryreport /duration 4</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_sleepstudy"><strong>/sleepstudy</strong></h3>
<p>Generates a diagnostic report of modern standby quality over the last three days on the system. The report is a file that is saved in the current path.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/sleepstudy</strong>&nbsp; [&nbsp;<strong>/output</strong>&nbsp; <em>file_name</em>&nbsp;]&nbsp; [&nbsp;<strong>/xml</strong>]</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/sleepstudy</strong>&nbsp; [&nbsp;<strong>/duration</strong>&nbsp; <em>days</em>&nbsp;]</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/sleepstudy</strong>&nbsp; [&nbsp;<strong>/transformxmL</strong>&nbsp; <em>file_name.xml</em>&nbsp;]&nbsp; [&nbsp;<strong>/output</strong>&nbsp; <em>file_name.html</em>&nbsp;]</p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/output</strong> <em>file_name</em></p></dt>
<dd>Specify the path and file name to store the Sleepstudy report HTML.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/output</strong> <em>file_name</em> <strong>/xml</strong></p></dt>
<dd>Formats the Sleepstudy report file as XML.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/duration</strong> <em>days</em></p></dt>
<dd>Specifies the number of days to analyze for the report.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/transformxml</strong> <em>file_name.xml</em> <strong>/output</strong> <em>file_name.html</em></p></dt>
<dd>Transforms the Sleepstudy report from XML to HTML.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /sleepstudy /output &quot;sleepstudy.html&quot;<br />
powercfg /sleepstudy /duration 7</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_srumutil"><strong>/srumutil</strong></h3>
<p>Enumerates the entire Energy Estimation data from the System Resource Usage Monitor (SRUM) in an XML or CSV file.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/srumutil</strong>&nbsp; [&nbsp;<strong>/output</strong>&nbsp; <em>file_name</em>&nbsp;]&nbsp; [&nbsp;<strong>/xml</strong>]&nbsp; [&nbsp;<strong>/csv</strong>]</p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/output</strong> <em>file_name</em></dt>
<dd>Specify the path and file name to store the SRUM data.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/output</strong> <em>file_name</em> <strong>/xml</strong></dt>
<dd>Formats the file as XML.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/output</strong> <em>file_name</em> <strong>/csv</strong></dt>
<dd>Formats the file as CSV.</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /batteryreport /output &quot;srumreport.xml&quot; /xml</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_systemsleepdiagnostics"><strong>/systemsleepdiagnostics</strong></h3>
<p>Generates a report of intervals when the user was not present over the last three days on the system, and if the system went to sleep. This option generates a report, an HTML file, in the current path.</p>
<p>This command requires administrator privileges and must be executed from an elevated command prompt.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/systemsleepdiagnostics</strong>&nbsp; [<strong>/output</strong>&nbsp; <em>file_name</em>&nbsp;]&nbsp; [<strong>/xml</strong>&nbsp;]</p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/output</strong> <em>file_name</em></dt>
<dd>Specifies the path and file name of the diagnostics report.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/xml</strong></dt>
<dd>Save the report as an XML file.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/duration</strong> <em>days</em></dt>
<dd>Specifies the number of days to analyze for the report.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/transformxml</strong> <em>file_name</em></dt>
<dd>Produces a report in HTML from a report that was previously created in XML.
</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /systemsleepdiagnostics<br/>
powercfg /systemsleepdiagnostics /output &quot;system-sleep-diagnostics.html&quot;<br/>
powercfg /systemsleepdiagnostics /output &quot;system-sleep-diagnostics.xml&quot; /XML<br/>
powercfg /systemsleepdiagnostics /transformxml &quot;system-sleep-diagnostics.xml&quot;</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>


<br/>
<h3 id="option_systempowerreport"><strong>/systempowerreport</strong> or <strong>/spr</strong></h3>
<p>Generates a report of system power transitions over the last three days on the system, including connected standby power efficiency. This option generates a report, an HTML file, in the current path.</p>
<p>This command requires administrator privileges and must be executed from an elevated command prompt.</p>
<p>Syntax:</p>
<p style="margin: .5em 0 .5em 1.4em;"><strong>powercfg</strong>&nbsp; <strong>/getsecuritydescriptor</strong>&nbsp; <em>GUID</em>&nbsp;|&nbsp;<em>action</em></p>
<p>Arguments:</p>
<dl>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/output</strong> <em>file_name</em></dt>
<dd>Specifies the path and file name of the diagnostics report.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/xml</strong></dt>
<dd>Save the report as an XML file.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/duration</strong> <em>days</em></dt>
<dd>Specifies the number of days to analyze for the report.</dd>
<dt><p style="margin: .7em 0 .3em 1.4em;"><strong>/transformxml</strong> <em>file_name</em></dt>
<dd>Produces a report in HTML from a report that was previously created in XML.
</dd>
</dl>
<p>Examples:</p>
<p style="margin: .7em 0 0 1.5em;"><code>powercfg /systempowerreport<br/>
powercfg /systempowerreport /output &quot;sleepstudy.html&quot;<br/>
powercfg /systempowerreport /output &quot;sleepstudy.xml&quot; /XML<br/>
powercfg /systempowerreport /transformxml &quot;sleepstudy.xml&quot;</code></p>
<p><sup><a href="#options_table">Return to the top.</a></sup></p>
