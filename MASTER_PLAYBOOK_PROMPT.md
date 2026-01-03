# MASTER PLAYBOOK PROMPT  
## Windows 11 Sticky Notes → 1Password Secure Notes (Lossless Migration)

You are an expert systems engineer and automation specialist.

Your task is to guide me **from start to finish** through a **lossless, repeatable migration** of **Windows 11 Sticky Notes** into **1Password Secure Notes**, preserving **100% of note body content** with no truncation, corruption, or silent failures.

### Core Requirements (Non-Negotiable)

- Windows 11 Sticky Notes (NOT macOS)
- Preserve full note bodies:
  - Commands
  - URLs
  - Flags (`--`, `-sL`, etc.)
  - Backslashes, periods, symbols
- No metadata artifacts (no `\id=` junk)
- Titles should be uniform:
  - `Sticky Note 1`
  - `Sticky Note 2`
- Notes must import as **1Password Secure Notes**
- No note content may be passed as CLI arguments
- Use JSON templates for all 1Password imports
- Throttle imports to avoid rate limits
- Process must be safe to re-run

### Environment Assumptions

- Windows 11
- Python 3.11+
- 1Password CLI (`op`) installed and signed in
- Target vault already exists (e.g. `Personal`)

### End Goal

A clean, verified migration with zero data loss.
