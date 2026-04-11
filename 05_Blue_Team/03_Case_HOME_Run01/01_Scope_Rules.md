# Scope and Rules

## Case Identification
- Case ID: HOME_Run01
- Workstream: Blue Team
- Review Type: Defensive review of the deployed infrastructure
- Environment Type: SME-scale remote-first startup lab environment
- Status: Initial review cycle

## Purpose
This document defines the scope, assumptions, boundaries, and operating rules for the Blue Team case `HOME_Run01`.

Its purpose is to:
- define exactly what is reviewed
- clarify what is included and excluded
- set the defensive review boundaries
- ensure consistency between evidence, findings, remediation, and retest
- prevent ambiguity during validation and analysis

This document is the reference perimeter for the Blue Team case.

## Case Objective
The objective of this Blue Team case is to review the deployed infrastructure from a defensive and operational security perspective in order to:
- identify meaningful weaknesses
- assess exposure and defensive gaps
- verify the state of core security controls
- document risks
- propose practical remediation actions
- support later retest validation where applicable

## Review Context
This Blue Team case is based on the actual deployed environment prepared for the final project.

The review focuses on the infrastructure as deployed and documented at the time of analysis, including:
- centralized identity and access management
- web service layer
- backend database
- file-sharing service
- backup and monitoring logic
- network security controls

The review is evidence-based and tied to the real project environment.

## In-Scope Components
The following components are in scope for this Blue Team case:

### 1. AD / IAM
Review areas:
- service availability
- user and group structure
- centralized access logic
- privilege separation
- basic account governance

### 2. Web Server
Review areas:
- service availability
- intended exposed path
- listening ports
- access behavior
- backend separation
- logging visibility

### 3. Database
Review areas:
- service availability
- intended backend access only
- restricted exposure
- application connectivity
- inclusion in backup logic

### 4. File Server
Review areas:
- authenticated access
- permission-based file access
- authorized versus unauthorized behavior
- service exposure
- shared data protection

### 5. Backup and Monitoring
Review areas:
- monitoring visibility over critical hosts/services
- useful event visibility
- backup artifact existence
- backup scope clarity
- restore-oriented readiness

### 6. Network Security
Review areas:
- firewall status
- intended versus unintended reachable ports
- controlled remote access
- backend isolation
- restriction of administrative paths

## In-Scope Review Activities
The following Blue Team activities are authorized and expected in this case:
- review service status
- review configuration state at a defensive level
- check exposure and access control behavior
- inspect logs and monitoring outputs
- inspect backup evidence
- compare intended architecture with actual behavior
- collect screenshots and command outputs
- document findings and remediation recommendations
- perform limited validation checks after corrective actions

## Out-of-Scope Areas
The following areas are out of scope for this case unless explicitly added later:
- full enterprise compliance audit
- large-scale forensic investigation
- production-grade incident response exercise
- deep malware analysis
- destructive testing
- denial-of-service style activity
- broad offensive exploitation beyond defensive validation needs
- external third-party systems not part of the project repository or deployment

## Review Boundaries
This Blue Team case is a defensive review, not a destructive exercise.

The review must remain:
- non-disruptive
- proportionate
- evidence-oriented
- aligned with the project environment
- limited to realistic validation and defensive analysis

The purpose is to evaluate and improve the infrastructure, not to damage or destabilize it.

## Assumptions
This review is performed under the following assumptions:
- the environment is project-scale and not enterprise-scale
- some elements may still be simplified due to MVP constraints
- documentation and deployment evidence are part of the review material
- the infrastructure is expected to be functional but may still contain gaps
- the review focuses on meaningful issues relative to the project scope
- risk ratings remain qualitative and project-oriented

## Authorized Evidence Sources
The following evidence sources may be used:
- screenshots
- service status outputs
- configuration excerpts
- firewall outputs
- logs
- monitoring dashboards
- access test results
- backup artifacts
- repository documentation
- validation notes

Evidence must be referenced later in:
- `03_Terrain_Card.md`
- `04_Evidence_Index.md`
- `05_Findings.md`
- `07_Remediation_Plan.md`
- `08_Retest_Results.md`

## Rules for Evidence Handling
Evidence collected during this case must follow these rules:
- keep filenames clear and reusable
- avoid storing unnecessary secrets
- mask passwords, tokens, or confidential values when needed
- keep only relevant technical proof
- ensure each important finding is tied to evidence
- keep evidence consistent with the actual state of the environment

## Authorized Review Methods
The following methods are acceptable in this Blue Team case:
- defensive configuration review
- visibility review through monitoring and logs
- access control verification
- service exposure verification
- role and permission review
- backup existence validation
- restore-oriented reasoning or limited validation
- comparison between intended design and observed reality

## Prohibited or Restricted Actions
The following actions are prohibited unless explicitly re-scoped:
- destructive modification of production-like data
- disabling core services for testing convenience
- deleting backup artifacts without reason
- making undocumented intrusive changes during review
- introducing unrelated tools that alter the environment significantly
- changing scope after findings appear without documenting it

## Severity / Risk Logic
A simple qualitative rating model is used in this case:

### Low
Minor issue with limited operational or security impact.

### Medium
Meaningful issue that should be corrected because it affects security posture, resilience, or management quality.

### High
Important issue that creates significant exposure, weakens critical service protection, or materially affects defensive credibility.

The purpose of this rating is prioritization, not false precision.

## Success Criteria for the Case
This Blue Team case will be considered successful if:
- scope is clear and respected
- evidence is collected properly
- findings are tied to observable facts
- risk reasoning is understandable
- remediation actions are practical
- retest logic is possible or documented
- the final Blue Team output remains coherent with the deployed environment

## Expected Outputs
This scope document supports the production of the following case outputs:
- timeline of the review
- terrain card
- evidence index
- findings list
- risk register
- remediation plan
- retest results
- executive summary

## Review Ownership
- Case Owner: To complete
- Reviewer(s): To complete
- Review Date(s): To complete
- Environment Version / Snapshot: To complete

## Environment Identification
Complete the following when the case is actively filled:

- Main review hostnames: To complete
- Main reviewed IP addresses: To complete
- Deployment state reference: To complete
- Monitoring reference: To complete
- Backup reference: To complete

## Notes and Exceptions
Use this section to document any scope adjustment, exception, or contextual note discovered during the review.

- To complete

## Conclusion
This document defines the review perimeter and operating rules for the Blue Team case `HOME_Run01`.

It ensures that the defensive review remains structured, evidence-based, and aligned with the actual project environment. All later Blue Team documents in this case must remain consistent with the scope defined here.