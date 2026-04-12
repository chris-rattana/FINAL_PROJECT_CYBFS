# Firewall and Port Proofs README

## Purpose
This folder stores proof related to network exposure, firewall rules, and reachable versus blocked service paths.

Its purpose is to centralize evidence showing:
- firewall protection is active
- only intended ports are reachable
- backend services are protected
- administrative paths are restricted
- blocked paths remain blocked

These proofs are critical for deployment validation, Blue Team review, and Red Team assessment.

## Expected Content
This folder may contain:
- firewall status outputs
- firewall rule exports
- port scan results
- listening-port outputs
- denied connection tests
- proof of intended allowed service reachability
- proof of blocked backend or admin paths

## Recommended File Types
Typical file formats may include:
- `.txt`
- `.log`
- `.png`

## Recommended Naming Convention
Use clear filenames such as:
- `FW01_web_firewall_status.txt`
- `FW02_db_firewall_status.txt`
- `FW03_allowed_web_port.png`
- `FW04_denied_db_direct_access.txt`
- `FW05_admin_path_denied.txt`
- `FW06_open_ports_scan.txt`

## Quality Rules
Each proof should:
- show one clear exposure or filtering fact
- be tied to a host or service
- distinguish allowed versus denied paths
- be easy to map to architecture expectations
- avoid unnecessary noise

## Notes
This folder is especially useful for proving that the trust-boundary model is enforced in practice.