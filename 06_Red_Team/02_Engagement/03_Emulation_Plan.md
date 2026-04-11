# Emulation Plan

## Engagement Identification
- Engagement ID: RT-ENG-REMOTE-01
- Workstream: Red Team
- Project: FINAL_PROJECT_CYBFS
- Assessment Type: Controlled offensive review / pentest-style engagement
- Environment Type: SME-scale remote-first startup lab infrastructure
- Status: Initial emulation plan

## Purpose
This document defines the emulation plan for the Red Team workstream of the final CYBFS project.

Its purpose is to:
- describe the attacker-oriented review logic
- explain how the environment will be assessed from an offensive perspective
- organize offensive review phases in a controlled way
- support evidence collection, findings, remediation, and retest
- keep the engagement realistic, scoped, and non-destructive

This emulation plan is not a full adversary campaign simulation. It is a project-scale offensive review plan aligned with the actual infrastructure.

## Emulation Objective
The objective of this emulation plan is to guide a controlled adversarial review of the deployed infrastructure in order to:
- identify exposed attack paths
- validate whether critical services are reachable from unintended paths
- assess trust-boundary weaknesses
- observe offensive opportunities created by configuration or exposure gaps
- support practical remediation

The intent is to simulate realistic attacker-oriented reasoning without destabilizing the environment.

## Assessed Environment
The assessed environment is a remote-first startup infrastructure that includes:
- a user-facing web service
- a backend database
- centralized identity and access management
- a file-sharing service
- backup and monitoring logic
- network security controls
- remote-access assumptions

The emulation will focus on how these components appear and behave from an offensive perspective.

## Emulation Philosophy
This emulation follows a realistic but proportionate logic.

It is based on:
- exposure review rather than destructive exploitation
- verification of reachable versus protected paths
- validation of offensive opportunities that matter in the project context
- proof of weakness rather than unnecessary escalation
- support for remediation and retest

The plan remains:
- evidence-based
- scoped
- non-destructive
- aligned with the actual project environment

## Threat Perspective
The emulation assumes a realistic attacker interested in:
- identifying exposed services
- reaching sensitive backend assets
- exploiting weak trust boundaries
- finding overexposed administrative paths
- identifying weak access restrictions
- leveraging misconfiguration or visibility gaps

This attacker is not modeled as a nation-state or a long-term stealth actor. The attacker model is practical and project-scale.

## Main Emulation Themes
The offensive review is structured around the following themes:

### 1. External Exposure Review
Assess what is reachable from the exposed or user-facing side of the environment.

### 2. Remote Access Boundary Review
Assess whether remote access is properly controlled and whether it creates unintended reachability.

### 3. Administrative Exposure Review
Assess whether privileged paths are more reachable than they should be.

### 4. Backend Reachability Review
Assess whether internal services such as the database are reachable from unintended paths.

### 5. Trust-Boundary Review
Assess whether public, user-facing, internal, and admin zones are separated as intended.

### 6. Service Configuration Weakness Review
Assess whether visible service behavior suggests weak hardening or unnecessary exposure.

## Emulation Phases

## Phase 1 — Scope Confirmation
### Objective
Confirm the target environment and offensive review perimeter before testing begins.

### Main Actions
- review engagement scope
- review rules of engagement
- identify in-scope components
- identify expected exposure assumptions
- define review boundaries

### Expected Output
A confirmed offensive perimeter aligned with the actual deployment.

---

## Phase 2 — Attack Surface Identification
### Objective
Identify the exposed services, ports, paths, and access points that matter for the offensive review.

### Main Actions
- identify user-facing services
- identify remote access entry points
- identify reachable ports
- identify administrative paths that appear reachable
- identify possible access to backend services
- compare visible exposure with intended architecture

### Expected Output
A structured target surface worksheet showing what appears reachable and relevant.

---

## Phase 3 — Exposure and Reachability Validation
### Objective
Validate whether intended and unintended paths are actually reachable.

### Main Actions
- test expected web service reachability
- test database reachability from non-approved paths
- test whether file-sharing access paths are exposed as expected
- test whether admin ports or services are broadly reachable
- test whether VPN or controlled remote access behaves as intended
- record blocked versus reachable paths

### Expected Output
Evidence showing which paths are correctly protected and which are too open.

---

## Phase 4 — Boundary Weakness Review
### Objective
Assess whether trust boundaries between exposed, internal, and administrative services are sufficiently enforced.

### Main Actions
- review separation between web layer and backend layer
- review whether internal services leak exposure
- review whether admin paths are distinguishable and restricted
- review whether remote access broadens internal reachability too much
- review whether identity-related services appear overly exposed

### Expected Output
A clear view of boundary strengths and weaknesses.

---

## Phase 5 — Finding Consolidation
### Objective
Transform offensive observations into structured findings.

### Main Actions
- review collected evidence
- identify meaningful offensive weaknesses
- discard purely theoretical or low-value noise
- document realistic attack-surface findings
- assign qualitative severity
- prepare findings for reporting

### Expected Output
A documented findings set grounded in actual evidence.

---

## Phase 6 — Remediation Alignment
### Objective
Translate findings into realistic corrective actions.

### Main Actions
- define which exposures should be reduced
- define which admin paths should be restricted
- define which backend services should be better isolated
- define which access paths require stronger control
- document remediation priorities

### Expected Output
A remediation tracker aligned with the findings.

---

## Phase 7 — Retest
### Objective
Verify whether the identified weaknesses were actually reduced or removed after remediation.

### Main Actions
- repeat the relevant reachability checks
- confirm whether blocked paths remain blocked
- confirm whether overexposed services are no longer reachable
- confirm whether admin access is more restricted
- update status to resolved, partially resolved, or not resolved

### Expected Output
A retest report showing whether the offensive posture improved.

## Main Review Scenarios

## Scenario A — Exposed Web Service Review
### Goal
Assess whether the user-facing web layer is exposed only as intended.

### Review Focus
- expected service availability
- unnecessary extra ports
- unexpected service behavior
- separation from backend assets

### Main Question
Can the web layer be reached only through the intended path, and does it avoid revealing or exposing backend services?

---

## Scenario B — Backend Database Reachability Review
### Goal
Assess whether the database remains protected behind the intended internal boundary.

### Review Focus
- direct reachability from unapproved paths
- firewall filtering behavior
- mismatch between architecture and actual access

### Main Question
Can the database be reached where it should not be reachable?

---

## Scenario C — Administrative Exposure Review
### Goal
Assess whether administrative access paths are sufficiently restricted.

### Review Focus
- externally visible admin ports
- admin path exposure
- distinction between user-facing and admin access
- restricted versus broad reachability

### Main Question
Can an attacker reach an administrative service more easily than intended?

---

## Scenario D — Remote Access Boundary Review
### Goal
Assess whether remote-access logic expands the attack surface beyond what is acceptable.

### Review Focus
- VPN or controlled access entry path
- internal service reachability after connection
- over-broad access through remote path

### Main Question
Does remote access provide only the intended reachability, or does it create unnecessary offensive opportunity?

---

## Scenario E — File Service Exposure Review
### Goal
Assess whether the file-sharing service exposure and access logic appear appropriately restricted.

### Review Focus
- visible access path
- authentication boundary
- excessive exposure of shared resources
- permission-related surface indicators

### Main Question
Is the file-sharing path exposed in a way that creates unnecessary offensive opportunity?

## Evidence Expectations
During emulation, collect:
- screenshots
- command outputs
- scan or reachability outputs
- denied-path proof
- service response proof
- connectivity validation notes
- firewall-related observations
- offensive interpretation notes

Each major observation should be tied to evidence in the Red Team evidence index.

## Emulation Success Criteria
The emulation plan is considered successful if:
- attack surface was reviewed coherently
- reachable and blocked paths were identified
- findings are tied to evidence
- the engagement remained non-destructive
- remediation priorities were clearly derived
- retest was possible after correction

## Known Limits
This emulation plan does not aim to include:
- destructive exploitation
- stealth persistence
- malware execution
- long-term adversary behavior
- enterprise-scale lateral movement simulation
- advanced multi-stage intrusion operations

Its purpose is to provide a realistic offensive review at project scale.

## Completion Fields
Complete the following when the emulation is actively finalized:
- Main analyst: To complete
- Review dates: To complete
- Environment snapshot: To complete
- Main exposed targets identified: To complete
- Main denied paths observed: To complete
- Main findings produced: To complete

## Conclusion
This emulation plan defines the attacker-oriented review logic for the Red Team workstream of the final CYBFS project.

It organizes the offensive assessment into controlled phases focused on attack surface, exposure validation, boundary review, and improvement-oriented reporting. Once populated with real evidence and final observations, it will provide a structured and credible adversarial review of the deployed infrastructure.