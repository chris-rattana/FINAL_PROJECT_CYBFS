# Red Team Methodology README

## Purpose
This document defines the methodology used for the Red Team part of the final CYBFS project.

Its purpose is to:
- explain the offensive review logic used in the project
- show how the deployed environment is assessed from an adversarial perspective
- structure the Red Team engagement documentation
- connect attack-surface observations to findings, remediation, and retest logic

This methodology is designed for a realistic SME-scale infrastructure and is aligned with the deployed environment of the remote-first startup scenario.

## Red Team Position in the Project
The Red Team workstream is not a generic pentest disconnected from the project. It is built on top of the actual deployed environment and focuses on:
- exposed services
- access paths
- backend protection boundaries
- identity-related exposure
- remote access assumptions
- network reachability
- configuration weaknesses visible from an attacker-oriented perspective

The Red Team role in this project is to identify meaningful offensive weaknesses, document realistic risk, and support corrective improvement of the deployed environment.

## Main Objectives
The Red Team methodology aims to:
- review the deployed infrastructure from an adversarial perspective
- identify meaningful attack paths and exposure weaknesses
- assess how an attacker could interact with the environment
- document findings in a structured way
- support remediation planning
- support retest after corrective actions
- produce a short pentest-style deliverable aligned with the final project

## Scope of Red Team Review
The Red Team methodology covers the main components of the deployed infrastructure:
- Web Server
- Network Security
- Remote Access path
- AD / IAM exposure where relevant
- Database exposure
- File-sharing exposure
- administrative paths
- backend reachability assumptions

The objective is not to simulate a large enterprise red team program, but to perform a realistic project-scale offensive assessment grounded in the actual environment.

## Red Team Review Logic
The methodology follows a structured sequence:

1. define engagement scope and rules
2. identify attack surface
3. review reachable services and exposure paths
4. collect evidence
5. document findings
6. assess risk
7. define remediation tracking
8. perform retest where applicable
9. produce a concise pentest-style conclusion

This sequence ensures that the Red Team work remains controlled, evidence-based, and aligned with the actual infrastructure.

## Core Methodology Steps

## 1. Engagement Framing
The first step is to define:
- what is being assessed
- what is in scope
- what is excluded
- what assumptions apply
- what testing limits must be respected

This prevents ambiguity and keeps the offensive review proportionate to the project environment.

## 2. Attack Surface Identification
The second step is to identify the relevant attack surface.

Typical review targets include:
- exposed web ports
- remote access entry points
- administrative service exposure
- backend reachability from unintended paths
- access control weaknesses
- weak separation between user-facing and internal components

## 3. Evidence Collection
The third step is to preserve proof that supports findings.

Evidence may include:
- screenshots
- scan results
- service banners
- connection attempts
- denied-path proof
- firewall observations
- application behavior
- configuration excerpts where relevant
- notes on reachability and exposure

Evidence must be:
- clearly named
- tied to a finding or validation point
- reusable in remediation and presentation

## 4. Finding Identification
A finding is documented when a meaningful offensive weakness, exposure gap, or exploitable condition is observed.

Typical Red Team finding themes include:
- excessive exposure
- weak access boundaries
- reachable backend service paths
- overly broad administrative access
- weak remote access control
- service misconfiguration
- insufficient separation between public and internal layers

Each finding should be tied to actual evidence.

## 5. Risk Evaluation
Each finding should be assessed according to:
- what is exposed
- how realistic the offensive opportunity is
- what the operational or security impact could be
- how urgent remediation should be

A simple qualitative rating can be used:
- Low
- Medium
- High

This keeps the methodology understandable and defensible.

## 6. Remediation Tracking
Each significant finding should lead to one or more remediation actions.

Remediation should remain:
- realistic
- technically relevant
- proportionate to project scale
- clearly connected to the finding

Examples:
- close unnecessary ports
- restrict admin paths
- isolate backend services
- tighten VPN or remote access exposure
- improve firewall rules
- strengthen access control boundaries

## 7. Retest Logic
If a remediation is applied, the Red Team case should include retest logic.

The purpose of retest is to verify:
- whether the original weakness still exists
- whether the attack path has been removed or reduced
- whether the risk level was reduced

Retest should stay focused and evidence-based.

## 8. Pentest-Style Reporting
At the end of the engagement, the Red Team case should produce:
- engagement framing
- rules of engagement
- attack surface worksheet
- evidence index
- findings
- pentest report
- remediation tracker
- retest report

This makes the Red Team contribution directly usable in the final project.

## Main Engagement Documents
The Red Team engagement is structured around the following files:

### 01_Engagement_Letter.md
Defines the engagement context, mission, and assessment purpose.

### 02_Rules_of_Engagement.md
Defines scope boundaries, limits, and permitted testing logic.

### 03_Emulation_Plan.md
Defines the high-level offensive review path and attacker-oriented logic.

### 04_Target_Surface_Worksheet.md
Indexes target surfaces, exposed paths, and offensive review points.

### 05_Evidence_Index.md
Indexes screenshots, outputs, scans, and technical proof.

### 06_Findings.md
Lists and explains the identified offensive weaknesses.

### 07_Pentest_Report.md
Provides the structured pentest-style reporting output.

### 08_Remediation_Tracker.md
Tracks remediation actions linked to findings.

### 09_Retest_Report.md
Records post-remediation validation of offensive weaknesses.

## Offensive Review Principles
The Red Team methodology follows these principles:
- scope first
- realism over exaggeration
- evidence first
- offensive relevance linked to the actual environment
- non-destructive testing
- improvement-oriented reporting
- clear boundaries between exposure review and disruptive action

## Typical Finding Categories
The following categories are especially relevant for this project:
- excessive exposed ports
- reachable backend services
- weak remote access boundaries
- administrative access overexposure
- weak separation between public and internal services
- overly permissive service paths
- weak identity-related exposure
- misconfiguration that enlarges attack surface

## What This Methodology Is Not
This methodology is not intended to be:
- a full enterprise red team program
- a stealth intrusion simulation
- a destructive attack exercise
- a persistence-based offensive campaign
- a malware deployment exercise
- a long-duration adversary emulation program

It is a structured project-scale offensive methodology adapted to an infrastructure final project.

## Quality Criteria for a Good Red Team Engagement
A Red Team engagement is considered good if:
- scope is clear
- evidence is present
- findings are meaningful
- offensive logic is realistic
- remediation is practical
- retest is documented where possible
- conclusions are aligned with the actual infrastructure

## Conclusion
This methodology provides a structured offensive framework for assessing the deployed infrastructure of the final CYBFS project.

It ensures that the Red Team work remains scoped, evidence-based, realistic, and aligned with the actual technical environment. Once populated with real observations and proofs, it will strengthen the project by showing a credible offensive review process.