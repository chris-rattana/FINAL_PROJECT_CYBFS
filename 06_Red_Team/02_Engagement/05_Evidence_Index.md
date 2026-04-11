# Evidence Index

## Engagement Identification
- Engagement ID: RT-ENG-REMOTE-01
- Workstream: Red Team
- Project: FINAL_PROJECT_CYBFS
- Assessment Type: Controlled offensive review / pentest-style engagement
- Environment Type: SME-scale remote-first startup lab infrastructure
- Status: In progress

## Purpose
This document indexes the technical evidence collected during the Red Team engagement.

Its purpose is to:
- identify the evidence used in the engagement
- explain what each evidence item demonstrates
- link offensive observations to findings
- support remediation and retest
- improve traceability across the Red Team documentation

This evidence index is one of the most important files in the Red Team engagement because it connects the offensive narrative to actual proof.

## Evidence Handling Principles
All evidence used in this engagement should follow the following rules:
- evidence must be relevant
- evidence must be understandable
- evidence must be linked to a real validation or offensive observation point
- evidence must avoid exposing unnecessary sensitive secrets
- filenames should be clear and reusable
- each important finding should reference at least one evidence item

Evidence may come from:
- screenshots
- service response captures
- command outputs
- scan results
- connection attempts
- denied-path proof
- firewall observations
- reachability notes
- application behavior observations
- deployment documentation references when useful for comparison

## Evidence Naming Logic
A simple naming convention is recommended.

Suggested naming style:
- `REV01_web_reachable.png`
- `REV02_web_ports_scan.txt`
- `REV03_db_direct_access_denied.png`
- `REV04_admin_path_reachable.txt`
- `REV05_admin_path_denied.txt`
- `REV06_vpn_entry_visible.png`
- `REV07_internal_resource_via_vpn.png`
- `REV08_file_service_login.png`
- `REV09_file_service_exposure_note.txt`
- `REV10_firewall_observation_web.txt`
- `REV11_firewall_observation_db.txt`
- `REV12_unexpected_open_port.png`

This naming logic keeps the evidence easy to reference in findings and retest.

## Evidence Categories

## 1. Web Exposure Evidence
This category includes evidence related to:
- exposed web services
- reachable web ports
- visible application entry points
- unexpected user-facing behavior
- signs of weak separation between web and backend layers

### Typical Examples
- homepage reachable
- intended endpoint responds
- unexpected port visible
- user-facing behavior reveals too much backend structure

## 2. Remote Access Evidence
This category includes evidence related to:
- VPN or remote access entry point visibility
- controlled versus uncontrolled remote reachability
- internal access obtained through the intended path
- potential over-broad remote access

### Typical Examples
- VPN entry point visible
- internal service reachable only after approved access
- remote-access path broader than expected

## 3. Administrative Exposure Evidence
This category includes evidence related to:
- reachable administrative services
- denied or allowed admin path tests
- exposed SSH or management ports
- weak admin boundary observations

### Typical Examples
- SSH reachable from unintended path
- admin port blocked from unapproved path
- management interface visible when it should not be

## 4. Backend Reachability Evidence
This category includes evidence related to:
- direct database reachability
- access to internal-only services
- path validation between exposed and backend layers
- evidence that backend paths are or are not protected

### Typical Examples
- database port reachable from wrong path
- database port blocked from wrong path
- internal service visible unexpectedly
- internal service properly filtered

## 5. File Service Exposure Evidence
This category includes evidence related to:
- visible file-sharing access path
- authentication boundary
- exposure of collaborative service entry points
- unexpected visibility of protected resources

### Typical Examples
- file-service login path reachable
- protected resource visible without intended boundary
- file-service exposure aligned or misaligned with expectations

## 6. Network Filtering and Reachability Evidence
This category includes evidence related to:
- port visibility
- allowed versus blocked paths
- firewall behavior observed from the offensive perspective
- mismatch between intended architecture and actual reachability

### Typical Examples
- scan results
- blocked connection attempts
- expected service reachable
- unexpected service reachable

## 7. Retest Evidence
This category includes evidence related to:
- post-remediation rechecks
- reduced exposure after correction
- blocked path that was previously open
- corrected admin access restriction
- corrected backend isolation

### Typical Examples
- port no longer reachable after firewall change
- admin path restricted after remediation
- retest scan shows reduced attack surface

## Evidence Register

| Evidence ID | File Name | Component | Type | What It Demonstrates | Related Area | Notes |
|-------------|-----------|-----------|------|----------------------|--------------|-------|
| REV01 | REV01_web_reachable.png | Web Server | Screenshot | intended web service is reachable | web exposure review | To complete |
| REV02 | REV02_web_ports_scan.txt | Web Server | Command Output | visible web-related ports | exposure validation | To complete |
| REV03 | REV03_db_direct_access_denied.png | Database | Screenshot | direct backend access is blocked | backend protection | To complete |
| REV04 | REV04_db_direct_access_test.txt | Database | Command Output | result of direct DB reachability check | backend reachability | To complete |
| REV05 | REV05_admin_path_reachable.txt | Admin Path | Command Output | admin path is reachable from tested path | admin exposure review | To complete |
| REV06 | REV06_admin_path_denied.txt | Admin Path | Command Output | admin path is blocked from unapproved path | admin exposure review | To complete |
| REV07 | REV07_vpn_entry_visible.png | Remote Access | Screenshot | remote access entry point exists | remote access review | To complete |
| REV08 | REV08_internal_resource_via_vpn.png | Remote Access | Screenshot | internal resource reachable through intended remote path | controlled access validation | To complete |
| REV09 | REV09_file_service_login.png | File Server | Screenshot | file service login path is reachable | file service exposure | To complete |
| REV10 | REV10_file_service_exposure_note.txt | File Server | Text Note | offensive observation about file service exposure | file service review | To complete |
| REV11 | REV11_firewall_observation_web.txt | Network Security | Command Output | firewall-related observation on web host | filtering review | To complete |
| REV12 | REV12_firewall_observation_db.txt | Network Security | Command Output | firewall-related observation on DB host | filtering review | To complete |
| REV13 | REV13_unexpected_open_port.png | Network Security | Screenshot | unexpected open port observed | unexpected exposure | To complete |
| REV14 | REV14_web_admin_path_test.txt | Web Server / Admin | Command Output | result of admin path test on web-facing host | admin boundary review | To complete |
| REV15 | REV15_backend_isolation_note.txt | Backend | Text Note | observation on separation between public and internal layer | trust-boundary review | To complete |
| REV16 | REV16_retest_exposure_reduced.png | Network Security | Screenshot | previously exposed path is now reduced | retest | To complete |
| REV17 | REV17_retest_admin_restricted.txt | Admin Path | Command Output | admin path no longer broadly reachable | retest | To complete |

## Evidence-to-Finding Mapping Template
When findings are written, each one should reference the relevant evidence IDs.

Use the following pattern:

| Finding ID | Finding Title | Evidence IDs | Comment |
|------------|---------------|--------------|---------|
| RF01 | To complete | REVxx, REVyy | To complete |
| RF02 | To complete | REVxx | To complete |
| RF03 | To complete | REVxx, REVyy, REVzz | To complete |

This ensures that every Red Team finding remains grounded in collected proof.

## Evidence-to-Target Mapping

### Web Layer
Recommended evidence IDs:
- REV01
- REV02
- REV14

### Database / Backend
Recommended evidence IDs:
- REV03
- REV04
- REV15

### Remote Access
Recommended evidence IDs:
- REV07
- REV08

### File Service
Recommended evidence IDs:
- REV09
- REV10

### Network Security
Recommended evidence IDs:
- REV11
- REV12
- REV13

### Retest
Recommended evidence IDs:
- REV16
- REV17

## Evidence Quality Criteria
A good evidence set should be:
- complete enough to support the engagement
- clear enough to be reused later
- consistent with the actual deployed environment
- linked to offensive review logic
- strong enough to support findings, remediation, and retest

At minimum, the evidence should prove:
- what is reachable
- what is not reachable
- whether backend services are protected
- whether admin paths are restricted
- whether remote access behaves as intended
- whether unexpected exposure exists
- whether remediation changed the offensive posture

## Sensitive Data Handling
Before saving evidence:
- remove or mask passwords
- remove or mask secrets and tokens
- avoid storing unnecessary confidential data
- keep only the technical proof needed for validation
- preserve the evidence value without exposing sensitive content

## Evidence Storage Notes
Complete the following when the real engagement is populated:

- Main screenshots folder location: To complete
- Main raw outputs location: To complete
- Scan output location: To complete
- Remote access proof location: To complete
- Retest proof location: To complete

## Analyst Notes
Use this section to record any important note about evidence coverage, missing proof, or evidence quality.

- To complete

## Conclusion
This evidence index provides the proof backbone of the Red Team engagement.

Once completed with actual filenames, outputs, screenshots, and mappings to findings, it will ensure that the offensive review remains traceable, evidence-based, and professionally structured.