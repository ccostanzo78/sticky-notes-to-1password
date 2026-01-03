# Troubleshooting

## 1Password CLI rate-limited (Too many requests)
**Symptom:** `Too many requests. Your client has been rate-limited. Try again in N seconds`
**Fix:** Add sleep/backoff between creates (e.g., 1–3 seconds + exponential backoff). Re-run only failed items.

## Desktop app timeout / CLI integration
**Symptom:** `connecting to desktop app timed out`
**Fix:**
- Ensure 1Password desktop is running
- Enable CLI integration in Settings
- Re-run `op whoami`

## PowerShell redirection issues (`<` reserved)
**Fix:** In PowerShell, feed stdin like this:
- Use `Get-Content file.json | op item create -`
- Or use `--template path\to\template.json`

## “assignment statement … more than 1 unescaped period”
**Cause:** You passed note content as assignment arguments instead of JSON template.
**Fix:** Import using JSON templates, not `field=value` assignments.

## UnicodeDecodeError / encoding
**Fix:**
- Read files with explicit encoding fallback (UTF-8 then UTF-16)
- Ensure output JSON is UTF-8

## Data loss risk (body truncated)
**Fix:** Only import notes via `notesPlain` using JSON template, not ad-hoc field assignment parsing.
Always spot-check 10 notes before deleting originals.
