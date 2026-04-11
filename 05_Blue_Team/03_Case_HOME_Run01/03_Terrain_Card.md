# Terrain Card

## Case Identification
- Case ID: HOME_Run01
- Workstream: Blue Team
- Review Type: Defensive review
- Environment Type: SME-scale remote-first startup lab infrastructure
- Review Status: Initial defensive assessment

## Purpose
This document provides a compact operational snapshot of the environment reviewed in the Blue Team case `HOME_Run01`.

Its purpose is to:
- summarize the infrastructure under review
- identify the main technical components
- record the defensive context of the case
- support evidence collection and finding interpretation
- provide a quick reference for the rest of the Blue Team documentation

This terrain card is not a full technical specification. It is a practical review snapshot used to understand the environment from a defensive perspective.

## Environment Overview
The reviewed environment is a small-to-medium infrastructure built for a remote-first startup scenario.

It is designed to support:
- secure remote access
- centralized identity and access management
- a web-facing business service
- a protected backend database
- a centralized file-sharing service
- monitoring and backup logic
- baseline network and host security controls

The environment is project-scale, documented, and intended to be demonstrable rather than enterprise-scale.

## Review Context
The Blue Team case reviews the environment in its deployed and documented state.

The defensive review focuses on:
- how the infrastructure behaves in practice
- whether key controls are present
- whether services are exposed correctly
- whether access paths are controlled
- whether visibility and recovery logic exist
- whether the infrastructure remains defensible in a realistic SME context

The case is evidence-based and tied to the actual deployment.

## Main Components in the Reviewed Terrain

### 1. AD / IAM
Role:
- centralized user and group management
- structured access governance
- permission logic for shared resources and service access

Defensive interest:
- privilege separation
- user/group consistency
- centralized access control
- admin versus standard account logic

### 2. Web Server
Role:
- main user-facing service layer
- entry point for business service access
- controlled exposure of the application path

Defensive interest:
- exposed ports
- service reachability
- configuration quality
- logging visibility
- separation from backend services

### 3. Database
Role:
- protected backend data storage
- support for web or application logic
- persistent service data layer

Defensive interest:
- restricted reachability
- backend-only logic
- application-to-database integration
- backup inclusion
- controlled access

### 4. File Server
Role:
- centralized collaborative file access
- authenticated document sharing
- remote access to operational files

Defensive interest:
- authorized versus unauthorized access
- permission structure
- exposure level
- shared data protection
- backup coverage

### 5. Backup and Monitoring
Role:
- visibility over critical hosts and services
- support for operational awareness
- support for recovery after incident or loss

Defensive interest:
- monitored service coverage
- visible logs or events
- backup artifact existence
- restore-oriented readiness
- usefulness for Blue Team review

### 6. Network Security
Role:
- host-based firewalling
- exposure reduction
- backend isolation
- controlled remote access
- restriction of administrative paths

Defensive interest:
- intended versus unintended reachability
- remote access control
- admin path restriction
- backend protection
- consistency between architecture and actual exposure

## Main Defensive Review Questions
The terrain is reviewed through the following questions:

### Access Governance
- Is access centralized and coherent?
- Are privileges reasonably separated?
- Are users and groups aligned with intended usage?

### Exposure Control
- Are only intended services reachable?
- Are backend services protected from unnecessary direct access?
- Are administrative paths restricted?

### Service Integrity and Usability
- Are the critical services running as intended?
- Is the environment integrated rather than fragmented?
- Are the core service relationships functional?

### Visibility and Resilience
- Is monitoring usable?
- Are meaningful logs or events visible?
- Do backup artifacts exist?
- Is restore logic at least partially considered?

### Defensive Credibility
- Does the infrastructure look reviewable, supportable, and improvable?
- Are weaknesses identifiable and actionable?
- Is the environment mature enough to support Blue Team findings and remediation logic?

## Environment Characteristics
The terrain can be characterized by the following features:
- centralized identity model
- one user-facing web layer
- one protected backend database
- one collaborative file-sharing service
- one monitoring and backup support layer
- one baseline network protection model
- one remote-access-oriented business scenario

This creates a compact but realistic defensive review terrain.

## Key Assets Under Review
The most important assets in this terrain are:
- user identities and permissions
- application access path
- application data
- shared files
- service configurations
- backup artifacts
- monitoring visibility
- administrative access paths

These assets are central to both the operational value and the defensive posture of the project.

## Threat Focus Areas
The terrain is especially relevant for reviewing exposure to:
- unauthorized remote access
- weak privilege management
- excessive service exposure
- direct backend reachability
- weak file access control
- insufficient monitoring visibility
- weak backup clarity
- administrative overexposure
- misconfiguration of security controls

## Evidence Sources Available
The terrain card assumes evidence can be collected from:
- deployment documentation
- service status outputs
- screenshots
- access tests
- firewall outputs
- logs
- monitoring dashboards
- backup artifacts
- component-level technical notes

These sources are indexed later in the evidence file.

## Defensive Strength Indicators
The following elements would indicate a stronger defensive posture in this terrain:
- clear identity and permission structure
- minimal and justified service exposure
- backend services not broadly reachable
- authenticated and controlled file access
- monitoring visibility over critical components
- backup evidence with restore awareness
- restricted administrative paths
- documentation aligned with observed reality

## Typical Weakness Indicators
The following observations would typically indicate a weaker posture:
- users or groups not clearly managed
- unnecessary open ports
- direct backend exposure
- unclear or broad file access
- weak monitoring coverage
- backup logic not evidenced
- admin access too broad
- gaps between documentation and actual system behavior

## Environment Snapshot Fields to Complete
Complete the following with actual review values:

- Main hostnames reviewed: To complete
- Main IP addresses reviewed: To complete
- Main exposed service(s): To complete
- Main internal-only service(s): To complete
- Main admin access path(s): To complete
- Monitoring reference: To complete
- Backup reference: To complete
- Current deployment version / snapshot: To complete

## Analyst Notes
Use this section to record quick review notes on the overall environment:

- To complete

## Conclusion
This terrain card provides the operational snapshot of the environment reviewed in Blue Team case `HOME_Run01`.

It summarizes the infrastructure under review, the defensive focus areas, and the main assets and controls that matter for the case. Once completed with actual environment identifiers and observations, it will serve as the quick-reference backbone of the Blue Team review.