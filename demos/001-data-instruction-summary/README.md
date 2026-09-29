# Demo 001 — Data Instruction Summary generator

**Status:** specified. Build begins 2026-09-30.

## Problem

Research data usually arrives as a folder of files with the context locked in someone's head — or in a lab notebook, or nowhere. That missing context is what makes data hard to reuse, hard to validate, and invisible to AI-assisted discovery.

## What it does

Takes a messy folder of research data files and emits a complete instruction summary:

1. `manifest.jsonld` — machine-readable, typed, linked metadata
2. `DATA-DICTIONARY.md` — one crisp entry per field and file
3. `README.md` — provenance, license, how to cite
4. `validation-report.md` — what's missing or ambiguous, stated plainly

## Design decisions, evaluation, failure mode

_To be written as the build proceeds — honesty is part of the demo._
