# Evidence Index

## Case Identification
- Case ID: HOME_Run01
- Workstream: Blue Team
- Review Type: Defensive review
- Environment Type: SME-scale remote-first startup lab infrastructure
- Status: In progress

## Purpose
This document indexes the technical evidence collected during the Blue Team case `HOME_Run01`.

Its purpose is to:
- identify the evidence used in the case
- explain what each evidence item demonstrates
- link observations to findings
- support risk evaluation and remediation
- improve traceability across the case documentation

This evidence index is one of the most important files in the Blue Team case because it connects the review narrative to actual proof.

## Evidence Handling Principles
All evidence used in this case should follow the following rules:
- evidence must be relevant
- evidence must be understandable
- evidence must be linked to a real validation or observation point
- evidence must avoid exposing unnecessary secrets
- filenames should be clear and reusable
- each important finding should reference at least one evidence item

Evidence may come from:
- screenshots
- service status outputs
- command outputs
- configuration excerpts
- logs
- monitoring views
- firewall outputs
- access test results
- backup artifacts
- deployment documentation references

## Evidence Naming Logic
A simple naming convention is recommended.

Suggested naming style:
- `EV01_iam_service_status.png`
- `EV02_iam_test_user.txt`
- `EV03_web_service_running.png`
- `EV04_web_listening_ports.txt`
- `EV05_db_internal_connectivity.txt`
- `EV06_db_direct_access_denied.png`
- `EV07_files_authorized_access.png`
- `EV08_files_denied_access.png`
- `EV09_monitoring_dashboard.png`
- `EV10_backup_artifact_exists.png`
- `EV11_firewall_status_web.txt`
- `EV12_firewall_status_db.txt`

This naming logic keeps the evidence easy to reference in findings and remediation.

## Evidence Categories

## 1. Identity and Access Management Evidence
This category includes evidence related to:
- service status
- domain or identity configuration
- created users
- created groups
- group membership
- permission-based access behavior
- admin access logic

### Typical Examples
- identity service active
- test user created
- test group created
- membership assigned
- authorized access works
- unrelated access denied

## 2. Web Server Evidence
This category includes evidence related to:
- service status
- web page or endpoint reachability
- listening ports
- configuration excerpts
- backend integration
- access logs
- reduced exposure

### Typical Examples
- Nginx running
- homepage loaded
- expected endpoint responds
- only intended web port exposed

## 3. Database Evidence
This category includes evidence related to:
- service status
- database existence
- service account existence
- internal connectivity
- application-to-database communication
- denied unauthorized access
- backup inclusion

### Typical Examples
- PostgreSQL running
- database created
- application connection successful
- direct database reachability denied

## 4. File Server Evidence
This category includes evidence related to:
- service status
- login page
- admin access
- shared folder visibility
- authorized file access
- file operation success
- unauthorized access restriction

### Typical Examples
- platform running
- authorized user sees shared space
- unrelated user denied
- file upload succeeds

## 5. Backup and Monitoring Evidence
This category includes evidence related to:
- monitoring dashboard
- monitored hosts
- monitored services
- event or log visibility
- documented backup scope
- backup artifact existence
- restore-oriented validation

### Typical Examples
- monitoring interface shows hosts
- backup file exists
- restore path documented

## 6. Network Security Evidence
This category includes evidence related to:
- firewall status
- active firewall rules
- intended service reachability
- denied direct backend access
- VPN or controlled remote access
- restricted admin path
- blocked unauthorized path

### Typical Examples
- firewall active on critical host
- web port reachable
- database port denied from unapproved path
- admin access restricted

## Evidence Register

| Evidence ID | File Name | Component | Type | What It Demonstrates | Related Area | Notes |
|-------------|-----------|-----------|------|----------------------|--------------|-------|
| EV01 | EV01_iam_service_status.png | AD / IAM | Screenshot | IAM service is active | service availability | To complete |
| EV02 | EV02_iam_test_user.txt | AD / IAM | Command Output | test user exists | access governance | To complete |
| EV03 | EV03_iam_group_membership.png | AD / IAM | Screenshot | user is assigned to group | permission logic | To complete |
| EV04 | EV04_web_service_running.png | Web Server | Screenshot | web service is active | service availability | To complete |
| EV05 | EV05_web_listening_ports.txt | Web Server | Command Output | intended web port is listening | exposure validation | To complete |
| EV06 | EV06_web_homepage_loaded.png | Web Server | Screenshot | homepage or endpoint is reachable | functional validation | To complete |
| EV07 | EV07_db_service_status.txt | Database | Command Output | database service is active | service availability | To complete |
| EV08 | EV08_db_internal_connectivity.txt | Database | Command Output | intended internal DB connectivity works | backend validation | To complete |
| EV09 | EV09_db_direct_access_denied.png | Database | Screenshot | unauthorized direct DB access is denied | exposure validation | To complete |
| EV10 | EV10_files_login_page.png | File Server | Screenshot | file-sharing platform is reachable | functional validation | To complete |
| EV11 | EV11_files_authorized_access.png | File Server | Screenshot | authorized user access works | access control | To complete |
| EV12 | EV12_files_denied_access.png | File Server | Screenshot | unauthorized access is denied | access control | To complete |
| EV13 | EV13_monitoring_dashboard.png | Backup / Monitoring | Screenshot | monitoring is operational | visibility validation | To complete |
| EV14 | EV14_monitored_services.png | Backup / Monitoring | Screenshot | critical services are visible | monitoring coverage | To complete |
| EV15 | EV15_backup_artifact_exists.png | Backup / Monitoring | Screenshot | backup artifact exists | resilience validation | To complete |
| EV16 | EV16_restore_validation.txt | Backup / Monitoring | Text Note | restore-oriented validation exists | recovery validation | To complete |
| EV17 | EV17_firewall_status_web.txt | Network Security | Command Output | firewall active on web host | firewall validation | To complete |
| EV18 | EV18_firewall_status_db.txt | Network Security | Command Output | firewall active on DB host | firewall validation | To complete |
| EV19 | EV19_vpn_connection_success.png | Network Security | Screenshot | controlled remote access works | remote access validation | To complete |
| EV20 | EV20_admin_access_restricted.png | Network Security | Screenshot | admin access is restricted | admin security validation | To complete |
| EV21 | EV21_unapproved_path_denied.txt | Network Security | Command Output | blocked unauthorized path confirmed | exposure control | To complete |

## Evidence-to-Finding Mapping Template
When findings are written, each one should reference the relevant evidence IDs.

Use the following pattern:

| Finding ID | Finding Title | Evidence IDs | Comment |
|------------|---------------|--------------|---------|
| F01 | To complete | EVxx, EVyy | To complete |
| F02 | To complete | EVxx | To complete |
| F03 | To complete | EVxx, EVyy, EVzz | To complete |

This ensures that every finding remains grounded in collected proof.

## Evidence-to-Component Mapping

### AD / IAM
Recommended evidence IDs:
- EV01
- EV02
- EV03

### Web Server
Recommended evidence IDs:
- EV04
- EV05
- EV06

### Database
Recommended evidence IDs:
- EV07
- EV08
- EV09

### File Server
Recommended evidence IDs:
- EV10
- EV11
- EV12

### Backup and Monitoring
Recommended evidence IDs:
- EV13
- EV14
- EV15
- EV16

### Network Security
Recommended evidence IDs:
- EV17
- EV18
- EV19
- EV20
- EV21

## Evidence Quality Criteria
A good evidence set should be:
- complete enough to support the case
- clear enough to be reused later
- consistent with the actual deployed environment
- linked to review logic
- strong enough to support findings and remediation

At minimum, the evidence should prove:
- critical services are running
- access control is testable
- intended service paths work
- unintended or unauthorized paths are restricted
- monitoring exists
- backup logic is evidenced
- firewalling and network controls are real

## Sensitive Data Handling
Before saving evidence:
- remove or mask passwords
- remove or mask secrets and tokens
- avoid storing unnecessary confidential data
- keep only the technical proof needed for validation
- preserve the evidence value without exposing sensitive content

## Evidence Storage Notes
Complete the following when the real case is populated:

- Main screenshots folder location: To complete
- Main raw outputs location: To complete
- Backup artifact location: To complete
- Monitoring proof location: To complete
- Network proof location: To complete

## Analyst Notes
Use this section to record any important note about evidence coverage, missing proof, or evidence quality.

- To complete

## Conclusion
This evidence index provides the proof backbone of the Blue Team case `HOME_Run01`.

Once completed with actual filenames, outputs, screenshots, and mappings to findings, it will ensure that the defensive review remains traceable, evidence-based, and professionally structured.