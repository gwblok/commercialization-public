---
title: PlaylistManager Methods
description: PlaylistManager Methods
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/hardware'
ms.assetid: 3C266330-1712-4CE1-937C-8E012754857F


ms.date: 10/15/2017
ms.topic: article


---

# PlaylistManager Methods


## <span id="Public_Methods"></span><span id="public_methods"></span><span id="PUBLIC_METHODS"></span>Public Methods


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="playlistmanager-createplaylist-method.md" data-raw-source="[CreatePlaylist](playlistmanager-createplaylist-method.md)">CreatePlaylist</a></p></td>
<td><p>Creates a Playlist file from this <a href="playlistmanager-class.md" data-raw-source="[PlaylistManager](playlistmanager-class.md)">PlaylistManager</a>&#39;s Project instance.</p></td>
</tr>
<tr class="even">
<td><p><a href="playlistmanager-deserializeplaylist-method.md" data-raw-source="[DeserializePlaylist](playlistmanager-deserializeplaylist-method.md)">DeserializePlaylist</a></p></td>
<td><p>Deserializes a playlist file into a <a href="playlist-class.md" data-raw-source="[Playlist](playlist-class.md)">Playlist</a> object.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Equals</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="even">
<td><p><strong>GetHashCode</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="odd">
<td><p><a href="playlistmanager-getmissingtests-method.md" data-raw-source="[GetMissingTests](playlistmanager-getmissingtests-method.md)">GetMissingTests</a></p></td>
<td><p>Uses the given <a href="playlist-class.md" data-raw-source="[Playlist](playlist-class.md)">Playlist</a> to find tests for each <a href="target-class.md" data-raw-source="[Target](target-class.md)">Target</a> in the current <a href="playlistmanager-class.md" data-raw-source="[PlaylistManager](playlistmanager-class.md)">PlaylistManager</a>&#39;s Project that should be present but are not.</p>
<div class="alert">
<strong>Warning</strong>  This method is being deprecated.
</div>
<div>
 
</div></td>
</tr>
<tr class="even">
<td><p><a href="playlistmanager-gettestsfromprojectthatmatchplaylist-method.md" data-raw-source="[GetTestsFromProjectThatMatchPlaylist](playlistmanager-gettestsfromprojectthatmatchplaylist-method.md)">GetTestsFromProjectThatMatchPlaylist</a></p></td>
<td><p>Retrieves the test from the current <a href="playlistmanager-class.md" data-raw-source="[PlaylistManager](playlistmanager-class.md)">PlaylistManager</a>&#39;s Project that match those in the Playlist.</p></td>
</tr>
<tr class="odd">
<td><p><a href="playlistmanager-gettestsinprojectnotinplaylist-method.md" data-raw-source="[GetTestsInProjectNotInPlaylist](playlistmanager-gettestsinprojectnotinplaylist-method.md)">GetTestsInProjectNotInPlaylist</a></p></td>
<td><p>Finds the tests that are in the <a href="playlistmanager-class.md" data-raw-source="[PlaylistManager](playlistmanager-class.md)">PlaylistManager</a>&#39;s Project but not in the given Playlist.</p>
<div class="alert">
<strong>Warning</strong>  This method is being deprecated.
</div>
<div>
 
</div></td>
</tr>
<tr class="even">
<td><p><strong>GetType</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="odd">
<td><p><a href="playlistmanager-isplaylistloaded-method.md" data-raw-source="[IsPlaylistLoaded](playlistmanager-isplaylistloaded-method.md)">IsPlaylistLoaded</a></p></td>
<td><p>Returns whether this <strong>PlaylistManager</strong>&#39;s <a href="project-class.md" data-raw-source="[Project](project-class.md)">Project</a> has a playlist applied.</p></td>
</tr>
<tr class="even">
<td><p><a href="playlistmanager-loadplaylist-method.md" data-raw-source="[LoadPlaylist](playlistmanager-loadplaylist-method.md)">LoadPlaylist</a></p></td>
<td><p>Loads the tests from a Playlist into this <a href="playlistmanager-class.md" data-raw-source="[PlaylistManager](playlistmanager-class.md)">PlaylistManager</a>&#39;s <a href="project-class.md" data-raw-source="[Project](project-class.md)">Project</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToString</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="even">
<td><p><a href="playlistmanager-unloadplaylist-method.md" data-raw-source="[UnloadPlaylist](playlistmanager-unloadplaylist-method.md)">UnloadPlaylist</a></p></td>
<td><p>Unloads the current playlist from this <a href="project-class.md" data-raw-source="[Project](project-class.md)">Project</a>.</p></td>
</tr>
</tbody>
</table>

 

## <span id="Protected_Methods"></span><span id="protected_methods"></span><span id="PROTECTED_METHODS"></span>Protected Methods


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Finalize</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
<tr class="even">
<td><p><strong>MemberwiseClone</strong></p></td>
<td><p>(Inherited from <strong>Object</strong>)</p></td>
</tr>
</tbody>
</table>

 

 

 






