# Known Limitations

## Purpose
This document identifies the main limitations of the deployed infrastructure and clarifies the boundaries of the project implementation.

The objective is to provide a realistic and transparent view of what the infrastructure currently delivers, what remains simplified at project scale, and which aspects would require further work in a more advanced or production-oriented environment.

This document helps position the project correctly:
- as a coherent and functional SME-scale infrastructure
- as a demonstrable MVP
- as a technically and security-oriented final project
- not as a full enterprise production platform

## General Positioning
The infrastructure has been designed to satisfy the core requirements of the final CYBFS project while remaining feasible within limited time, scope, and available resources.

As a result, the deployment intentionally prioritizes:
- coherence over unnecessary complexity
- functional integration over large-scale feature completeness
- realistic security controls over full enterprise security maturity
- documentation and demonstrability over advanced production automation

These limitations are normal and acceptable as long as they are clearly identified and justified.

## 1. Scale Limitation
The deployed infrastructure is designed for a small-to-medium remote-first startup scenario.

It is not intended to represent:
- a large enterprise environment
- a multi-site global organization
- a high-user-density production platform
- a heavily distributed architecture with complex scaling requirements

The project demonstrates architectural and security logic at SME scale rather than industrial scale.

## 2. Availability and Redundancy Limitation
The project does not aim to provide full production-grade high availability.

This means that the infrastructure may not include:
- active-active service redundancy
- clustered failover for all critical components
- load balancing at enterprise scale
- advanced automatic service recovery across multiple hosts
- zero-downtime architecture guarantees

The objective is to demonstrate a working and defendable infrastructure, not a full highly available enterprise platform.

## 3. Disaster Recovery Limitation
The project includes backup and recovery logic, but it does not implement a full enterprise disaster recovery architecture.

This means that the deployment may not include:
- automated off-site failover
- geographically distributed recovery sites
- fully orchestrated recovery runbooks
- production-grade business continuity guarantees
- formal SLA-backed recovery commitments

The project instead demonstrates baseline recoverability thinking through backup scope, restore-oriented validation, and recovery priorities.

## 4. Security Maturity Limitation
The project integrates realistic baseline security controls, but it does not aim to reproduce full enterprise security maturity.

This means that the deployment may not include:
- full zero-trust enforcement
- full SOC operations
- advanced detection engineering
- complete IDS/IPS coverage at scale
- full security orchestration and automated response
- advanced threat hunting capability

The security posture is intentionally designed as a strong baseline for an SME environment rather than a full mature enterprise cyber program.

## 5. Monitoring Limitation
The monitoring solution provides useful operational and security-oriented visibility, but it remains limited compared with enterprise observability platforms.

This means that the project may not include:
- full correlation across all infrastructure layers
- long-term retention and analytics at scale
- advanced alert engineering
- enterprise-wide performance observability
- deep custom detection content

The goal is to provide enough visibility to support operations, validation, and Blue Team reasoning.

## 6. Backup Limitation
The backup approach is realistic and documented, but it remains simplified compared with a production-grade backup program.

This means that the project may not include:
- multiple backup tiers with enterprise retention policy depth
- fully automated restore orchestration
- air-gapped recovery design
- complete off-site replication
- frequent live restore drills at scale

The project focuses instead on proving that critical assets are identified, backed up, and at least partially restorable.

## 7. Identity and Access Management Limitation
The identity model demonstrates centralized access governance, but it remains simplified compared with a mature enterprise directory environment.

This means that the project may not include:
- advanced federation features
- complex trust relationships
- large organizational unit hierarchies
- enterprise-grade identity lifecycle automation
- conditional access logic at broad scale

The project demonstrates the essential value of centralized identity management without reproducing every advanced directory feature.

## 8. Web Application Limitation
The web service supports the business logic of the project, but it is not intended to represent a fully mature commercial SaaS product.

This means that the deployment may not include:
- advanced application security testing coverage
- production-grade scaling architecture
- advanced session management architecture
- broad feature completeness
- extensive API ecosystem integration

The purpose is to provide a realistic service layer that can be integrated, protected, tested, and documented.

## 9. Database Limitation
The database deployment is designed as a protected backend component, but it is not intended to reproduce a highly available enterprise data platform.

This means that the project may not include:
- clustering
- replication across multiple nodes
- advanced backup topology
- performance tuning for high concurrency environments
- formal database governance processes

The goal is to demonstrate controlled backend data storage and secure integration with the application layer.

## 10. File-Sharing Limitation
The file-sharing service is designed for controlled collaboration, but it remains smaller in scope than a full enterprise document platform.

This means that the project may not include:
- advanced enterprise content governance
- full DLP controls
- large-scale retention and archival policy management
- broad multi-tenant collaboration models
- advanced workflow automation for document handling

The project focuses instead on secure, centralized, permission-based collaboration.

## 11. Network Security Limitation
The network security model provides strong baseline controls, but it remains simpler than a large enterprise network security architecture.

This means that the deployment may not include:
- complex multi-zone hardware segmentation
- advanced enterprise firewall ecosystems
- broad IDS/IPS deployment across multiple segments
- micro-segmentation at fine-grained scale
- automated network policy orchestration

The project demonstrates practical service exposure control, remote access protection, and internal backend protection appropriate for the scenario.

## 12. Automation Limitation
The project may include some structured deployment or configuration logic, but it does not necessarily provide full infrastructure-as-code or full deployment automation.

This means that the environment may still rely partly on:
- manual configuration steps
- simplified administration procedures
- documentation-driven repeatability rather than complete automated provisioning
- project-scale validation instead of industrial CI/CD for infrastructure

This is acceptable as long as the configuration remains understandable, documented, and reproducible enough for project review.

## 13. Compliance Limitation
The project takes compliance-related concerns into account in a practical sense, but it does not constitute a full compliance program or legal certification framework.

This means that the deployment does not claim:
- audited compliance certification
- full legal framework implementation
- complete regulatory mapping
- formal governance maturity equivalent to a production organization

Instead, it demonstrates baseline good practice in:
- controlled access
- traceability
- documentation
- backup awareness
- recoverability
- professional security reasoning

## 14. Testing Limitation
The testing and validation process is designed to prove functional and security coherence, but it is not equivalent to a full industrial qualification program.

This means that the project may not include:
- exhaustive automated test coverage
- large-scale load testing
- advanced resilience simulation
- long-duration stability benchmarking
- full production acceptance cycles

The project instead focuses on practical validation of core services, integration paths, access control, backup logic, monitoring visibility, and supporting security review.

## 15. Blue Team and Red Team Limitation
The Blue Team and Red Team deliverables are designed to remain realistic within the project scope.

This means that they may not represent:
- long-duration operational incident response maturity
- full penetration testing breadth across a large environment
- enterprise-scale attack emulation campaigns
- advanced purple teaming cycles over time
- full remediation governance with multiple stakeholder teams

Their value lies in showing that the deployed environment can be analyzed, challenged, improved, and documented through defensive and offensive perspectives.

## 16. Documentation Limitation
The documentation aims to be clear, professional, and coherent, but it remains tied to the scale and objectives of the final project.

It may therefore not include:
- highly formalized enterprise operational manuals
- full runbook libraries for all incident classes
- large-scale governance document sets
- exhaustive production support procedures

The documentation is designed first to:
- justify the architecture
- support validation
- support security review
- support presentation
- show professional project reasoning

## Future Improvement Areas
The following areas could be developed further in a more advanced version of the infrastructure:
- stronger redundancy and failover logic
- deeper monitoring and alerting coverage
- more advanced backup retention and restore testing
- stronger identity automation and conditional access
- broader hardening and security validation
- improved infrastructure automation
- deeper compliance mapping
- more advanced segmentation and traffic control
- expanded Blue Team and Red Team cycles

These improvements are natural next steps rather than signs of project failure.

## Why These Limitations Are Acceptable
These limitations are acceptable because the project is intentionally framed as a realistic final project with:
- limited time
- limited resources
- a need for demonstrability
- a focus on core infrastructure integration
- a focus on baseline security and documentation quality

The project is successful if it remains coherent, functional, secure at baseline, well documented, and defendable during review and presentation.

## Conclusion
The deployed infrastructure includes known limitations that are normal for an SME-scale final project.

These limits do not weaken the value of the project as long as they are clearly stated, justified, and understood. On the contrary, identifying them improves the credibility of the work by showing realistic technical judgment, transparency, and professional project positioning.