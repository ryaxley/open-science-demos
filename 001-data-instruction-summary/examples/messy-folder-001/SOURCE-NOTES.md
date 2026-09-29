# The fictional messy folder behind the example

**This folder does not exist. The study is invented.** It is designed to be
realistically messy in the ways real folders are messy — the example
`manifest.jsonld` next to this file is what the Data Instruction Summary
generator should produce from it.

## Folder layout (imagined)

```
castillo-oddball-pilot/
├── raw/
│   ├── session_log_v2_FINAL.csv      # 1,204 rows — the "current" data
│   ├── session_log_v1.csv            # 312 rows — older export, different column names
│   └── mystery_file.dat              # 0.4 MB — nobody remembers what this is
├── processed/
│   └── summary by group.xlsx         # spaces in the filename; one sheet, "Sheet1"
└── notes/
    ├── README.txt                    # half-finished, ends mid-sentence
    └── protocol_v3.pdf               # methods, scanned, not OCR'd
```

## What's wrong with it (the good stuff)

1. **Two versions of the same log, different schemas.** v1 uses
   `subject, date, group, rt, acc`; v2 uses `subj_id, session_date, grp,
   rt_ms, correct`. Same measurements, renamed columns. Are `grp` values
   `A/B` the same groups as v1's `ctrl/trt`? Unresolved.
2. **Mixed date formats.** v2 has `2024-03-01` and `03/01/2024` in the same
   column. March 1 or January 3? Unresolvable without the lab.
3. **`mystery_file.dat`.** Binary, ~0.4 MB, no extension hint, no notes.
   Honest role: `unknown`.
4. **The README gives up halfway.** Last line: "TODO: ask Priya about the
   exclusion criteria for".
5. **The Excel file has spaces in its name** and a default sheet name —
   cosmetic, but the kind of thing that breaks scripts.

## Honesty notes on the example manifest

- `sha256` values are **omitted**, not faked. A hand-built example must not
  invent checksums; the slice-2 scanner fills them mechanically.
- `sizeBytes` and `tabular` row/column counts are the imagined values from
  this note, marked as human-supplied until the scanner verifies them.
- Every ambiguity above appears in the manifest's `ambiguities[]` array.
  Nothing was tidied up to make the example look better than the folder.
