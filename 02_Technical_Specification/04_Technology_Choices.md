# Technology Choices

## Purpose
This section explains the main technology choices made for the project and the rationale behind them.

The selected company profile is a remote-first startup. This profile naturally emphasizes secure remote access, cloud-oriented thinking, and controlled access to distributed business resources. The final project also requires an integrated infrastructure including a web server, a database, a file server or drive, Active Directory or centralized IAM, backup and monitoring, and baseline security controls. :contentReference[oaicite:3]{index=3} :contentReference[oaicite:4]{index=4}

The objective of these choices is not to build the most complex architecture possible, but to define a coherent, realistic, and defensible SME infrastructure that can be deployed, documented, tested, and presented clearly. This is also consistent with the project guidance to start small, keep the MVP achievable, and prioritize a working environment over unnecessary complexity. :contentReference[oaicite:5]{index=5} :contentReference[oaicite:6]{index=6}

## Selection Strategy
The technology stack was selected according to the following principles:
- coherence with the remote-first startup scenario
- compatibility with the minimum technical requirements
- realistic deployment at small scale
- ease of demonstration and documentation
- strong security justification without over-engineering
- good balance between operational usefulness and project feasibility

## Hosting Model
### Selected Approach
Hybrid / virtualized lab-oriented infrastructure

### Rationale
The project allows on-premise, cloud, or hybrid approaches depending on the selected company profile. For this project, a hybrid or virtualized SME-style environment is the most appropriate because it allows practical deployment, controlled exposure, and realistic service separation without requiring a full enterprise cloud implementation. :contentReference[oaicite:7]{index=7}

This approach also remains compatible with the project’s emphasis on building a realistic but feasible infrastructure within limited time and scope. :contentReference[oaicite:8]{index=8} :contentReference[oaicite:9]{index=9}

## Core Technology Choices

## 1. Directory Services / Identity and Access Management
### Selected Technology
Samba AD

### Why This Choice
The final project explicitly requires an Active Directory or centralized identity and access management component, and the suggested tools include both Windows Server AD and Samba AD. Samba AD is selected here because it provides centralized identity management while remaining consistent with a cost-conscious, flexible, and lab-friendly SME environment. :contentReference[oaicite:10]{index=10} :contentReference[oaicite:11]{index=11}

### Intended Role
Samba AD will be used to manage:
- users
- groups
- permissions
- centralized authentication logic
- access control for services and shared resources

### Why It Fits the Project
This choice supports one of the most important project needs: controlled remote access through centralized identity management. It also keeps the infrastructure more realistic than isolated local accounts spread across multiple machines.

## 2. Web Layer
### Selected Technology
Nginx

### Why This Choice
The project requires a web server or web application and explicitly lists Nginx and Apache among possible options. Nginx is selected because it is lightweight, widely used, and well adapted to reverse proxy, static serving, and controlled service exposure in a small-scale infrastructure. :contentReference[oaicite:12]{index=12} :contentReference[oaicite:13]{index=13}

### Intended Role
Nginx will be used to:
- expose the web service
- control inbound HTTP/HTTPS access
- support reverse proxy logic if needed
- separate the public-facing layer from backend services

### Why It Fits the Project
This is a simple and robust choice for a startup environment where service exposure must remain controlled and understandable.

## 3. Database Layer
### Selected Technology
PostgreSQL

### Why This Choice
The project requires a database securely connected to the web server and lists MySQL, PostgreSQL, and MongoDB as acceptable options. PostgreSQL is selected because it is reliable, mature, well documented, and suitable for structured application data in a secure SME environment. :contentReference[oaicite:14]{index=14} :contentReference[oaicite:15]{index=15}

### Intended Role
PostgreSQL will be used to:
- store application or business data
- support backend logic
- remain protected behind the web layer
- restrict direct exposure

### Why It Fits the Project
It provides a clear and professional relational database choice that is easy to justify in a technical specification and presentation.

## 4. File Sharing / Collaboration
### Selected Technology
Nextcloud

### Why This Choice
The project requires a file server or drive and suggests Samba, Nextcloud, OwnCloud, or NFS. For a remote-first startup, Nextcloud is the most coherent functional choice because it better matches distributed collaboration and remote access needs than a simple local file share alone. :contentReference[oaicite:16]{index=16} :contentReference[oaicite:17]{index=17} :contentReference[oaicite:18]{index=18}

### Intended Role
Nextcloud will be used to:
- provide shared document access
- centralize collaborative files
- support remote users
- enforce controlled access to shared resources

### Why It Fits the Project
This choice aligns directly with the remote-first context, where users need secure shared access to documents from different locations. It also makes the business value of the file-sharing component easier to demonstrate.

## 5. Remote Access
### Selected Technology
OpenVPN

### Why This Choice
The selected company profile highlights VPN, cloud-based logic, and remote access as primary concerns. The tool suggestions explicitly include OpenVPN among the security options. OpenVPN is therefore selected as the remote access component because it directly addresses the central business and security need of authenticated remote connectivity. :contentReference[oaicite:19]{index=19} :contentReference[oaicite:20]{index=20}

### Intended Role
OpenVPN will be used to:
- provide secure remote access to internal services
- reduce uncontrolled exposure
- create a clearer access boundary between public and internal services

### Why It Fits the Project
For this project, VPN is not a bonus feature; it is one of the most natural technical responses to the remote-first scenario.

## 6. Monitoring
### Selected Technology
Wazuh

### Why This Choice
The project requires a backup and monitoring system and explicitly cites Wazuh as an example. Wazuh is selected because it provides a strong monitoring and security visibility angle that supports both infrastructure supervision and security-oriented analysis. :contentReference[oaicite:21]{index=21} :contentReference[oaicite:22]{index=22} :contentReference[oaicite:23]{index=23}

### Intended Role
Wazuh will be used to:
- provide event visibility
- support host monitoring
- centralize useful security-related telemetry
- strengthen Blue Team analysis and operational oversight

### Why It Fits the Project
This choice improves coherence between the infrastructure layer and the Blue Team deliverables by making visibility part of the architecture.

## 7. Backup
### Selected Technology
Documented backup workflow with snapshots and scheduled data backup

### Why This Choice
The project requires backup capabilities but does not force one specific product. A documented and testable backup workflow is therefore selected as a realistic MVP choice, provided it includes backup evidence and at least one restore-oriented validation path. This is aligned with the project expectation that the environment should remain feasible and demonstrable at small scale. :contentReference[oaicite:24]{index=24} :contentReference[oaicite:25]{index=25}

### Intended Role
The backup approach will protect:
- application data
- shared files
- critical configuration
- selected service states where relevant

### Why It Fits the Project
This is sufficient for an SME-oriented final project as long as the backup logic is clearly documented and evidenced.

## 8. Firewall and Service Exposure Control
### Selected Technology
UFW on Linux hosts, with architecture-level exposure control

### Why This Choice
The project explicitly requires firewalls and access control policies and lists UFW, iptables, Suricata, pfSense, and OpenVPN among the security tools that may be used. UFW is selected as the baseline host firewall because it is simple, effective, and easy to justify in a lab-scale Linux-centric deployment. :contentReference[oaicite:26]{index=26} :contentReference[oaicite:27]{index=27} :contentReference[oaicite:28]{index=28}

### Intended Role
UFW will be used to:
- restrict inbound exposure
- allow only required ports
- separate user-facing and internal service paths
- support service hardening

### Why It Fits the Project
This keeps the security model practical and understandable while still satisfying the project requirement for baseline security controls.

## 9. Operating Model
### Selected Approach
Linux-based service deployment with Git-backed documentation

### Why This Choice
The project encourages practical tooling and documentation, and the overall final deliverable must remain clear, structured, and professionally defensible. A Linux-based stack for services combined with Git-based versioning for documentation provides a manageable and traceable operating model for the project. :contentReference[oaicite:29]{index=29} :contentReference[oaicite:30]{index=30}

### Intended Role
This model supports:
- reproducibility
- version tracking
- clearer change history
- easier organization of project deliverables

## Summary of Selected Stack
The selected reference stack for the project is:

- Directory Services: Samba AD
- Web Layer: Nginx
- Database: PostgreSQL
- File Sharing: Nextcloud
- Remote Access: OpenVPN
- Monitoring: Wazuh
- Backup: documented snapshot / backup workflow
- Firewall / Exposure Control: UFW
- Hosting Logic: hybrid or virtualized SME-style environment

## Trade-offs and Justification
These choices intentionally favor coherence, demonstrability, and operational clarity over maximal complexity.

Alternative technologies such as Apache, MySQL, MongoDB, Samba file shares, pfSense, Suricata, or full cloud-native orchestration would also be valid in principle because they are consistent with the project guidance. However, for this project, the selected stack offers a better balance between:
- remote-first business relevance
- security justification
- implementation feasibility
- documentation simplicity
- final presentation clarity :contentReference[oaicite:31]{index=31} :contentReference[oaicite:32]{index=32}

## Conclusion
The selected technologies form a coherent SME infrastructure stack tailored to a remote-first startup. Each choice supports a specific business and security need while remaining realistic within the scope of the final project.

The architecture is therefore intentionally designed to be:
- integrated
- secure
- explainable
- testable
- presentable