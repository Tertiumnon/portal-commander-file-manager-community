# Viewers and text editing

> [Documentation and version scope](User.Guide.md#version-scope).

The filename, Edit/Save actions and Close button share a header above the tools. The footer shows the opened file's size and mode information. The shortcut panel follows the active file.

## Open and close

In the default layout, Enter opens configured supported extensions in the panel; other files can open in their associated application. Next/previous-file navigation can display an icon-only preview for unsupported files without executing them. Opening keys can differ with the layout.

Ctrl+Q or Escape closes an opened file. Unsaved text changes require confirmation before discarding. In read-only mode, Alt+Page Down/Up or Alt+mouse wheel moves through files in the visible list's order, stopping at its boundaries.

## Text

Text opens read-only; F4 or Edit enables editing. Large files require confirmation, and binary files are refused as text. UTF variants and detected legacy encodings are supported. Saving preserves encoding, byte-order mark and line endings; unrepresentable characters produce an error instead of silent conversion.

Ctrl+F opens Find (Cmd+F for the macOS layout). Previous/next arrows move through matches; icon toggles control match case, regular expressions and whole words. Ctrl+H opens replacement controls and enables editing if needed. Replacements remain unsaved edits until saved.

Word wrap is shared and persisted: its viewer toggle and Settings option stay synchronized across text panels.

## PDF

PDFs open fitted to width. Width/height buttons choose the fit mode. Zoom buttons, Ctrl+/− and Ctrl+mouse wheel change scale; the macOS layout also supports Command zoom. Manual zoom stays fixed on resize until a fit mode is chosen again.

Arrow and Page Up/Down keys navigate within the focused viewer. Ctrl+F opens document search; Enter/Shift+Enter step through matches, and Escape closes search. Font rendering also depends on the document and its embedded fonts.

## Images

Choose whole-image, width or height fit. Zoom with buttons or modifier+mouse wheel. Drag to pan when scaled dimensions exceed the viewport. Fit modes respond to resizing and rotation; manual zoom stays fixed.

Rotate left/right to preview a change. Save rotation asks before replacing the original. Re-encoding can affect quality or metadata; keep a backup when those matter. Viewing support does not imply rotation saving for every format or animated image.
