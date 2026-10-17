# File operations

> [Unreleased documentation and version scope](User.Guide.md#version-scope).

Select files in the active panel. Shift extends a range; Ctrl or the applicable platform modifier changes a multiple selection. Panel-to-panel Copy and Move use the other panel's folder as their destination. Files can also be dragged between panels.

| Operation | Behavior |
| --- | --- |
| Copy / Move | Progress shows items, bytes and the current file; existing destinations require a replacement decision |
| Clipboard | Copy/paste files, including supported system file-clipboard contents |
| New file / New folder | Create an entry in the current folder |
| Rename | Rename the selected entry and retain its selection |
| Delete | Send entries to system Trash; confirmation follows the delete-confirmation setting |
| Archive / Extract | Use supported external archivers such as 7-Zip or WinRAR when installed and available |
| Context menu | File actions, path copying and supported native shell actions |

Transfers validate paths to reject unsafe overlaps. A failure can leave some items already transferred; inspect the refreshed panels and error before retrying. Cancellation or failure does not imply rollback of every completed item.

Opening or copying an online-only file may download it through its sync client. A transfer can spend time waiting for content before byte progress advances. [Cloud handling](Features.Cloud.md) explains how explicit operations differ from automatic previews.

While a file is open inside a panel, viewer shortcuts replace folder commands. Close the viewer to return to ordinary file operations. See [shortcuts](Features.Shortcuts.md) for layout-dependent keys.
