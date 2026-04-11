# Blue Team Playbooks README

## Purpose
This document explains the role of the Blue Team playbooks used in the final CYBFS project.

Its purpose is to:
- define how defensive review actions are organized
- show how recurring verification tasks can be performed consistently
- support case execution with repeatable review logic
- connect technical checks to findings, remediation, and validation

These playbooks are not meant to replace the case documentation. They are support tools used to guide the review of the deployed environment in a structured and repeatable way.

## Position of Playbooks in the Blue Team Workflow
The playbooks are used during the Blue Team review phase to structure how specific areas of the infrastructure are checked.

They help answer practical questions such as:
- what should be verified
- which evidence should be collected
- what kind of issues may appear
- how results should be interpreted
- what remediation directions may follow

They act as operational checklists and review guides.

## Main Objectives
The Blue Team playbooks aim to:
- standardize review steps across components
- reduce omissions during defensive analysis
- make evidence collection more consistent
- support repeatable validation logic
- improve clarity between technical checks and documented findings

## Scope of Playbooks
The playbooks are designed to cover the core infrastructure components of the final project:
- AD / IAM
- Web Server
- Database
- File Server
- Backup and Monitoring
- Network Security

They may also support transversal review themes such as:
- access control
- exposure reduction
- logging and monitoring visibility
- backup readiness
- administrative access control
- configuration hardening

## How Playbooks Are Used
A playbook is used when reviewing one specific component or one specific defensive theme.

A typical usage flow is:
1. select the component or review area
2. read the relevant playbook
3. perform the listed checks
4. collect the required evidence
5. note observed weaknesses or confirmations
6. transfer meaningful results into the Blue Team case files

The playbook helps structure the work, but the actual documented result belongs in:
- `03_Terrain_Card.md`
- `04_Evidence_Index.md`
- `05_Findings.md`
- `07_Remediation_Plan.md`
- `08_Retest_Results.md`

## Playbook Design Principles
Each playbook should remain:
- practical
- concise
- evidence-oriented
- repeatable
- aligned with the real deployed environment

A playbook should not become a generic theory document. It must remain usable during actual review work.

## Recommended Playbook Structure
Each component playbook can follow the same simple structure:

### 1. Objective
What the playbook is trying to verify.

### 2. Scope
Which host, service, or control area is concerned.

### 3. Key Checks
The main technical or defensive checks to perform.

### 4. Expected Evidence
What screenshots, logs, outputs, or notes should be collected.

### 5. Typical Issues
What types of weaknesses are commonly found.

### 6. Remediation Direction
What type of corrective action may be appropriate if an issue is observed.

### 7. Retest Logic
What should be checked again after remediation.

## Suggested Playbook Families
The following playbooks are especially relevant for this project.

### 1. AD / IAM Review Playbook
Focus:
- service availability
- user and group structure
- privilege separation
- centralized access logic
- permission consistency

### 2. Web Server Review Playbook
Focus:
- service reachability
- intended exposed ports only
- web configuration
- logging availability
- backend separation

### 3. Database Review Playbook
Focus:
- service availability
- intended internal-only access
- restricted connectivity
- application integration
- backup inclusion

### 4. File Server Review Playbook
Focus:
- authenticated access
- role-based or group-based permissions
- authorized vs unauthorized access behavior
- service exposure
- shared data protection

### 5. Backup and Monitoring Review Playbook
Focus:
- host visibility
- service visibility
- useful logs or events
- backup artifact existence
- restore-oriented validation

### 6. Network Security Review Playbook
Focus:
- firewall status
- intended vs unintended reachable ports
- backend protection
- remote access control
- restricted administrative paths

## Typical Review Outputs Produced Through Playbooks
The playbooks help generate:
- structured observations
- evidence references
- findings
- risk notes
- remediation suggestions
- retest checkpoints

This makes the final Blue Team case more consistent and easier to defend.

## Playbook Example Logic
A simple playbook flow may look like this:

### Example: Web Server Review
- verify the service is running
- verify the expected page loads
- verify only intended ports are open
- review logging visibility
- confirm backend services are not directly exposed
- capture evidence
- document any observed issue

This same logic can be adapted to every component.

## Relationship with Findings
A playbook does not automatically create a finding.

A finding should only be documented when:
- a real weakness or gap is observed
- the issue has actual relevance in the project context
- the issue is supported by evidence
- the issue can be explained and rated

This helps avoid inflating the Blue Team report with purely theoretical issues.

## Relationship with Remediation
Playbooks should also support remediation.

For each important issue observed, the reviewer should be able to derive:
- what should be corrected
- what evidence should change after correction
- what retest step should confirm improvement

This makes the Blue Team process improvement-oriented rather than purely descriptive.

## Recommended Folder Use
This `02_Playbooks/` folder can contain:
- this general README
- one playbook per component
- optional transversal playbooks for access control, logging, backup, or hardening
- optional checklist versions for quicker execution

Suggested future files:
- `AD_IAM_Playbook.md`
- `Web_Server_Playbook.md`
- `Database_Playbook.md`
- `File_Server_Playbook.md`
- `Backup_Monitoring_Playbook.md`
- `Network_Security_Playbook.md`

## Quality Criteria for a Good Playbook
A playbook is considered useful if:
- it is easy to execute
- it points to concrete checks
- it helps collect usable evidence
- it remains aligned with the actual environment
- it supports findings and remediation clearly
- it avoids unnecessary theory

## Known Limits
These playbooks are project-scale review tools.

They are not intended to be:
- a full enterprise runbook library
- a SOC operating manual
- a complete incident response framework
- a formal compliance control catalog

Their role is to support a realistic and professional defensive review within the scope of the final infrastructure project.

## Conclusion
This folder provides the operational review logic used during the Blue Team part of the project.

Once completed with component-specific playbooks, it will help ensure that defensive checks are structured, repeatable, evidence-based, and clearly connected to findings, remediation, and retest logic.