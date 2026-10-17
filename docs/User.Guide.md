# Portal Commander user guide

> **0.3.0 — unreleased development documentation.** These pages describe the upcoming 0.3.0 release, not the published 0.2.0 installer. Some controls may be missing or different in 0.2.0.

## Version scope

| Item | Reviewed baseline |
| --- | --- |
| App source commit | `5dc125bcd260d9f230dffa4182631d14255c41ae` |
| Package version at review | `0.2.0` in development source; this does not establish release availability |
| Documentation reviewed | 2026-10-17 |
| Intended release | `0.3.0` — in development, not yet published |

Portal Commander is the development name. Earlier releases and notes use Portal File Manager. Version 0.2.0 is published; use its [release notes](../release-notes/0.2.0.md) for released behavior. The [0.1.0 notes](../release-notes/0.1.0.md) cover the first preview. The [0.3.0 notes](../release-notes/0.3.0.md) describe the upcoming release and remain subject to review.

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
