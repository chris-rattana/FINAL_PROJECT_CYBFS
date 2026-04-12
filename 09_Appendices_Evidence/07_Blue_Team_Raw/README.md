# Blue Team Raw Materials README

## Purpose
This folder stores raw and supporting materials used during the Blue Team workstream.

Its purpose is to centralize technical content that supports the defensive review but does not need to appear directly in the main Blue Team case files.

These materials help preserve context, traceability, and supporting detail.

## Expected Content
This folder may contain:
- raw log excerpts
- raw command outputs
- longer service outputs
- raw monitoring extracts
- backup-related notes
- raw configuration excerpts
- defensive review notes
- supporting screenshots not directly indexed in the main Blue Team evidence file

## Recommended File Types
Typical file formats may include:
- `.txt`
- `.log`
- `.png`
- `.md`

## Recommended Naming Convention
Use clear filenames such as:
- `BT01_auth_log_excerpt.txt`
- `BT02_firewall_rules_web.txt`
- `BT03_monitoring_event_excerpt.png`
- `BT04_backup_validation_notes.txt`
- `BT05_defensive_review_notes.md`

## Quality Rules
Each file should:
- support a real Blue Team observation
- remain readable and relevant
- be easy to reference from findings or remediation
- avoid unnecessary duplication with the main Blue Team case
- avoid exposing secrets or confidential values

## Notes
This folder is for supporting material. The final Blue Team logic should still remain centered in the structured case files under `05_Blue_Team/`.