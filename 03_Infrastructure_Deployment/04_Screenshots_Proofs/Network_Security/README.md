# Network Security Screenshots and Proofs Index

## Purpose
This document indexes the screenshots, command outputs, and technical proofs collected for the Network Security component of the project infrastructure.

Its purpose is to:
- identify which proofs were collected
- explain what each proof demonstrates
- support deployment validation
- support Blue Team and Red Team review
- support final documentation and presentation

This folder should contain evidence showing that network exposure is controlled, remote access is protected, backend services are restricted, administrative paths are limited, and firewall rules are aligned with the intended architecture.

## Evidence Collection Rules
The evidence stored in this folder should be:
- clearly named
- easy to understand without extra context
- linked to a validation objective
- reusable in deployment documentation and final presentation

Recommended naming style:
- `NET01_firewall_status_host1.png`
- `NET02_firewall_rules_host1.txt`
- `NET03_allowed_web_port.png`
- `NET04_denied_db_direct_access.png`
- `NET05_vpn_connection_success.png`
- `NET06_internal_resource_via_vpn.png`
- `NET07_admin_access_restricted.png`
- `NET08_open_ports_scan.png`
- `NET09_backend_isolation_proof.png`
- `NET10_denied_unapproved_path.png`

## Expected Proof Categories

## 1. Firewall Availability Proof
This category proves that firewall protection is active on critical hosts.

### Examples
- screenshot of firewall status
- command output showing active firewall service
- rule summary for the host

### Suggested Files
- `NET01_firewall_status_host1.png`
- `NET02_firewall_rules_host1.txt`

## 2. Allowed Service Exposure Proof
This category proves that intended user-facing services are reachable.

### Examples
- proof that the web service port is reachable
- screenshot of successful access to the intended exposed service
- validation that allowed traffic matches the architecture

### Suggested Files
- `NET03_allowed_web_port.png`
- `NET03_allowed_web_port.txt`

## 3. Backend Protection Proof
This category proves that backend services are not broadly exposed.

### Examples
- failed direct connection to the database from a non-approved path
- proof that internal services are not publicly reachable
- comparison between intended and actual exposure

### Suggested Files
- `NET04_denied_db_direct_access.png`
- `NET09_backend_isolation_proof.png`

## 4. VPN / Controlled Remote Access Proof
This category proves that remote access follows the intended protected path.

### Examples
- screenshot of successful VPN connection
- proof that internal resources become reachable only through VPN
- command output showing tunnel or assigned remote IP

### Suggested Files
- `NET05_vpn_connection_success.png`
- `NET06_internal_resource_via_vpn.png`
- `NET05_vpn_connection_success.txt`

## 5. Administrative Access Restriction Proof
This category proves that administrative services are not broadly exposed.

### Examples
- proof that SSH or admin port is reachable only from the approved path
- denied admin access from a non-approved path
- firewall rule excerpt for administrative restriction

### Suggested Files
- `NET07_admin_access_restricted.png`
- `NET07_admin_access_restricted.txt`

## 6. Port Exposure Review Proof
This category proves that only intended ports are open.

### Examples
- port scan result
- command output listing listening ports
- comparison against the expected architecture

### Suggested Files
- `NET08_open_ports_scan.png`
- `NET08_open_ports_scan.txt`

## 7. Denied Unapproved Path Proof
This category proves that one or more unintended paths are blocked.

### Examples
- failed connection to an internal service from an unauthorized path
- denied access to an admin path
- proof that a blocked service remains unreachable

### Suggested Files
- `NET10_denied_unapproved_path.png`
- `NET10_denied_unapproved_path.txt`

## Validation Mapping

| Proof ID | What It Demonstrates | Related Validation Area |
|----------|----------------------|-------------------------|
| NET01 | firewall protection is active | firewall validation |
| NET02 | rules are applied on the host | configuration validation |
| NET03 | intended exposed service is reachable | functional exposure validation |
| NET04 | direct backend access is denied | backend protection validation |
| NET05 | VPN access works | remote access validation |
| NET06 | internal resources are reachable through approved path | controlled access validation |
| NET07 | admin paths are restricted | admin security validation |
| NET08 | only intended ports are open | exposure validation |
| NET09 | backend isolation is effective | trust-boundary validation |
| NET10 | unapproved path is blocked | security control validation |

## Evidence Register Template

| File Name | Type | Description | Validation Use | Notes |
|-----------|------|-------------|----------------|-------|
| NET01_firewall_status_host1.png | Screenshot | Shows firewall is active on a critical host | firewall validation | To complete |
| NET02_firewall_rules_host1.txt | Text Output | Shows active firewall rules | configuration validation | To complete |
| NET03_allowed_web_port.png | Screenshot | Shows intended web port/path is reachable | functional exposure | To complete |
| NET04_denied_db_direct_access.png | Screenshot | Shows direct DB access is denied | backend protection | To complete |
| NET05_vpn_connection_success.png | Screenshot | Shows successful VPN connection | remote access validation | To complete |
| NET06_internal_resource_via_vpn.png | Screenshot | Shows internal resource accessible via approved path | controlled access | To complete |
| NET07_admin_access_restricted.png | Screenshot | Shows admin access is restricted | admin security | To complete |
| NET08_open_ports_scan.png | Screenshot | Shows actual open ports | exposure validation | To complete |
| NET09_backend_isolation_proof.png | Screenshot | Shows backend isolation logic works | trust-boundary validation | To complete |
| NET10_denied_unapproved_path.png | Screenshot | Shows blocked unauthorized path | security validation | To complete |

## Quality Rules for Screenshots and Proofs
Each proof should:
- show the relevant part clearly
- avoid unnecessary personal or sensitive data
- be readable without excessive zoom
- have a meaningful file name
- correspond to an actual validation point
- be referenced in deployment or test documentation where needed

## Notes on Sensitive Information
Before storing screenshots or outputs:
- avoid exposing real passwords
- avoid exposing secrets or tokens
- avoid storing full credential details
- mask confidential values if needed
- keep only the technical evidence necessary for validation

## Minimum Expected Evidence Set
At minimum, this folder should contain proof of:
- active firewall protection on at least one critical host
- applied firewall rules
- one intended exposed service reachable
- one denied direct backend access
- one VPN or controlled remote access proof
- one restricted admin access proof
- one port exposure review
- one blocked unauthorized path

## Conclusion
This folder is intended to provide clear, structured, and reusable proof that the Network Security component is correctly deployed and operational.

Once populated, it will support technical validation, security review, and final presentation by showing that the infrastructure includes controlled exposure, protected backend services, restricted administrative paths, and realistic baseline network security.