# Slice 1 design notes — manifest schema (2026-09-29)

## The one big decision

**The manifest is the single source of truth. The other three outputs are rendered views of it.**

- `fields[]` renders to `DATA-DICTIONARY.md` (slice 3)
- top-level metadata + `provenance` renders to `README.md` (slice 5)
- `ambiguities[]` + schema-validation gaps render to `validation-report.md` (slice 4)

One thing to get right, three things generated for free. If the manifest is wrong, every view is wrong in the same way — which is exactly what you want from a source of truth.

## Vocabulary discipline

Everything that has a standard term uses the standard term: schema.org `Dataset`, `creator`, `variableMeasured`-adjacent `fields`, `distribution`-adjacent `files`. Meemir-specific housekeeping (`status`, `generator`, `manifestVersion`) lives under one `meemir` object so the standard surface stays clean. If we ever map to DCAT or LinkML, the translation is mechanical.

## Ambiguities are first-class

The most important array in the schema is `ambiguities`. A data instruction summary that can't say "I don't know" is marketing, not documentation. Each ambiguity has a severity, what it affects, and an optional resolution — so the validation report can show open vs. resolved over time. This is the append-only decision record idea, in miniature.

## What's deliberately missing (for later slices)

- `sizeBytes`, `sha256`, `tabular` — filled mechanically by the folder scanner (slice 2), not by hand.
- Rendering logic — slices 3–5.
- Cross-study linkage — that's Level 2, explicitly deferred.

## Validation

The example manifest in `examples/messy-folder-001/` was checked against this schema by hand for slice 1. Machine validation of manifests against the schema becomes part of slice 2's scanner.
