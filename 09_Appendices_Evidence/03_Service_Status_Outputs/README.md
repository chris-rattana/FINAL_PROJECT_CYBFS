# Service Status Outputs README

## Purpose
This folder stores raw outputs proving that core services are installed, running, and reachable in their intended role.

Its purpose is to centralize technical proof such as:
- service state
- listening ports
- readiness checks
- process confirmation
- component availability

These outputs support deployment validation and technical review.

## Expected Content
This folder may contain:
- `systemctl status` outputs
- service readiness outputs
- `ss -tulpen` or equivalent listening-port outputs
- database readiness checks
- web service status outputs
- file-sharing service status outputs
- monitoring service status outputs

## Recommended File Types
Typical file formats may include:
- `.txt`
- `.log`
- `.png`

## Recommended Naming Convention
Use clear filenames such as:
- `STAT01_nginx_status.txt`
- `STAT02_postgresql_status.txt`
- `STAT03_samba_status.txt`
- `STAT04_nextcloud_service_status.txt`
- `STAT05_wazuh_status.txt`
- `STAT06_listening_ports_web.txt`

## Quality Rules
Each output should:
- be tied to one clear service or host
- include enough context to be understandable
- remain clean and readable
- avoid unnecessary noise
- avoid exposing sensitive secrets

## Notes
Prefer raw text outputs when possible, because they are easier to reuse in technical documentation and case evidence.