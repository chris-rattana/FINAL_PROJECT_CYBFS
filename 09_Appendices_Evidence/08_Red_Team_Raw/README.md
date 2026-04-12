# Red Team Raw Materials README

## Purpose
This folder stores raw and supporting materials used during the Red Team workstream.

Its purpose is to centralize technical content that supports the offensive review but does not need to appear directly in the main Red Team engagement files.

These materials help preserve traceability, offensive context, and supporting detail.

## Expected Content
This folder may contain:
- raw reachability tests
- raw scan outputs
- denied-path outputs
- firewall observation dumps
- raw service response captures
- offensive comparison notes
- retest raw outputs
- supporting screenshots not directly indexed in the main Red Team evidence file

## Recommended File Types
Typical file formats may include:
- `.txt`
- `.log`
- `.png`
- `.md`

## Recommended Naming Convention
Use clear filenames such as:
- `RT01_port_scan_raw.txt`
- `RT02_db_reachability_test.txt`
- `RT03_admin_path_test.txt`
- `RT04_remote_access_notes.txt`
- `RT05_retest_scan_comparison.txt`

## Quality Rules
Each file should:
- support a real offensive observation
- remain readable and relevant
- be easy to reference from findings, remediation, or retest
- avoid unnecessary duplication with the main Red Team engagement
- avoid exposing secrets or confidential values

## Notes
This folder is for supporting offensive material. The final Red Team logic should still remain centered in the structured engagement files under `06_Red_Team/`.