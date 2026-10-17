# Folder sizes

> [Development documentation and version scope](User.Guide.md#version-scope).

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

Completed totals and timestamps are saved on disk and restored after restart. Saved totals do not disappear merely because they are old; they can be displayed while automatic calculation revalidates them in the background. Partial/skipped results are not stored as complete cached totals. There is no cache-duration option in Settings.

Parent scans also reuse previously calculated child-folder totals while they are still valid. A reused child's contents are not traversed again; files directly inside the parent and uncached portions are still examined. A child total already includes its descendants, so those totals are not added a second time. Cloud, link and filesystem-boundary safeguards apply before child-cache reuse.

When a parent combines cached children, its timestamp retains the oldest reused total. This prevents repeated parent scans from delaying revalidation of that child. The displayed timestamp therefore may be older than the parent request itself.

The backend uses a one-hour reuse window before requesting another scan during automatic calculation. This is an internal revalidation policy, not timed deletion of saved data. Revalidation occurs when automatic sizing requests a folder; disabled automatic sizing does not scan simply because an hour passes. The implementation uses normal filesystem reads on Windows, Linux and macOS, without system-journal dependencies. A folder's unchanged timestamp is not treated as proof that all descendants are unchanged.

External changes may make a cached total inaccurate before revalidation. A result describes a point in time, not a live quota. It is not a measure of physical disk allocation or compression savings.
