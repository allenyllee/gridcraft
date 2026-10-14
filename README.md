# Fixed picture save/reopen evidence

Created 2026-10-14 by @allenyllee. Original synthetic values, PNG pixels and drawing extents were generated in Rust; no company/personnel workbook, vendor sample, font file or source implementation was used. The native captures were retained from the completed local investigation, not newly composed images. Captures are original window backing pixmaps, never resized.

Files: synthetic-original.xlsx has a fixed 320 x 160-pixel absolute image at (96,216) pixels. before-save.xlsx was saved by the previous GridCraft 0.6.1 writer; after-save.xlsx was saved by the corrected writer. Every file has exactly the six synthetic strings listed in privacy-audit.json, one original solid magenta PNG, no macros/external links. PNG bytes match in all three files.

All LibreOffice captures use 24.2.7.2, GNOME X11, desktop100%, same read-only profile/worksheet view settings, macros/link updates disabled, UsePrinterMetrics=false. A25 selected, first row/column visible. Public UNO model geometry and original screen pixels measured:

| File | Width / height (1/100 mm, Size API) | X / Y (1/100 mm) | PNG screen pixels at 50 / 100 / 150% |
|---|---|---|---|
| Original | 8466 / 4232 | 2540 / 5715 | 153x80 / 309x160 / 465x240 |
| Previous writer save | 9990 / 4232 | 3048 / 5715 | 181x80 / 364x160 / 548x240 |
| Fixed writer save | 8466 / 4232 | 2540 / 5715 | 153x80 / 309x160 / 465x240 |

UNO Transformation rounds the original/fixed extent to8467 x4233 (approximately320 x160px). The reference's independent3-4% horizontal screen mapping difference remains; compare original/before/after in the SAME application, not literal screen pixels across products. This fixes actual saved physical size/position, independent of the Linux display-scale PR.

The GridCraft Chinese-reopen capture is from the actually installed local combined0.6.1 build, retaining the separate CJK, Linux1.0 scale, EMF and Chinese-notice fixes. It demonstrates the saved synthetic file, not the source PR's inclusion of those unrelated changes. The source PR is directly based on official main84acf6293b1dc1fc09837524e035d674eb4d6741 and contains only fixed drawing export work.

Isolated GridCraft control was private to its Flatpak namespace, task-only file grants and unchanged permanent network/broad-filesystem denies. LibreOffice used separate task profiles/local named-pipe UNO. All owned controls were stopped. No private original workbook was opened by these tests.
