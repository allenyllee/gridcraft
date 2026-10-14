# GridCraft Flatpak CJK rendering evidence

Captured 2026-10-14 by @allenyllee with synthetic spreadsheet data only.

- before-original-0.5.0.png: original official 0.5.0 GUI binary, opened the Chinese test workbook inside the isolated Flatpak.
- after-local-0.5.0-fix.png: locally rebuilt 0.5.0 GUI with the CJK host-font path fix, after saving, quitting, and reopening in a fresh process.

Both use the freedesktop 25.08 runtime on GNOME X11. Network sharing and broad filesystem access were disabled; private sandbox control was stopped after capture. These are not screenshots of the latest main build.

The application UI is from https://github.com/storytold/gridcraft (MIT OR Apache-2.0); ArtCraft brand elements remain subject to its brand licence. No proprietary application or customer data is pictured.

This evidence branch is independent of the source-fix PR and adds no bundled fonts or binaries to its diff.
