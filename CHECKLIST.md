# Migration Checklist (Windows Sticky Notes → 1Password)

## Pre-flight
- [ ] 1Password desktop app installed
- [ ] 1Password CLI installed (`op --version`)
- [ ] CLI Integration enabled in 1Password desktop settings
- [ ] Signed in to 1Password (`op whoami`)
- [ ] Confirm target vault name (e.g., `Personal`)

## Export
- [ ] Locate Sticky Notes database (Windows 11)
- [ ] Copy DB to a working folder (do not operate on the live DB)
- [ ] Run export script
- [ ] Verify exported JSON count matches expected

## Clean + Canonicalize
- [ ] Build “clean import JSON” (titles normalized)
- [ ] Verify no data loss: spot-check 10 random notes

## Template Build (recommended)
- [ ] Generate per-item templates (`templates/note_###.json`)
- [ ] Validate a sample template imports correctly

## Import
- [ ] Import templates with rate-limit protection
- [ ] Verify count imported equals expected
- [ ] Spot-check bodies: verify full note text preserved

## Post-import
- [ ] Tag imported notes consistently (`sticky-notes`, `import-YYYY-MM-DD`)
- [ ] Archive or delete previous bad imports (only after verification)
