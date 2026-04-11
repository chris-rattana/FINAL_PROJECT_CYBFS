# Findings

## Case Identification
- Case ID: HOME_Run01
- Workstream: Blue Team
- Review Type: Defensive review
- Environment Type: SME-scale remote-first startup lab infrastructure
- Status: Initial findings set

## Purpose
This document records the main defensive findings identified during the Blue Team case `HOME_Run01`.

Its purpose is to:
- document meaningful weaknesses observed in the deployed environment
- connect findings to technical evidence
- explain why each issue matters
- support qualitative risk evaluation
- prepare remediation planning and retest logic

This document is evidence-based. A finding should only appear here if it is supported by a real observation, a review result, or a concrete gap identified in the deployed environment.

## Findings Methodology
Each finding should remain:
- relevant to the actual environment
- supported by evidence
- understandable in operational and security terms
- proportionate to project scale
- actionable through remediation

Each finding is described using the following structure:
- Finding ID
- Title
- Component(s)
- Severity
- Description
- Evidence
- Impact
- Recommendation
- Status

## Severity Scale
The following qualitative severity scale is used:
- **Low**: minor issue with limited impact
- **Medium**: meaningful weakness that should be corrected
- **High**: important weakness affecting defensive credibility, access control, or exposure

---

# Finding List

## F01 — Documentation and Evidence Coverage Still Incomplete
**Component(s):** Entire infrastructure  
**Severity:** Medium

### Description
The project documentation structure is now strong and professionally organized, but a significant part of the case still relies on placeholders such as “To complete” sections, evidence templates, and future screenshot references.

This means that although the methodology and structure are mature, the defensive review cannot yet rely on a fully populated set of real-world deployment proof for every component.

### Evidence
- `03_Infrastructure_Deployment/04_Screenshots_Proofs/.../README.md`
- `05_Blue_Team/03_Case_HOME_Run01/04_Evidence_Index.md`
- multiple files still contain placeholder fields such as “To complete”

### Impact
If not completed, this weakens:
- review credibility
- traceability of findings
- ability to demonstrate real validation
- final presentation readiness

### Recommendation
- replace placeholders with real screenshots and outputs
- complete all evidence references with actual filenames
- populate environment-specific fields in Blue Team case files
- ensure each major control has at least one real supporting proof

### Status
Open

---

## F02 — Blue Team Case Not Yet Fully Populated with Real Observations
**Component(s):** Blue Team case management  
**Severity:** Medium

### Description
The Blue Team case structure is complete, but the operational review content is not yet fully populated with actual review observations for each component. Several timeline entries, terrain values, and future mapping elements are still awaiting real environment data.

### Evidence
- `05_Blue_Team/03_Case_HOME_Run01/02_Timeline.md`
- `05_Blue_Team/03_Case_HOME_Run01/03_Terrain_Card.md`
- `05_Blue_Team/03_Case_HOME_Run01/04_Evidence_Index.md`

### Impact
This reduces the maturity of the Blue Team deliverable because the case is structurally ready but not yet fully transformed into a concrete defensive review.

### Recommendation
- replace generic placeholders with actual findings and observations
- fill in real hostnames, IPs, service states, and validation outputs
- align evidence IDs with actual collected proof
- update the timeline using real review steps and dates

### Status
Open

---

## F03 — Residual Risk of Overexposure Until Firewall and Port Proofs Are Collected
**Component(s):** Web Server, Database, Network Security  
**Severity:** High

### Description
The architecture and documentation clearly define exposure reduction, backend isolation, and host firewalling as essential controls. However, until actual firewall outputs, port scans, and denied-path proof are collected and indexed, the review cannot fully confirm that unintended exposure has been eliminated in practice.

### Evidence
- `02_Technical_Specification/06_Security_Controls.md`
- `03_Infrastructure_Deployment/02_Components/Network_Security.md`
- `03_Infrastructure_Deployment/04_Screenshots_Proofs/Network_Security/README.md`
- `03_Infrastructure_Deployment/05_Test_Cases.md`

### Impact
Unverified service exposure may affect:
- web server attack surface
- direct database reachability
- administrative service protection
- overall defensive credibility of the environment

### Recommendation
- collect actual firewall status outputs for critical hosts
- collect port exposure proof for web and database hosts
- confirm at least one blocked unauthorized path
- document VPN or controlled remote access proof if used

### Status
Open

---

## F04 — Access Control Logic Must Be Proven with Real Authorized and Unauthorized Tests
**Component(s):** AD / IAM, File Server, possibly Web access layer  
**Severity:** High

### Description
The project design correctly emphasizes centralized identity, group-based access, and least privilege. However, the defensive case still depends on demonstrating that access really behaves as intended for both authorized and unauthorized users.

Without these tests, access control remains documented but not fully proven.

### Evidence
- `03_Infrastructure_Deployment/02_Components/AD_IAM.md`
- `03_Infrastructure_Deployment/02_Components/File_Server.md`
- `03_Infrastructure_Deployment/05_Test_Cases.md`
- `03_Infrastructure_Deployment/04_Screenshots_Proofs/AD_IAM/README.md`
- `03_Infrastructure_Deployment/04_Screenshots_Proofs/File_Server/README.md`

### Impact
If not demonstrated, the project remains weaker on:
- access governance validation
- least-privilege credibility
- file-sharing protection
- identity-driven control proof

### Recommendation
- create at least one real authorized user test
- create at least one real unauthorized or unrelated user denial test
- capture screenshots and outputs of both cases
- map these proofs into the Blue Team evidence index

### Status
Open

---

## F05 — Backup Logic Is Documented but Needs Real Restore-Oriented Validation
**Component(s):** Backup and Monitoring, Database, File Server  
**Severity:** High

### Description
The project correctly includes backup scope, backup logic, and recovery thinking. However, a backup process is only defensively credible if at least one restore-oriented path is validated or clearly demonstrated.

At the current state of the case structure, restore proof is still largely planned rather than evidenced.

### Evidence
- `02_Technical_Specification/07_Compliance_Backup_DR.md`
- `02_Technical_Specification/08_Testing_Validation.md`
- `03_Infrastructure_Deployment/02_Components/Backup_Monitoring.md`
- `03_Infrastructure_Deployment/04_Screenshots_Proofs/Backup_Monitoring/README.md`

### Impact
Without restore-oriented evidence, the environment may appear to have:
- backup confidence without proof
- reduced resilience credibility
- incomplete recovery readiness demonstration

### Recommendation
- produce at least one concrete backup artifact
- document exactly what is included in backup scope
- validate one limited restore scenario
- preserve proof of backup existence and restore reasoning

### Status
Open

---

## F06 — Monitoring Coverage Must Be Confirmed on Critical Services
**Component(s):** Backup and Monitoring, Web Server, Database, AD / IAM, File Server  
**Severity:** Medium

### Description
Monitoring is part of the required infrastructure and strongly supports both operations and Blue Team review. The project documentation positions monitoring correctly, but actual proof of visibility over critical hosts and services is still required to show that the monitoring layer is practically useful.

### Evidence
- `03_Infrastructure_Deployment/02_Components/Backup_Monitoring.md`
- `03_Infrastructure_Deployment/04_Screenshots_Proofs/Backup_Monitoring/README.md`
- `03_Infrastructure_Deployment/05_Test_Cases.md`

### Impact
Insufficient monitoring proof weakens:
- operational visibility
- incident awareness
- Blue Team evidence quality
- defensive maturity of the infrastructure

### Recommendation
- capture monitoring dashboard screenshots
- show critical hosts and services in monitoring
- include at least one useful operational or security-relevant view
- map the related proof in the evidence index

### Status
Open

---

## F07 — Integration Proof Between Core Services Still Needs to Be Materialized
**Component(s):** Web Server, Database, AD / IAM, File Server  
**Severity:** Medium

### Description
The architecture is coherent and the deployment documentation is well structured, but the final Blue Team value depends on proving that the environment behaves as an integrated system rather than a set of isolated components.

The most important integration paths still need final real evidence:
- web to database
- IAM to permission-based access
- file-sharing tied to user/group logic
- monitoring visibility tied to deployed services

### Evidence
- `02_Technical_Specification/08_Testing_Validation.md`
- `03_Infrastructure_Deployment/05_Test_Cases.md`
- component screenshots/proofs folders

### Impact
Weak integration proof reduces:
- confidence in end-to-end operability
- confidence in defensive conclusions
- overall final project cohesion

### Recommendation
- perform and capture end-to-end tests
- confirm application-to-database behavior
- confirm group-based file access
- confirm monitored services correspond to real deployed components

### Status
Open

---

## F08 — Administrative Access Restriction Needs Explicit Evidence
**Component(s):** AD / IAM, Network Security, critical hosts  
**Severity:** Medium

### Description
The project repeatedly states that administrative access should remain restricted and separated from standard user activity. This is a strong design choice, but the Blue Team case still needs explicit proof that admin paths are controlled and not broadly exposed.

### Evidence
- `02_Technical_Specification/06_Security_Controls.md`
- `03_Infrastructure_Deployment/02_Components/Network_Security.md`
- `03_Infrastructure_Deployment/03_Installation_Configuration/Network_Security/README.md`

### Impact
If undocumented in practice, admin-path protection remains an assumption rather than a verified control.

### Recommendation
- capture one proof of restricted admin access
- show approved versus unapproved access behavior where possible
- include firewall or connectivity outputs that support the restriction model

### Status
Open

---

## F09 — Residual Gap Between Strong Framework and Fully Finalized Deliverables
**Component(s):** Entire project / Blue Team contribution  
**Severity:** Medium

### Description
A major strength of the project is the quality of its structure, methodology, and documentation design. However, there remains a residual gap between having a strong framework and having every deliverable fully completed with actual case material.

This is not a design failure, but it is a meaningful delivery risk.

### Evidence
- structured repository and case files exist
- multiple sections still wait for real completion
- evidence folders are indexed but not yet fully populated

### Impact
If not closed, this may affect:
- final project completeness
- jury confidence
- practical defensibility of the Blue Team case

### Recommendation
- prioritize completion of real evidence before further expansion
- convert templates into concrete outputs
- close open placeholders in case documents
- align findings, risk register, remediation, and retest with actual observations

### Status
Open

---

# Findings Summary Table

| Finding ID | Title | Component(s) | Severity | Status |
|------------|-------|--------------|----------|--------|
| F01 | Documentation and Evidence Coverage Still Incomplete | Entire infrastructure | Medium | Open |
| F02 | Blue Team Case Not Yet Fully Populated with Real Observations | Blue Team case management | Medium | Open |
| F03 | Residual Risk of Overexposure Until Firewall and Port Proofs Are Collected | Web / DB / Network Security | High | Open |
| F04 | Access Control Logic Must Be Proven with Real Authorized and Unauthorized Tests | AD / IAM / File Server | High | Open |
| F05 | Backup Logic Is Documented but Needs Real Restore-Oriented Validation | Backup / Monitoring / DB / File Server | High | Open |
| F06 | Monitoring Coverage Must Be Confirmed on Critical Services | Backup / Monitoring and core services | Medium | Open |
| F07 | Integration Proof Between Core Services Still Needs to Be Materialized | Web / DB / IAM / File Server | Medium | Open |
| F08 | Administrative Access Restriction Needs Explicit Evidence | IAM / Network Security / critical hosts | Medium | Open |
| F09 | Residual Gap Between Strong Framework and Fully Finalized Deliverables | Entire project | Medium | Open |

## Notes for Real Case Completion
When the environment is fully populated with real evidence:
- update each finding with exact evidence IDs
- close findings that are no longer relevant
- downgrade findings after successful remediation if justified
- add concrete observations in place of generic wording when possible
- keep only findings that are defensibly linked to the actual environment

## Conclusion
These findings represent the initial defensive view of the Blue Team case `HOME_Run01`.

At this stage, the most important themes are:
- turning structure into fully evidenced delivery
- proving access control in practice
- proving restricted exposure
- proving monitoring usefulness
- proving backup and restore credibility

Once evidence is fully collected and remediation is documented, this file will serve as the core analytical output of the Blue Team case.