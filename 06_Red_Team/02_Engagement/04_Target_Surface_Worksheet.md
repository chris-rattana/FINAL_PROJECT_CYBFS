# Target Surface Worksheet

## Engagement Identification
- Engagement ID: RT-ENG-REMOTE-01
- Workstream: Red Team
- Project: FINAL_PROJECT_CYBFS
- Assessment Type: Controlled offensive review / pentest-style engagement
- Environment Type: SME-scale remote-first startup lab infrastructure
- Status: Initial target surface worksheet

## Purpose
This document records the target surface reviewed during the Red Team engagement.

Its purpose is to:
- identify the relevant exposed or reachable components of the environment
- organize the offensive review perimeter by target type
- distinguish intended exposure from unintended exposure
- support evidence collection and finding generation
- provide a practical attacker-oriented map of the infrastructure

This worksheet is not a full technical architecture document. It is an offensive review tool focused on what matters from the attacker’s perspective.

## Target Surface Logic
The target surface includes any component, service, or access path that could become relevant for offensive review, including:
- exposed services
- remote access entry points
- administrative paths
- backend services reachable from unintended paths
- weak trust boundaries
- visible application paths
- authentication-related exposure

The objective is to understand:
- what can be reached
- from where
- through which path
- with what level of expected protection
- whether the observed reachability matches the intended design

## Surface Classification Model
Each target surface item should be reviewed through the following dimensions:

- **Target ID**
- **Target Name**
- **Component Type**
- **Expected Exposure**
- **Observed Reachability**
- **Intended Access Path**
- **Potential Risk Theme**
- **Evidence Reference**
- **Notes**

## Exposure Categories

### Public / User-Facing
Services intentionally reachable by users or external paths.

### Controlled Remote Access
Services intended to be reachable only through VPN or another controlled access mechanism.

### Internal-Only
Services that should remain reachable only from approved internal hosts or specific backend paths.

### Administrative-Only
Services that should be reachable only through tightly controlled administrative access paths.

## Main Target Categories

## 1. Web Layer Targets
This category includes:
- web server ports
- application entry points
- user-facing URLs
- exposed HTTP/HTTPS services
- backend-facing web components if relevant

### Offensive Interest
- overexposed ports
- unexpected endpoints
- user-facing behavior that reveals backend structure
- weak separation between public and internal layers

## 2. Remote Access Targets
This category includes:
- VPN entry point
- remote access service ports
- externally reachable controlled-access services
- access paths that change internal reachability

### Offensive Interest
- whether remote access is too broad
- whether the access path is correctly restricted
- whether remote access unintentionally exposes internal services

## 3. Administrative Access Targets
This category includes:
- SSH paths
- administration interfaces
- management ports
- service management paths
- privileged access entry points

### Offensive Interest
- admin overexposure
- reachable privileged interfaces
- weak separation between admin and user-facing paths

## 4. Backend Service Targets
This category includes:
- database service ports
- internal application interfaces
- identity services
- internal file-sharing backends
- any service intended to remain hidden behind other layers

### Offensive Interest
- direct reachability from unintended paths
- backend exposure inconsistent with architecture
- weak internal segmentation or filtering

## 5. File-Sharing Targets
This category includes:
- visible file service access paths
- platform entry URLs
- reachable service ports
- authentication boundaries around shared resources

### Offensive Interest
- weak authentication boundary
- unnecessarily broad exposure
- paths that reveal shared resource access too easily

## 6. Monitoring and Support Targets
This category includes:
- monitoring interfaces if reachable
- support or visibility ports
- backup-related network paths if relevant
- administration-related visibility endpoints

### Offensive Interest
- management visibility interfaces that should not be exposed
- support systems reachable from unintended paths
- weak protection of resilience-related components

## Target Register

| Target ID | Target Name | Component Type | Expected Exposure | Observed Reachability | Intended Access Path | Potential Risk Theme | Evidence Ref | Notes |
|-----------|-------------|----------------|-------------------|-----------------------|----------------------|----------------------|--------------|-------|
| T01 | Main Web Service | Web Server | Public / User-Facing | To complete | Direct user-facing path | overexposure / weak separation | To complete | To complete |
| T02 | Web Admin or Management Path | Web Server / Admin | Administrative-Only | To complete | Restricted admin path | admin overexposure | To complete | To complete |
| T03 | Remote Access Entry Point | Remote Access | Controlled Remote Access | To complete | VPN / approved remote path | excessive remote reachability | To complete | To complete |
| T04 | Database Service Port | Database | Internal-Only | To complete | application/backend only | direct backend exposure | To complete | To complete |
| T05 | AD / IAM Service Exposure | AD / IAM | Internal-Only or Administrative-Only | To complete | internal/admin path | identity service exposure | To complete | To complete |
| T06 | File-Sharing Access Path | File Server | Controlled Remote Access or User-Facing | To complete | authenticated access path | over-broad file access exposure | To complete | To complete |
| T07 | File Service Admin Path | File Server / Admin | Administrative-Only | To complete | restricted admin path | admin exposure | To complete | To complete |
| T08 | Monitoring Interface | Backup / Monitoring | Administrative-Only | To complete | admin/ops path | visibility interface exposure | To complete | To complete |
| T09 | SSH on Critical Host(s) | Admin / Host Access | Administrative-Only | To complete | approved admin path only | weak admin boundary | To complete | To complete |
| T10 | Unexpected Open Port | Any Component | Not Expected | To complete | none | unintended exposure | To complete | To complete |

## Recommended Review Questions per Target

### Reachability
- Is the target reachable?
- Is it reachable from the correct path only?
- Is it reachable when it should not be?

### Exposure Intent
- Is the exposure intentional?
- Does it match the documented architecture?
- Is the service more visible than required?

### Boundary Quality
- Does the target remain behind the expected trust boundary?
- Can it be reached from an unapproved zone?
- Is there evidence of weak separation?

### Administrative Risk
- Is the target privileged or sensitive?
- Should it be admin-only?
- Is admin reachability broader than expected?

### Backend Risk
- Is the target part of the internal layer?
- Can it be reached without going through the intended frontend or control path?
- Does this create unnecessary offensive opportunity?

## Surface Review Notes by Component

## Web Server
Expected:
- one intended user-facing access path
- limited web ports
- no direct leakage of backend services

Review Notes:
- To complete

## Database
Expected:
- internal-only reachability
- application/backend path only
- no broad external exposure

Review Notes:
- To complete

## AD / IAM
Expected:
- protected service role
- limited administrative or internal-only exposure
- no broad user-facing exposure

Review Notes:
- To complete

## File Server
Expected:
- authenticated access path
- controlled service exposure
- permission-based access model

Review Notes:
- To complete

## Remote Access
Expected:
- controlled entry point
- no unnecessary broad internal reachability
- clear relation to intended user/admin access

Review Notes:
- To complete

## Network Security
Expected:
- only intended ports reachable
- backend services protected
- administrative paths restricted

Review Notes:
- To complete

## High-Value Surface Areas
The following surface areas are likely to deserve the most attention:
- the main web service
- the remote access entry point
- administrative service exposure
- direct database reachability
- backend paths accessible from the wrong zone

These areas are prioritized because they represent the highest-value offensive opportunities in a remote-access-oriented infrastructure.

## Low-Value / Noise Surface Areas
Not every visible target deserves equal attention.

A target may be lower priority if:
- it is already clearly filtered
- it has no meaningful offensive value
- it is not practically reachable
- it has no realistic project-scale impact
- it does not affect the main trust boundaries

This helps keep the Red Team review focused.

## Evidence Expectations
For each meaningful target, collect evidence such as:
- screenshot of reachable service
- screenshot of denied path
- command output showing port reachability
- scan result
- note confirming intended versus observed exposure
- firewall or filtering observation where relevant

These evidence items should later be indexed in `05_Evidence_Index.md`.

## Surface-to-Finding Mapping Template
Use this mapping once findings are finalized:

| Target ID | Possible Finding ID | Observation Type | Notes |
|-----------|---------------------|------------------|-------|
| T01 | To complete | exposed service review | To complete |
| T02 | To complete | admin exposure review | To complete |
| T03 | To complete | remote access review | To complete |
| T04 | To complete | backend reachability review | To complete |
| T05 | To complete | identity exposure review | To complete |
| T06 | To complete | file service exposure review | To complete |
| T07 | To complete | admin exposure review | To complete |
| T08 | To complete | monitoring interface review | To complete |
| T09 | To complete | privileged access review | To complete |
| T10 | To complete | unexpected exposure review | To complete |

## Fields to Complete During Real Assessment
Complete the following when the engagement is populated with real values:
- main public IP or hostname targets: To complete
- main VPN or remote-access target: To complete
- main internal-only service targets: To complete
- main admin-only service targets: To complete
- unexpected exposed services discovered: To complete

## Conclusion
This target surface worksheet provides the offensive view of what matters in the reviewed environment.

Once completed with real target values, observed reachability, and evidence references, it will serve as the practical target map of the Red Team engagement and will support findings, remediation, and retest logic.