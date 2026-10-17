# Folder sizes

> [Documentation and version scope](User.Guide.md#version-scope).

Enable **Automatic folder sizes** in a panel's toolbar. A confirmation appears before enabling it. The app calculates listed folders in the background, prioritizing visible folders. Both panels share a scan queue rather than starting unrestricted parallel recursive scans.

Disabling the toggle or navigating away cancels that panel's pending work. When both panels request the same scan, cancelling one does not cancel the other's request. The toggle state is saved per panel.

## Read the result

| Display | Meaning |
| --- | --- |
| `250 MB` | Complete total at calculation time; it may subsequently become stale |
| `≥ 250 MB` | At least 250 MB was counted, but part of the tree was skipped or unreadable |
| Dash | No calculated total, or a skipped/unavailable location; hover for the available reason |
| Cloud icon | A recognized cloud folder has no calculated size or its automatic scan was skipped |

`≥` is a lower bound, not an estimate of the missing amount. Readable files may total 250 MB while a protected subfolder's contents remain unknown.

Hover over a calculated size to see its timestamp and whether it is incomplete. The tooltip identifies a partial total; it does not enumerate every skipped child.

## Skipped locations

Automatic scans skip drive roots, detected network locations and recognized/configured cloud roots. They do not follow symbolic links, junctions or cloud placeholders. Inaccessible entries, metadata failures and boundaries to other filesystems can also be skipped. A skipped child makes an otherwise counted parent's total incomplete.

The toolbar's excluded-folder list affects visibility only. It is not a recursive scan-exclusion policy: an excluded child may contribute to its parent's total if safely readable.

## Cache

Completed totals and timestamps are saved on disk and restored after restart. Saved totals do not disappear merely because they are old; totals for folders that no longer exist are removed when the cache file is compacted. Partial totals are saved too and shown with `≥` until they are recalculated, so a folder keeps its size after you navigate away. Skipped results are not stored. There is no cache-duration option in Settings.

Each time a folder is opened with automatic sizes on, its total is rebuilt from its direct files and its children's saved totals, so navigating back to a folder whose children were already measured does not rescan them. A child without a saved total is scanned in full. Saved totals are shown until the rebuild finishes, and the result then replaces them.

Cloud folders are never measured: they are not queued, and their contents are never read. The implementation uses normal filesystem reads on Windows, Linux and macOS, without system-journal dependencies.

External changes can make a total inaccurate between opening the folder and the next scan. A result describes a point in time, not a live quota. It is not a measure of physical disk allocation or compression savings.
