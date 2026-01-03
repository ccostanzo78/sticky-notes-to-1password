# Windows 11 Sticky Notes → 1Password Secure Notes

This repository provides a **lossless, production-safe workflow** to migrate **Windows 11 Sticky Notes** into **1Password Secure Notes** while preserving **100% of note body content**.

## Why This Exists

Bulk imports via CLI often fail due to:
- CLI flag parsing
- Periods, slashes, and symbols in note bodies
- Rate limiting
- Truncated content

This approach avoids all of that by using **JSON templates only**.

## What You Get

- Uniform titles (`Sticky Note 1`, `Sticky Note 2`, …)
- Full body preservation
- Secure Note category
- Repeatable and auditable process

## Requirements

- Windows 11
- Python 3.11+
- 1Password CLI (`op`)
- Signed in to 1Password
- Target vault exists

## High-Level Flow

1. Extract Sticky Notes from `plum.sqlite`
2. Export to raw JSON
3. Convert into 1Password Secure Note templates
4. Import templates with throttling
5. Verify content in 1Password

## Status

✔ Tested  
✔ Proven  
✔ Safe to re-run  

This is the recommended approach for long-term archival and migration.
