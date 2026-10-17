# Cloud folders

> [Documentation and version scope](User.Guide.md#version-scope).

Portal browses cloud content through the local filesystem and installed sync client. It does not connect directly to provider account APIs or provide a universal cloud-account browser.

## Automatic protection

Detection includes common path names, registered Windows sync roots and configured custom roots. Native checks examine Windows offline/recall attributes, macOS dataless-file flags and detected remote mounts. Typical path names include OneDrive, Google Drive, Nextcloud, ownCloud, Dropbox and Apple's CloudStorage locations.

Background text/video previews and recursive folder-size scans are blocked for recognized protected locations. Image/PDF previews may use existing application or cached Windows shell thumbnails. Without an eligible cache entry, a regular file icon can appear.

The cloud icon in the size column indicates recognized cloud handling. It is not a provider sync-status indicator and does not confirm that every child is downloaded or synchronized.

## Custom locations

Use **Settings → Storage → Cloud folders** for renamed sync folders, unusual Nextcloud roots or virtual drives that detection misses. Enter one absolute path per line. Descendants are included; similarly prefixed siblings are not.

If startup cannot configure the native cloud policy, it reports an error and disables background previews/scans, while retaining browsing and explicit file operations. Editing roots refreshes preview state; outdated asynchronous results are ignored.

## Explicit access and limitations

Opening a file in a viewer/editor, launching its associated application, copying or saving can cause the sync client to download content. Background protection does not promise that explicit operations stay offline.

Clients differ in placeholder flags, mounts, authentication and downloads. Unknown custom locations need configuration and testing. Automated checks cover guard logic and simulated offline/cache cases; they do not establish compatibility with every live provider or native OS combination.
