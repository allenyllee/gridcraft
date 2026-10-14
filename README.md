# Synthetic GridCraft XLSX reproduction

All cells, picture pixels and relationship XML in `synthetic-bitmap-emf.xlsx` are generated
from scratch by the accompanying Rust `bitmap_emf_repro` example. No company/personnel data,
private workbook, private source path, vendor picture or font file is included.

Fixture SHA256: `6f15e7aa122c945eaf96e31d5ae21f5d01f1a399f96ddbd93ae73e62f231f85e`.
Its only external target is `https://example.invalid/synthetic-source.xlsx`; no formula uses it.

- `before-synthetic.png`: actual GUI built from unmodified official main
  `84acf6293b1dc1fc09837524e035d674eb4d6741` (0.6.1), showing the modal note and gray picture.
- `after-synthetic.png`: the EMF/import-note fix on that baseline; four colored quadrants and
  the nonblocking explicit external-update notice.
- `after-reopen-synthetic.png`: saved synthetic copy reopened, with picture still visible.
- `after-chinese-with-font-fix.png`: **combined integration preview** including this fix and
  the separate pending CJK font-path PR #1236 (`938097f5b697568f3bb5b0eed6e69cb0e61e9c4b`).
  The font-path changes are not included in the source PR for this XLSX fix.

The captures show only the app window with synthetic data. An accidental keyboard edit was
discarded; the file was reloaded and captures repeated. Saving/reopening preserves the original
synthetic cell strings and embedded image bytes. Tests use a private Flatpak network namespace,
exact task-directory grants and a task-local UI profile. Host loopback cannot connect to control,
and the test controls are closed afterward. Permanent isolation overrides remain unchanged.

External links are preserved but not read or automatically updated. No enable/refresh action
is implemented. EMF support is limited to complete single-bitmap uncompressed DIB metafiles;
arbitrary vector EMF/WMF remains unsupported.

Generated fixture/pixel artwork: original @allenyllee contribution under MIT OR Apache-2.0,
matching the source repository. Screenshots document GridCraft's open-source UI; no Office UI
or vendor artwork is copied into the source PR. This separate evidence branch keeps binary
screenshots and fixture downloads out of the source PR.
