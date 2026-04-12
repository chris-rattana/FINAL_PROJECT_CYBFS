# Appendices and Evidence README

## Purpose
This folder contains the transversal appendices and supporting evidence for the final CYBFS project.

Its purpose is to:
- centralize reusable project proof
- preserve raw and supporting material outside the main deliverables
- improve traceability across architecture, deployment, Blue Team, Red Team, and presentation
- avoid overloading the main project documents
- support final review and oral presentation

This folder is not the primary location for structured analysis. It is the global evidence repository supporting the project.

## Role in the Project
The main project deliverables already contain:
- technical documentation
- deployment notes
- Blue Team case files
- Red Team engagement files
- project management documents
- final presentation material

This appendices folder exists to store the supporting proof that can be referenced from those deliverables when needed.

## Main Principles
The evidence stored here should be:
- clearly named
- reusable
- easy to understand
- linked to a real validation or review purpose
- organized by theme
- free of unnecessary secrets or sensitive data

## Folder Structure

### 01_Architecture_Diagrams
Contains architecture visuals and supporting diagrams:
- logical diagrams
- trust-zone diagrams
- service flow diagrams
- network overview diagrams

### 02_Deployment_Screenshots
Contains screenshots proving deployed services and components:
- application pages
- admin interfaces
- platform dashboards
- service access screens

### 03_Service_Status_Outputs
Contains raw outputs showing service state:
- systemctl outputs
- host/service status
- listening port outputs
- readiness outputs

### 04_Access_Control_Tests
Contains proof related to identity and permissions:
- authorized access proof
- denied access proof
- group membership proof
- permission validation

### 05_Firewall_Port_Proofs
Contains proof related to exposure and filtering:
- firewall status
- firewall rules
- port scans
- blocked path proof
- intended reachability proof

### 06_Monitoring_Backup_Proofs
Contains proof related to visibility and resilience:
- monitoring dashboards
- monitored hosts/services
- logs and event visibility
- backup artifacts
- restore-oriented notes

### 07_Blue_Team_Raw
Contains raw materials supporting the Blue Team case:
- extra logs
- raw outputs
- supporting screenshots
- technical notes used during defensive analysis

### 08_Red_Team_Raw
Contains raw materials supporting the Red Team engagement:
- raw reachability tests
- offensive notes
- scan excerpts
- blocked/unblocked path comparisons
- retest raw outputs

### 09_Presentation_Assets
Contains reusable assets for the oral presentation:
- final visuals
- diagrams
- summary screenshots
- cleaned images used in slides

## Recommended Naming Convention
Use meaningful filenames such as:
- `ARCH01_global_architecture.png`
- `DEP01_web_homepage.png`
- `STAT01_nginx_status.txt`
- `ACC01_authorized_file_access.png`
- `FW01_web_firewall_status.txt`
- `MON01_wazuh_dashboard.png`
- `BT01_auth_log_excerpt.txt`
- `RT01_port_scan_raw.txt`
- `PRES01_architecture_visual.png`

## Referencing Rules
When a file stored here is useful for a document:
- mention the filename in the relevant document
- keep the filename stable
- avoid duplicates across folders
- keep one clear source of truth

## Quality Rules
Each item stored here should:
- have a clear purpose
- remain readable
- support a real project claim
- be reusable in final review
- not duplicate unnecessary material

## Sensitive Information Handling
Before storing any proof:
- remove or mask passwords
- remove or mask tokens and secrets
- avoid exposing unnecessary confidential values
- keep only the technical material needed for validation

## Conclusion
This folder provides the global evidence backbone of the final CYBFS project.

Once populated, it will strengthen the project by centralizing architecture proof, deployment proof, access-control proof, firewall proof, monitoring and backup proof, Blue Team raw material, Red Team raw material, and final presentation assets in one structured location.