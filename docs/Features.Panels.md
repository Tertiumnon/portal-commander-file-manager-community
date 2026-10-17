# Panels and navigation

> [Unreleased documentation and version scope](User.Guide.md#version-scope).

## Navigate

Each panel has an address bar above its toolbar. Back, Forward and Refresh control that panel. Click a path segment to visit an ancestor, or enter a path and use the navigation button. Copy path copies the address and shows a success message.

Local paths and network locations are supported. Network access can depend on OS mounting and authentication. The parent row goes up a folder. Each panel keeps its history and reopens its saved location when available.

The right-panel toggle switches between one and two panels. Narrow layouts can stack panels. The active panel determines which selection keyboard commands act on.

## List, sort and filter

Choose List, Small icons, Large icons or Very large icons. Previews have a separate toggle. Filter narrows the current folder's visible entries; it is not recursive disk search.

List headers sort by name, size or modified time. Clicking the current header reverses direction. Folders always on top is independent of direction. Name-sorted navigation displays names before background metadata. Size/date sorting waits for metadata before publishing the new list, avoiding an intermediate order; slow folders can take longer.

Directory changes are watched or checked periodically. Changed entries are merged where possible, preserving unchanged previews and selection. A slow listing shows a loading overlay; failed navigation keeps the previous folder.

## Visibility

| Toggle | Controls |
| --- | --- |
| Show dot files | Names beginning with a dot; these use this toggle instead of the hidden toggle |
| Show hidden files | Other entries marked hidden by the OS |
| Show system files | Entries marked as system by the OS |
| Show excluded folders | Folder names in the editable exclusion list |

Filters combine: showing excluded folders does not override dot/system filtering. Exclusions do not hide ordinary files with the same name. See [exclusion rules](Features.Settings.md#excluded-folders).

Views, visibility, sorting, folders-on-top, automatic sizes and the status display are saved independently for both panels in Settings.ini. Visibility states are not global popup checkboxes.

## Top bar and status

Disk buttons visit their roots; Trash opens the system trash. Compact layouts retain disk paths while hiding some details. Hide disks in Settings removes selected disks from the strip without restricting access to their paths.

Favorites pin folders, support custom labels/icons and drag reordering, and move excess items to the adjacent `...` menu. Clicking an open overflow trigger closes it. Toolbar tools also use overflow when they no longer fit.

The settings-icon menu contains Settings and About. The logo and unused top-bar space support native window dragging. Window controls can use Windows or macOS styling.

The panel footer shows item count and size. Its status button switches between a dot and progress bar; progress describes that panel's activity, including metadata, previews and scans.
