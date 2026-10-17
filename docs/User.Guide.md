# Portal Commander user guide

> **0.3.0 documentation.** These pages describe Portal Commander 0.3.0. Earlier versions, such as 0.2.0, may have different or missing controls.

## Version scope

| Item | Reviewed baseline |
| --- | --- |
| App source baseline | `17ccb87` (tag `v0.3.0`) |
| Package version | `0.3.0` |
| Documentation reviewed | 2026-10-17 |
| Release | `0.3.0`, tagged `v0.3.0` |

This pass updated the version labels and scope. The feature pages were not re-checked against the installed 0.3.0 build.

Portal Commander is the name from 0.3.0; earlier releases and notes use Portal File Manager. Version 0.3.0 is the current release: its [release notes](../release-notes/0.3.0.md) list what changed. Earlier versions: [0.2.0](../release-notes/0.2.0.md) and [0.1.0](../release-notes/0.1.0.md).

## Find a feature

| Guide | Contents |
| --- | --- |
| [Panels and navigation](Features.Panels.md) | Addresses, sorting, filters, visibility, favorites and status |
| [File operations](Features.FileOperations.md) | Copy, move, rename, delete, clipboard and archives |
| [Folder sizes](Features.FolderSizes.md) | Calculation, cancellation, cache, partial totals and skipped folders |
| [Cloud folders](Features.Cloud.md) | Detection, cached previews, explicit downloads and limitations |
| [Viewers and editing](Features.Viewers.md) | Text, PDF, images, search, zoom and rotation |
| [Settings](Features.Settings.md) | Appearance, exclusions, Settings.ini, import and export |
| [Keyboard shortcuts](Features.Shortcuts.md) | Layouts, default keys and opened-file controls |
| [Documentation versioning](Docs.Versioning.md) | Development labels and release snapshots |

## Start here

Open a folder using an address bar, disk button or favorite. Select files in the source panel; the other panel is the destination for panel-to-panel copy and move. Each panel's toolbar controls its own view and visibility.

The shortcut panel follows the active panel. It changes to file controls while a viewer/editor is active. Its help button opens the full shortcut table for the chosen layout.

## Platform scope

The public installation instructions target Windows 10 and 11. Development source also contains Linux and macOS support; this guide does not certify equivalent native behavior on every OS. Shell integration, acrylic, cloud clients, mounts and installer availability need target-platform verification. Choosing an OS-styled window control does not establish native OS support.
