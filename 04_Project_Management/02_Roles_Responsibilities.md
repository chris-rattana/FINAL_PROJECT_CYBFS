# Roles and Responsibilities

## Purpose
This document defines the main project roles and their responsibilities for the final CYBFS project.

Its purpose is to:
- clarify who is responsible for what
- show that the project is managed in a structured way
- support planning, accountability, and coordination
- strengthen the professional quality of the project management file

Even if the project is carried by a small team or partially by one main contributor, roles are still defined in order to reflect a realistic project organization.

## Role Allocation Logic
The project is organized around the main workstreams required to deliver the final infrastructure project:
- architecture and technical design
- infrastructure deployment
- security implementation
- Blue Team analysis
- Red Team assessment
- project management and documentation
- final presentation preparation

These responsibilities may be distributed across several team members or partially concentrated depending on the actual team size.

## Main Roles

## 1. Project Lead
### Main Responsibility
Ensure the overall coherence of the project from planning to final delivery.

### Core Tasks
- define project direction
- supervise scope and priorities
- ensure consistency between business context, architecture, deployment, and security
- track project progress
- coordinate deliverables
- ensure final readiness for review and presentation

### Expected Contribution
The Project Lead ensures that the project remains structured, realistic, and aligned with the final objectives.

## 2. Infrastructure Architect
### Main Responsibility
Design the overall infrastructure and define the main technical choices.

### Core Tasks
- define the target architecture
- choose the technology stack
- justify technical design decisions
- define trust boundaries and service roles
- align the design with business needs and project constraints
- support technical specification writing

### Expected Contribution
The Infrastructure Architect ensures that the project is technically coherent, understandable, and defendable.

## 3. System and Services Administrator
### Main Responsibility
Deploy and configure the core infrastructure services.

### Core Tasks
- install and configure AD / IAM
- install and configure the web service
- install and configure the database
- install and configure the file-sharing service
- support system-level troubleshooting
- preserve technical deployment notes and validation evidence

### Expected Contribution
The System and Services Administrator ensures that the environment is actually functional and integrated.

## 4. Network and Security Administrator
### Main Responsibility
Implement and validate baseline security controls across the infrastructure.

### Core Tasks
- configure firewall rules
- control service exposure
- protect backend services
- define remote access logic
- support network segmentation or trust-boundary enforcement
- document security controls and their rationale

### Expected Contribution
The Network and Security Administrator ensures that the infrastructure is not only functional, but also protected in a realistic and demonstrable way.

## 5. Monitoring and Resilience Owner
### Main Responsibility
Implement monitoring, backup, and recovery logic.

### Core Tasks
- configure monitoring visibility
- document monitored hosts and services
- define backup scope
- configure or document backup workflows
- validate backup artifact existence
- support restore-oriented validation
- preserve resilience-related evidence

### Expected Contribution
The Monitoring and Resilience Owner ensures that the infrastructure remains observable, manageable, and recoverable.

## 6. Blue Team Analyst
### Main Responsibility
Review the deployed environment from a defensive and operational security perspective.

### Core Tasks
- review logs, monitoring outputs, and system state
- identify weaknesses or findings
- document risks and recommendations
- prepare remediation planning
- support retest reasoning where applicable
- align findings with the real deployed environment

### Expected Contribution
The Blue Team Analyst ensures that the project includes a meaningful defensive review grounded in actual evidence.

## 7. Red Team / Pentest Analyst
### Main Responsibility
Assess the deployed environment from an offensive or adversarial perspective.

### Core Tasks
- define testing scope and methodology
- review attack surface
- identify exposures or exploitable weaknesses
- document findings and recommendations
- support remediation tracking and retest logic
- align offensive analysis with the actual environment

### Expected Contribution
The Red Team / Pentest Analyst ensures that the project demonstrates realistic offensive assessment and security improvement logic.

## 8. Documentation Owner
### Main Responsibility
Ensure that project documentation is complete, readable, and coherent.

### Core Tasks
- structure repository documentation
- maintain consistency across deliverables
- ensure that technical content is understandable
- organize screenshots, outputs, and evidence
- support clarity of the technical specification and deployment documentation
- reduce gaps between implementation and written deliverables

### Expected Contribution
The Documentation Owner ensures that the final project is professional, traceable, and easy to review.

## 9. Presentation Owner
### Main Responsibility
Prepare the final presentation and ensure that the project can be explained clearly.

### Core Tasks
- define presentation structure
- extract key results from technical documentation
- prepare diagrams, visuals, and speaking notes
- align the presentation with evaluation expectations
- support delivery readiness
- prepare concise explanation of architecture, findings, and lessons learned

### Expected Contribution
The Presentation Owner ensures that the final work is not only built and documented, but also clearly communicated.

## Responsibility Matrix by Workstream

| Workstream | Primary Role | Supporting Roles |
|-----------|--------------|------------------|
| Project direction and scope | Project Lead | Documentation Owner, Presentation Owner |
| Architecture design | Infrastructure Architect | Project Lead, Network and Security Administrator |
| AD / IAM deployment | System and Services Administrator | Network and Security Administrator |
| Web service deployment | System and Services Administrator | Infrastructure Architect |
| Database deployment | System and Services Administrator | Infrastructure Architect |
| File-sharing deployment | System and Services Administrator | AD / IAM support, Documentation Owner |
| Network protection and remote access | Network and Security Administrator | Infrastructure Architect |
| Monitoring and backup | Monitoring and Resilience Owner | System and Services Administrator |
| Blue Team review | Blue Team Analyst | Monitoring and Resilience Owner |
| Red Team review | Red Team / Pentest Analyst | Network and Security Administrator |
| Documentation structure | Documentation Owner | All roles |
| Final presentation | Presentation Owner | Project Lead, Documentation Owner |

## Example Allocation for a Small Team
If the project is handled by a small team, one person may cover several roles.

A realistic distribution may look like this:

### Team Member 1
- Project Lead
- Infrastructure Architect
- Presentation Owner

### Team Member 2
- System and Services Administrator
- Monitoring and Resilience Owner

### Team Member 3
- Network and Security Administrator
- Blue Team Analyst
- Red Team / Pentest Analyst

### Shared Responsibility
- Documentation Owner role shared across the team, with one person responsible for final consistency

## Example Allocation for a Single Main Contributor
If one main contributor performs most of the project work, the following logic can be used:

### Main Contributor
- Project Lead
- Infrastructure Architect
- System and Services Administrator
- Network and Security Administrator
- Monitoring and Resilience Owner
- Documentation Owner
- Presentation Owner

### Analytical Role Separation
Even in a single-contributor context, the Blue Team and Red Team roles should still be treated as distinct review perspectives in order to preserve professional structure and reasoning.

## Responsibility Principles
The project follows the following responsibility principles:
- each major workstream has a clear owner
- technical decisions must remain documented
- evidence collection must happen during the work, not only at the end
- security analysis must remain tied to the actual deployed environment
- final presentation must be prepared from documented material
- deliverable quality is a shared responsibility even when roles are distinct

## Accountability Expectations
Each role owner is expected to:
- complete assigned workstreams
- maintain clarity and traceability
- preserve supporting evidence
- communicate blockers when they appear
- contribute to final project coherence

## Known Limits
This role model reflects a project-scale organization and not a full enterprise delivery organization.

It does not aim to reproduce:
- large team structures
- formal department boundaries
- enterprise governance committees
- separate production, security, and PMO organizations

The goal is to show clear ownership and professional structure appropriate to the final project.

## Conclusion
This document defines the main roles and responsibilities required to deliver the final CYBFS project in a structured and professional way.

It helps show that the project is not only a technical build, but also a managed delivery combining planning, ownership, implementation, security review, documentation, and communication.