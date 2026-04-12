# Monitoring and Backup Proofs README

## Purpose
This folder stores proof related to operational visibility, security-oriented monitoring, backup artifacts, and restore readiness.

Its purpose is to centralize evidence showing:
- monitoring is operational
- critical hosts or services are visible
- useful events or logs can be observed
- backup artifacts exist
- restore-oriented validation has been considered

These proofs support both resilience and defensive credibility.

## Expected Content
This folder may contain:
- monitoring dashboard screenshots
- monitored host screenshots
- monitored service screenshots
- event visibility captures
- backup artifact screenshots
- backup command outputs
- restore notes or restore validation outputs

## Recommended File Types
Typical file formats may include:
- `.png`
- `.jpg`
- `.txt`
- `.log`

## Recommended Naming Convention
Use clear filenames such as:
- `MON01_wazuh_dashboard.png`
- `MON02_monitored_hosts.png`
- `MON03_monitored_services.png`
- `MON04_event_visibility.png`
- `BKP01_backup_artifact_exists.png`
- `BKP02_backup_command_output.txt`
- `BKP03_restore_validation.txt`

## Quality Rules
Each proof should:
- show one meaningful monitoring or backup fact
- be readable
- be linked to a service, host, or backup scope item
- avoid exposing secrets
- support testing, Blue Team analysis, or final presentation

## Notes
This folder is essential for proving that the infrastructure is not only deployed, but also observable and recoverable.