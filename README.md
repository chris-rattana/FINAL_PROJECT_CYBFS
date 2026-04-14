# CYBFS - CoreShield

## Project Title
Secure Infrastructure Design, Deployment, Monitoring and Validation for a Distributed Collaboration Environment

## Project Overview
CYBFS - CoreShield is a final cybersecurity infrastructure project focused on building, securing, monitoring, and validating a realistic small-scale enterprise environment.

The project demonstrates how a structured infrastructure can support essential business services while keeping security, visibility, and operational validation at the center of the design.

The environment was built around four dedicated virtual machines:
- **dc01**: centralized identity, authentication, and DNS services
- **app01**: application node hosting the operational web service stack
- **file01**: secure file-sharing and collaboration node powered by Nextcloud
- **sec01**: centralized security monitoring node powered by Wazuh

This repository gathers the complete project documentation, deployment evidence, validation outputs, and presentation materials required for the CYBFS final submission.

## Project Theme
**CoreShield**

CoreShield represents a minimal yet credible cyber-oriented infrastructure model designed to combine:
- secure service delivery
- centralized identity and name resolution
- monitored collaboration services
- evidence-based validation
- defensive visibility through centralized monitoring

## Main Objectives
- Design a coherent and realistic multi-service infrastructure
- Deploy core business and infrastructure services across dedicated virtual machines
- Implement practical security controls and role separation
- Centralize monitoring and endpoint visibility with Wazuh
- Validate service accessibility, listening ports, and monitoring coverage
- Produce structured technical documentation and evidence-backed deliverables

## Final Infrastructure Scope
The final deployed environment includes:
- **Identity and DNS services** on `dc01`
- **Web application stack** on `app01`
- **Secure file-sharing platform (Nextcloud)** on `file01`
- **Centralized monitoring and detection platform (Wazuh)** on `sec01`
- **Wazuh agent coverage** on `dc01`, `app01`, and `file01`
- **Deployment evidence and validation outputs** stored in `09_Appendices_Evidence/`

## Core Architecture Summary
| VM | Role | Main Services |
|---|---|---|
| `dc01` | Identity / DNS node | Samba AD DC, DNS |
| `app01` | Application node | Nginx, Gunicorn, Flask, PostgreSQL |
| `file01` | Collaboration node | Apache2, PHP-FPM, MariaDB, Nextcloud |
| `sec01` | Security monitoring node | Wazuh manager, indexer, dashboard |

## Security Logic
The project follows a simple but strong security logic:
- separate core roles across dedicated machines
- avoid collapsing identity, application, collaboration, and monitoring into one host
- monitor critical nodes from a centralized security platform
- validate exposed services and internal communication paths
- keep evidence for deployment, service state, access tests, and monitoring results

## Repository Structure
- `00_README_GLOBAL.md` : global project overview
- `01_Context_PRD/` : context, needs analysis, PRD, MVP definition
- `02_Technical_Specification/` : architecture, risks, controls, backup, testing
- `03_Infrastructure_Deployment/` : deployment overview and implementation documentation
- `04_Project_Management/` : planning, budget, roadmap, project tracking
- `05_Blue_Team/` : Blue Team deliverables and defensive analysis
- `06_Red_Team/` : Red Team deliverables and pentest-oriented outputs
- `07_Technology_Watch/` : technology watch and research material
- `08_Final_Presentation/` : presentation slides and speaking material
- `09_Appendices_Evidence/` : screenshots, command outputs, validation proofs, monitoring evidence

## Evidence and Validation
The repository includes real validation material demonstrating that the infrastructure is not only documented, but effectively deployed and tested.

Evidence includes:
- VMware deployment screenshots
- service status outputs from each VM
- access validation for the web application, Nextcloud, and Wazuh
- listening port proofs
- centralized monitoring screenshots showing active agents

## Deliverables
- Global project documentation
- Technical specification files
- Infrastructure deployment documentation
- Project management files
- Blue Team and Red Team deliverables
- Technology watch report
- Final presentation materials
- Evidence pack supporting deployment and validation claims

## Project Status
**Infrastructure deployed and validated.**

Current status:
- `dc01` operational and monitored
- `app01` operational and monitored
- `file01` operational and monitored
- `sec01` operational with Wazuh dashboard and active endpoint visibility
- evidence pack completed and organized

## Conclusion
CYBFS - CoreShield delivers a compact but serious cybersecurity infrastructure project based on real deployment work, real monitoring, and real validation outputs.

The result is a coherent environment that combines infrastructure services, application hosting, collaboration capabilities, centralized monitoring, and professional documentation in a single final project repository.
