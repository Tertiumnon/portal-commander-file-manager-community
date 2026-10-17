# Settings and persistence

> [Unreleased documentation and version scope](User.Guide.md#version-scope).

Open the settings-icon menu and choose Settings. Changes save automatically. About is in the same menu and contains application information and links.

## Settings popup

| Area | Options |
| --- | --- |
| Appearance | Theme, font/size, icon pack, acrylic and background opacity |
| Interface | Window-control style, shortcut layout/panel, scale and favorite labels |
| File operations | Panel refresh, multiple-opening delay, in-panel extensions, delete confirmation and word wrap |
| File visibility | Editable excluded-folder rules only |
| Storage | Custom cloud roots, hidden disks, disk/trash display and refresh, folder-size cache duration |
| User settings | Export, import and restoring popup defaults |

Acrylic and opacity are independent. Background opacity applies across the app while text/icons remain opaque. Native acrylic availability depends on the OS; Linux transparency depends on the desktop compositor.

## Excluded folders

Enter one exact folder name per line, applying at any depth. Windows path matching is case-insensitive; Unix matching is case-sensitive. Paths and general glob expressions are not accepted. The special `found.###` rule matches exactly three digits only at a Windows drive root, such as `C:\found.001`.

The initial list includes dependency/cache locations such as `node_modules`, `.next`, `.gradle` and `__pycache__`, plus OS housekeeping names. Edit or remove rules to suit your work. Recovery folders may contain recovered files; exclusions never delete anything.

Each panel's Show excluded folders toolbar toggle controls matching folders. Dot, hidden and system filters still apply. Editing rules refreshes both panels without changing their separate toggle states.

## Settings.ini

Settings.ini is stored in the OS application-configuration directory. Its exact path depends on the OS and application identifier. Export provides a readable copy without guessing the installed path.

| Saved key | Contents |
| --- | --- |
| `preferences` | Shared popup options, exclusions and cloud roots |
| `panel0_options` | Left panel's view, sorting/direction, visibility, previews, folders-on-top, automatic sizes and status display |
| `panel1_options` | The same choices for the right panel, independently |
| `panelHistory` | Panel locations and navigation history |
| `favorites`, `favoriteLabels`, `favoriteIcons` | Pinned paths and custom appearance |

INI values are JSON-quoted strings; some contain another JSON object. Preserve escaping when manually editing. Close the app first so an automatic save cannot overwrite edits, and keep a backup.

There are no global visibility checkboxes in Settings. Toolbar choices survive restart; absent saved choices use the application's initial states. Restoring popup defaults preserves panel visibility choices, favorites and history, but resets shared exclusion rules and other popup preferences.

Export writes a settings file. Import validates a file, asks before replacing settings and reloads the app. Import is blocked during an active file operation. Back up the current configuration before replacing it.
