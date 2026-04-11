# Rules of Engagement

## Engagement Identification
- Engagement ID: RT-ENG-REMOTE-01
- Workstream: Red Team
- Project: FINAL_PROJECT_CYBFS
- Assessment Type: Controlled offensive review / pentest-style engagement
- Environment Type: SME-scale remote-first startup lab infrastructure
- Status: Initial rules of engagement

## Purpose
This document defines the Rules of Engagement for the Red Team workstream of the final CYBFS project.

Its purpose is to:
- define what is authorized during the offensive review
- clarify scope boundaries and exclusions
- establish safe operating conditions
- prevent ambiguity during the assessment
- ensure the engagement remains controlled, non-destructive, and professionally structured

This document is the operational boundary reference for the Red Team engagement.

## Engagement Objective
The Red Team engagement is intended to identify meaningful offensive weaknesses in the deployed infrastructure through a realistic but controlled assessment.

The objective is to:
- assess attack surface
- identify offensive exposure
- document findings supported by evidence
- support remediation and retest
- strengthen the final project through adversarial review

The engagement is improvement-oriented and not intended to damage or destabilize the environment.

## In-Scope Targets
The following areas are in scope for the engagement:

### 1. Web Service Exposure
Review focus:
- exposed ports
- service reachability
- user-facing paths
- potential overexposure of the web layer
- separation between user-facing and backend services

### 2. Remote Access Path
Review focus:
- VPN or controlled remote access exposure
- remote entry points
- path restriction logic
- excessive external accessibility where relevant

### 3. Administrative Access Exposure
Review focus:
- externally or improperly reachable admin paths
- weak boundary between user-facing and admin access
- overexposed administration services

### 4. Backend Reachability
Review focus:
- unintended database reachability
- direct access to internal services
- trust-boundary failures between public and internal zones

### 5. Identity-Related Exposure
Review focus:
- identity service exposure where relevant
- weak separation between standard and privileged access paths
- identity-related access assumptions that may enlarge attack surface

### 6. File-Sharing Exposure
Review focus:
- exposed file-sharing access path
- authentication boundary
- over-broad access visibility where relevant

### 7. Network Exposure Logic
Review focus:
- intended versus unintended reachable ports
- service path filtering
- firewall behavior observable from the offensive perspective

## In-Scope Activities
The following activities are authorized in this engagement:
- review exposed services and ports
- test intended and unintended connectivity paths
- inspect user-facing service reachability
- perform limited enumeration of accessible services
- review access boundaries from an attacker-oriented perspective
- collect screenshots and command outputs
- document observed weaknesses
- validate whether a protected path is reachable or blocked
- perform retest after remediation where applicable

These activities must remain controlled and proportionate to the environment.

## Out-of-Scope Activities
The following activities are out of scope:
- destructive exploitation
- denial-of-service activity
- intentional service disruption
- malware deployment
- persistence mechanisms
- credential theft beyond limited project-scale validation logic
- deletion or corruption of project data
- destructive manipulation of backups
- broad exploitation of systems not explicitly related to the project environment
- any activity that would materially damage the environment or reduce its availability

## Testing Philosophy
The engagement follows a non-destructive offensive review model.

This means:
- testing is controlled
- validation is evidence-based
- unnecessary exploitation is avoided
- the environment must remain usable after the assessment
- findings must be meaningful and proportionate to the project scope

The Red Team work is not intended to simulate unrestricted hostile action. It is intended to assess offensive exposure safely and professionally.

## Authorized Methods
The following methods are acceptable:
- service discovery at project scale
- reachability verification
- exposure verification
- path validation
- administrative exposure checking
- backend reachability checking
- limited configuration observation where available
- screenshot and output-based evidence collection
- post-remediation validation

## Prohibited Methods
The following methods are prohibited unless explicitly re-scoped and documented:
- disruptive brute-force testing
- persistence installation
- destructive exploitation
- wiping, deleting, or modifying important data without need
- disabling core services
- altering the environment in undocumented ways
- introducing tools that create unnecessary instability
- causing intentional outage or denial of service

## Safety Requirements
The following safety principles apply throughout the engagement:
- preserve service availability
- avoid unnecessary modifications
- document any meaningful interaction affecting system state
- stop if a test could create disproportionate instability
- prefer proof of exposure over deep exploitation
- preserve the project environment for later remediation and retest

## Evidence Collection Rules
Evidence collected during the engagement must:
- be clearly named
- be linked to a review point or finding
- avoid storing unnecessary sensitive secrets
- remain understandable and reusable
- support findings, remediation, and final reporting

Acceptable evidence types include:
- screenshots
- command outputs
- port reachability outputs
- denied access proof
- service response proof
- firewall-related observations
- application behavior captures

## Exposure Validation Logic
When a path is tested, the reviewer should determine:
- is the service reachable
- is it reachable from the correct path only
- is it reachable when it should not be
- does the observed behavior match the documented architecture
- is the path blocked, filtered, or insufficiently restricted

This logic is especially important for:
- web exposure
- backend isolation
- remote access
- administrative access
- file-sharing access

## Authentication and Access Boundaries
The engagement may test whether:
- a service is reachable before authentication
- a protected path is incorrectly exposed
- admin or backend services are reachable from unintended paths

However, the engagement must remain controlled and avoid abusive or destabilizing authentication activity.

## Time and Execution Boundaries
Complete the following when finalizing the engagement:
- Planned review period: To complete
- Analyst(s): To complete
- Environment snapshot / version: To complete
- Main review window: To complete

If different phases are used, document them clearly:
- attack surface review
- evidence collection
- findings drafting
- retest phase

## Communication and Documentation Rules
During the engagement:
- all meaningful observations should be documented
- any major deviation from expected scope should be recorded
- findings should only be reported if evidence exists
- remediation suggestions should remain realistic and proportionate
- retest should only claim improvement if supported by new evidence

## Severity Logic
A simple qualitative severity scale is used:

### Low
Minor offensive weakness with limited practical impact.

### Medium
Meaningful offensive weakness that should be corrected.

### High
Important offensive weakness affecting service exposure, backend protection, administrative boundary, or overall security credibility.

This scale is used for prioritization, not for false precision.

## Success Criteria for the Engagement
The Red Team engagement will be considered successful if:
- scope is respected
- testing remains controlled and non-destructive
- attack surface review is meaningful
- findings are tied to evidence
- remediation guidance is practical
- retest logic is possible
- the final offensive deliverables are coherent with the real environment

## Exceptions and Scope Changes
Any scope extension, testing exception, or special rule must be documented here before being applied.

- To complete

## Notes
Use this section for contextual comments relevant to the offensive engagement.

- To complete

## Conclusion
This document defines the operational boundaries of the Red Team engagement for the final CYBFS project.

It ensures that the offensive review remains scoped, safe, non-destructive, and professionally structured, while still producing meaningful adversarial findings that improve the final infrastructure project.