# Technology Watch Report (English)

## Title
Technology Watch: Wazuh and Zero Trust Principles for a Remote-first SME Infrastructure

## Purpose
This report presents a short technology watch aligned with the final CYBFS project.  
Its purpose is to explain why two security-related technology directions are particularly relevant for the project environment:

- Wazuh as a monitoring and security-visibility platform
- Zero Trust principles as an access-control and architecture model for remote-first organizations

The report is written in English in order to match the project requirement for a short technology watch report.

## 1. Context
The final project is based on a remote-first startup scenario. In such an environment, users connect from different locations, internal resources must remain protected, and the organization depends heavily on digital services such as identity management, web access, file sharing, monitoring, and backup.

This context creates two major security needs:
- stronger visibility over hosts and services
- tighter control over who can access which resource, through which path, and under what conditions

For these reasons, Wazuh and Zero Trust principles are particularly relevant to the project.

## 2. Technology 1 — Wazuh

### 2.1 Overview
Wazuh is an open-source security platform that combines SIEM and XDR-oriented capabilities. Its documentation presents it as a platform that can protect endpoints and cloud workloads across on-premises, virtualized, containerized, and cloud-based environments.

This makes Wazuh especially interesting for a small but security-aware infrastructure because it supports centralized visibility without requiring a very large enterprise stack.

### 2.2 Why Wazuh Matters for This Project
In the project infrastructure, monitoring is not optional. The environment includes:
- identity and access management
- a web-facing service
- a backend database
- a file-sharing platform
- backup and operational monitoring
- network and host security controls

Wazuh is relevant here because it can help centralize security-relevant visibility across those components. In practice, this means it can support:
- host monitoring
- log collection
- event visibility
- security-oriented review of the environment
- stronger Blue Team analysis

### 2.3 Strengths of Wazuh for an SME-Scale Project
For a project like this one, Wazuh has several advantages:

#### Unified visibility
A single platform can provide visibility across multiple hosts and services.

#### Open-source positioning
This fits a cost-conscious SME or lab-oriented environment.

#### Security monitoring focus
Wazuh is not only a generic infrastructure monitor; it is oriented toward security visibility and defensive analysis.

#### Broad deployment compatibility
Its documentation shows support for on-premises, virtualized, containerized, and cloud-connected environments, which matches the flexible logic of the project.

### 2.4 Practical Limits
Wazuh is useful, but it does not automatically create full SOC maturity. For a small project environment, the main challenge is not only installation, but also:
- choosing meaningful visibility targets
- collecting useful events
- keeping the monitoring scope manageable
- avoiding a large amount of unused data

This means that in the project, Wazuh should be used in a focused and practical way rather than as a full enterprise observability platform.

### 2.5 Relevance to the Final Project
Wazuh is a strong choice for the project because it improves:
- operational visibility
- defensive credibility
- Blue Team evidence quality
- consistency between infrastructure and monitoring requirements

It therefore directly supports one of the project’s most important goals: building an infrastructure that is not only functional, but also observable and defensible.

## 3. Technology 2 — Zero Trust Principles

### 3.1 Overview
According to NIST, Zero Trust is an evolving set of cybersecurity paradigms that shifts defenses away from broad, implicit network trust and instead focuses on users, assets, resources, and policy-based access decisions.

In simple terms, Zero Trust means that no user, device, or service should be trusted only because it is “inside” the network. Access should be controlled according to identity, context, and resource sensitivity.

### 3.2 Why Zero Trust Matters for a Remote-first Startup
A remote-first organization is a very strong use case for Zero Trust thinking because:
- users connect from different networks and locations
- internal resources cannot rely only on perimeter trust
- remote access paths must remain controlled
- sensitive services such as admin interfaces and databases should not be broadly reachable

This makes Zero Trust particularly relevant for the final project, even if the project only implements a simplified SME-scale version of its principles.

### 3.3 Zero Trust Ideas Applied to This Project
The project does not implement a full enterprise Zero Trust architecture, but several of its core ideas are directly relevant:

#### Identity-centered access
Centralized IAM is used so that access decisions depend on users and permissions rather than scattered local accounts.

#### Resource-focused protection
The database, admin paths, and internal services are treated as protected resources rather than as services that should be broadly reachable.

#### Reduced implicit trust
The design assumes that being on the network is not enough to justify broad access.

#### Controlled remote access
VPN or controlled remote access acts as a boundary, but does not remove the need for internal access restriction.

#### Trust-boundary enforcement
The architecture distinguishes between user-facing, internal, and administrative services.

### 3.4 Strengths of Zero Trust Thinking in This Project
For the final project, Zero Trust is valuable because it improves the logic behind:
- firewall rules
- remote-access design
- backend isolation
- admin-path restriction
- service exposure limitation
- least-privilege reasoning

It helps justify why the infrastructure should not expose all services equally and why internal resources must remain behind tighter access boundaries.

### 3.5 Practical Limits
Zero Trust is not a single product and is not something that can be “installed” in one step. It is an architectural and policy-oriented model.

For a project like this one, the main practical limit is that only a baseline implementation is realistic. A full Zero Trust program would require:
- richer policy engines
- broader identity integration
- continuous trust evaluation
- more advanced access control and logging
- larger operational maturity

Therefore, the value of Zero Trust in this project is mainly conceptual and architectural: it improves design decisions even if the implementation remains simple.

## 4. Why These Two Topics Fit Together
Wazuh and Zero Trust principles are complementary.

- Zero Trust improves how access and trust boundaries are designed.
- Wazuh improves how the environment is observed and reviewed after deployment.

In other words:
- Zero Trust helps define who should access what
- Wazuh helps verify what is happening in the environment

Together, they are highly relevant for a remote-first infrastructure because remote work increases both:
- the need for access control discipline
- the need for operational and security visibility

## 5. Relevance to the CYBFS Project Deliverable
These two topics are directly relevant to the final project deliverables because they strengthen:
- the technical specification
- the security controls section
- the backup and monitoring logic
- the Blue Team workstream
- the Red Team review logic
- the final presentation narrative

Wazuh gives practical value to the monitoring layer, while Zero Trust gives strong conceptual value to the access-control and exposure model.

## 6. Conclusion
For a remote-first SME infrastructure, Wazuh and Zero Trust principles are highly relevant and complementary.

Wazuh is useful because it improves security-oriented visibility and supports operational and defensive review of the environment.

Zero Trust principles are useful because they help design a more disciplined infrastructure in which:
- access is controlled through identity and policy logic
- internal resources are protected
- remote access is limited to intended paths
- implicit trust is reduced

For the final CYBFS project, these two technology directions provide both practical and architectural value. They improve the realism, coherence, and professional quality of the infrastructure and help position the project as more than a simple service deployment exercise.
