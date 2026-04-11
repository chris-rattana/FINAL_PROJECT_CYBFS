# MVP Definition

## MVP Purpose
The purpose of the MVP is to deliver a realistic, functional, and secure small-scale infrastructure for a remote-first startup within the time and scope constraints of the final project.

The MVP is not intended to represent a full enterprise production environment. Its goal is to demonstrate the minimum set of integrated services, security controls, and documentation required to prove the feasibility, coherence, and professional quality of the project.

## MVP Scope
The MVP includes the minimum technical and documentary elements necessary to meet the project objectives:

- centralized identity and access management
- one functional web service
- one protected database connected to the web service
- one file-sharing service for remote users
- one backup mechanism or documented backup workflow
- one monitoring or visibility solution
- baseline security controls
- one documented Blue Team case
- one documented Red Team assessment
- supporting technical and project documentation

## Included Components

### 1. Identity and Access Management
The MVP includes a centralized identity system used to manage:
- users
- groups
- permissions
- access to core services

This component is necessary to avoid unmanaged access and to support administration and least-privilege logic.

### 2. Web Service
The MVP includes a web server or web application representing a business service used by the startup.

This service must:
- be reachable by authorized users
- be documented
- be integrated into the architecture
- interact with the backend database where relevant

### 3. Database
The MVP includes one database service used by the application stack.

This database must:
- be connected to the web service
- not be unnecessarily exposed
- use controlled access
- be documented as part of the architecture

### 4. File Sharing Service
The MVP includes one file-sharing or collaborative storage component.

This service must:
- allow remote access for authorized users
- use access controls
- support operational collaboration needs
- be documented and tested

### 5. Backup Capability
The MVP includes a basic backup and recovery logic.

This may consist of:
- scheduled backup procedures
- snapshot logic
- manual backup workflow with validation
- restoration evidence or documented restore test

The objective is to demonstrate that the environment is not only functional, but also recoverable.

### 6. Monitoring and Visibility
The MVP includes a basic monitoring or visibility capability.

This may include:
- service health checks
- logs
- dashboards
- host or network monitoring
- alert examples

The goal is to provide operational visibility over the infrastructure.

### 7. Baseline Security Controls
The MVP includes realistic baseline protections such as:
- firewall rules
- controlled service exposure
- hardening measures
- access restrictions
- segmentation or isolation logic
- logging

These controls must be justified and aligned with the SME context.

### 8. Blue Team Deliverable
The MVP includes one completed Blue Team case documenting:
- observed issues or weaknesses
- evidence
- risk evaluation
- remediation planning
- retest logic where applicable

### 9. Red Team Deliverable
The MVP includes one completed Red Team assessment documenting:
- scope
- methodology
- findings
- risk level
- recommendations
- remediation tracking or retest logic where applicable

## Out of Scope
The MVP does not aim to include:

- large-scale enterprise redundancy
- advanced multi-site disaster recovery
- full zero-trust architecture in depth
- full SOC or SIEM maturity
- complete compliance implementation
- complex production-grade clustering unless already available and fully justified
- highly advanced cloud-native orchestration at scale

These elements may be discussed as future improvements, but they are not required for the MVP.

## Why This Scope Is Appropriate
This scope is appropriate because it balances:
- realism
- feasibility
- integration
- security relevance
- demonstrability

It ensures that the project remains achievable while still covering the core expectations of the final project:
- infrastructure design
- deployment
- security
- documentation
- assessment
- presentation

## MVP Validation Criteria
The MVP will be considered valid if:

- the selected infrastructure scenario is clearly defined
- core services are present and integrated
- identity management is centralized
- access to services is controlled
- database exposure is limited and justified
- file-sharing is functional
- backup logic is documented and evidenced
- monitoring or visibility is demonstrated
- baseline security controls are implemented
- Blue Team and Red Team outputs are coherent with the environment
- documentation is clear and usable for presentation

## Expected Deliverable Form
The MVP must result in:
- a coherent project repository
- technical documentation
- deployment evidence
- security assessment outputs
- project management artifacts
- a final presentation

## Conclusion
The MVP is the minimum viable version of the final project that demonstrates a secure, integrated, and documented infrastructure adapted to a remote-first startup. It is intentionally limited in scope in order to remain feasible, understandable, and defendable, while still covering the essential operational and security requirements of the project.