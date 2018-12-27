---
title: Windows System Image Manager User Interface Overview
description: Windows System Image Manager User Interface Overview
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 9672fce8-40ee-44f9-be21-cb367bb9a24d
ms.mktglfcycl: deploy
ms.sitesec: msdn


ms.date: 05/02/2017
ms.topic: article


---
# Windows System Image Manager User Interface Overview

The Windows System Image Manager (Windows SIM) user interface contains a series of panes. You can use these panes to open Windows image (.**wim**) files, create unattended answer files, and then add components and packages to the respective configuration passes in an answer file.

The following screen shot illustrates the Windows SIM user interface.

![windows sim user interface](images/dep-win8-l-wsim-screenshot.gif)

## <a href="" id="-simpanes"></a>Windows SIM Panes

### Distribution Share Pane

The **Distribution Share** pane displays the currently open distribution share folder in tree view. You can select, create, explore, and close distribution share folders by selecting the top node and then right-clicking in the pane. You can add items in an open distribution share folder to an answer file by right-clicking the item. For more information, see [Distribution Shares and Configuration Sets Overview](distribution-shares-and-configuration-sets-overview.md).

### Answer File Pane

The **Answer File** pane displays the Windows Setup configuration passes, the settings to apply in each pass, and the packages to install. You can open and change an existing answer file, validate the settings in an answer file against a Windows image, or create a new answer file. For more information, see [Answer Files Overview](answer-files-overview.md).

### Windows Image Pane

The **Windows Image** pane displays the currently open Windows image in tree view. When the tree is expanded, all of the components and packages for the image are visible and available to add to an answer file in the **Answer File** pane. For more information, see [Windows Image Files and Catalog Files Overview](windows-image-files-and-catalog-files-overview.md).

### Properties Pane

The **Properties** pane displays the properties and settings of a selected component or package. You can use the **Properties** pane to change the settings, and, in the case of packages, Windows feature selections. At the bottom of the **Properties** pane, Windows SIM displays the name of the setting and the associated **Microsoft® .NET** type. For more information, see [Component Settings and Properties Reference](component-settings-and-properties-reference.md).

### Messages Pane

The **Messages** pane consists of three tabs: **XML**, **Validation**, and **Configuration Set**. Clicking a tab in the **Messages** pane displays the type of message, a description, and the location of the issue.

The types of messages that the **Messages** pane displays are informational. Messages appear on the **Configuration Set** tab if a configuration set has been created. For more information, see [Distribution Shares and Configuration Sets Overview](distribution-shares-and-configuration-sets-overview.md).

## <a href="" id="-simmenu"></a>Windows SIM Menus

### File Menu

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Menu command</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>New Answer File</strong></p></td>
<td><p>Creates a new answer file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Open Answer File</strong></p></td>
<td><p>Opens an existing answer file.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Close Answer File</strong></p></td>
<td><p>Closes the currently open answer file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Save Answer File</strong></p></td>
<td><p>Saves the currently open answer file.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Save Answer File As…</strong></p></td>
<td><p>Opens a dialog box to enable naming of the answer file with which you are currently working.</p></td>
</tr>
<tr class="even">
<td><p><strong>Select Distribution Share</strong></p></td>
<td><p>Opens a valid distribution share folder.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Close Distribution Share</strong></p></td>
<td><p>Closes the currently open distribution share folder.</p></td>
</tr>
<tr class="even">
<td><p><strong>Select Windows Image</strong></p></td>
<td><p>Browses to and selects a Windows image file.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Close Windows Image</strong></p></td>
<td><p>Closes the currently open Windows image file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Exit</strong></p></td>
<td><p>Closes Windows SIM.</p></td>
</tr>
</tbody>
</table>

### Edit Menu

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Menu command</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Cut</strong></p></td>
<td><p>Deletes the highlighted text or tree structure (<strong>Unattend</strong> and <strong>Properties</strong>).</p></td>
</tr>
<tr class="even">
<td><p><strong>Copy</strong></p></td>
<td><p>Copies the highlighted text or tree structure (all panes).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Paste</strong></p></td>
<td><p>Pastes text or tree structure (<strong>Unattend</strong> and <strong>Properties</strong>).</p></td>
</tr>
<tr class="even">
<td><p><strong>Delete</strong></p></td>
<td><p>Deletes the currently selected item or text. (This command may be disabled if the item is not removable.)</p></td>
</tr>
<tr class="odd">
<td><p><strong>Find</strong></p></td>
<td><p>Opens a search dialog box to scan a Windows image and answer file, distribution share, or message for a specific item.</p></td>
</tr>
<tr class="even">
<td><p><strong>Revert Change</strong></p></td>
<td><p>Reverts the most recent customization.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Write Image Value</strong></p></td>
<td><p>Writes the value of the setting in the currently open Windows image to the answer file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Add to Answer File</strong></p></td>
<td><p>For components, a submenu opens that shows the available passes. The item and its children are added to the Unattend.xml answer file. Packages are automatically added to the packages section of the Unattend.xml answer file.</p></td>
</tr>
</tbody>
</table>

### Insert Menu

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Menu command</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Synchronous Command</strong></p></td>
<td><p>Adds a synchronous command to a configuration pass. You can select the <strong>windowsPE</strong>, <strong>specialize</strong>, <strong>auditUser</strong>, or <strong>oobeSystem</strong> configuration pass. After you select a configuration pass, a window opens so that you can specify the command line and the order of execution.</p></td>
</tr>
<tr class="even">
<td><p><strong>Driver Path</strong></p></td>
<td><p>Adds a driver path to a configuration pass. You can use <strong>Driver Path</strong> to select the configuration pass in which to add the driver path. <strong>Driver Path</strong> then opens a window where you can select a file or folder.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Package(s)</strong></p></td>
<td><p>Opens a window where you can browse to the location of a package. Then, it inserts a package from a file or folder into the currently open answer file.</p></td>
</tr>
</tbody>
</table>

### Tools Menu

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Menu command</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Hide Sensitive Data</strong></p></td>
<td><p>Stores local account passwords in an answer file as unreadable text. Domain passwords, product keys, and other sensitive data are not hidden.</p></td>
</tr>
<tr class="even">
<td><p><strong>Validate Answer File</strong></p></td>
<td><p>Validates the XML and other settings in the answer file. Settings are validated against the currently open Windows image.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Create Configuration Set</strong></p></td>
<td><p>Generates a new configuration set.</p></td>
</tr>
<tr class="even">
<td><p><strong>Explore Distribution Share</strong></p></td>
<td><p>Opens a distribution share folder in Windows Explorer or File Explorer view.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Create Distribution Share</strong></p></td>
<td><p>Creates a distribution share folder and subfolders.</p></td>
</tr>
<tr class="even">
<td><p><strong>Import Package(s)</strong></p></td>
<td><p>Enables you to browse to a folder that contains a package, and then import it into the currently open distribution share. For more information, see <a href="add-packages-to-a-distribution-share.md" data-raw-source="[Add Packages to a Distribution Share](add-packages-to-a-distribution-share.md)">Add Packages to a Distribution Share</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Create Catalog</strong></p></td>
<td><p>Generates a catalog file. For more information, see <a href="open-a-windows-image-or-catalog-file.md" data-raw-source="[Open a Windows Image or Catalog File](open-a-windows-image-or-catalog-file.md)">Open a Windows Image or Catalog File</a>.</p></td>
</tr>
</tbody>
</table>

### Help Menu

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Menu command</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Image Manager Help</strong></p></td>
<td><p>Displays the User&#39;s Guide.</p></td>
</tr>
<tr class="even">
<td><p><strong>Unattended Reference</strong></p></td>
<td><p>Displays the Unattended Windows Setup Reference.</p></td>
</tr>
<tr class="odd">
<td><p><strong>About</strong></p></td>
<td><p>Displays version, copyright, and licensing information.</p></td>
</tr>
</tbody>
</table>

## <a href="" id="-simbuttons"></a>Windows SIM Buttons

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Button name</th>
<th>Function</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>New Answer File</strong></p></td>
<td><p>Creates a new answer file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Open Answer File</strong></p></td>
<td><p>Opens an existing answer file.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Close Answer File</strong></p></td>
<td><p>Closes the currently selected answer file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Save Answer File</strong></p></td>
<td><p>Saves the currently open answer file.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cut, Copy, Paste, Delete</strong></p></td>
<td><p>Manipulates data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Find</strong></p></td>
<td><p>Enables you to search through a Windows image and answer file, through a distribution share, or within the <strong>Messages</strong> pane.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Validate Answer File</strong></p></td>
<td><p>Validates the answer file against the settings in the opened catalog file.</p></td>
</tr>
<tr class="even">
<td><p><strong>Create Configuration Set</strong></p></td>
<td><p>Creates a configuration set.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Help Contents</strong></p></td>
<td><p>Displays the User&#39;s Guide.</p></td>
</tr>
</tbody>
</table>

## Related topics

[Windows System Image Manager Scenarios Overview](windows-system-image-manager-scenarios-overview.md)

[Windows System Image Manager Overview Topics](windows-system-image-manager-overview-topics.md)
