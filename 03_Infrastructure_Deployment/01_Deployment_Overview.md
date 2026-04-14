# Deployment Overview — CoreShield Infrastructure

## 1. Executive Summary

This document describes the final deployment state of the **CYBFS — CoreShield Infrastructure** project.

The environment was designed as a compact but realistic cyber-oriented infrastructure composed of four virtual machines, each with a clearly separated role:

- **dc01**: identity, directory, and DNS services
- **app01**: web application node
- **file01**: collaborative file-sharing node
- **sec01**: centralized security monitoring node

The final platform demonstrates a complete and operational environment with:

- centralized name resolution and domain services
- a validated web application stack
- a validated collaborative file-sharing service
- centralized monitoring and detection through Wazuh
- technical validation supported by real deployment evidence

---

## 2. Deployment Scope

The deployment was completed on **VMware Workstation** and structured around a dual-network logic:

- a **NAT network** used for administration and SSH access from the host
- a **host-only internal network** used for inter-VM communication inside the lab

This approach allowed the project to remain easy to manage while preserving a realistic internal infrastructure layout.

---

## 3. Final Infrastructure Inventory

### 3.1 dc01 — Domain Controller and DNS Node

**Hostname:** `dc01.cybfs.lab`  
**Internal IP:** `192.168.120.10`  
**NAT IP:** `192.168.86.133`

**Role in the platform:**
- domain and identity backbone
- internal DNS resolution for the lab
- central naming service for all nodes

**Validated functions:**
- internal DNS service listening on port 53
- successful name resolution for `app01`, `file01`, and `sec01`
- operational Active Directory / Samba-based control plane
- Wazuh agent installed and connected to `sec01`

---

### 3.2 app01 — Application Node

**Hostname:** `app01.cybfs.lab`  
**Internal IP:** `192.168.120.20`  
**NAT IP:** `192.168.86.134`

**Role in the platform:**
- application delivery node
- demonstration of a secured and monitored web service

**Validated functions:**
- Nginx running as web front-end
- Gunicorn running as application server
- Flask application operational
- local PostgreSQL validated
- web endpoint accessible from the lab
- Wazuh agent installed and connected to `sec01`

**Operational objective:**
- provide a realistic production-like application node inside the infrastructure

---

### 3.3 file01 — Collaboration and File-Sharing Node

**Hostname:** `file01.cybfs.lab`  
**Internal IP:** `192.168.120.30`  
**NAT IP:** `192.168.86.135`

**Role in the platform:**
- collaborative storage and document-sharing service
- practical business service inside the infrastructure

**Validated functions:**
- Apache2 running
- PHP-FPM operational
- MariaDB operational
- Nextcloud installed, validated, and accessible
- application status validated through `occ status`
- Wazuh agent installed and connected to `sec01`

**Operational objective:**
- provide a realistic collaboration platform representative of internal business services

---

### 3.4 sec01 — Centralized Monitoring and Detection Node

**Hostname:** `sec01.cybfs.lab`  
**Internal IP:** `192.168.120.40`  
**NAT IP:** `192.168.86.136`

**Role in the platform:**
- centralized security visibility
- monitoring, collection, and detection
- operational Blue Team support layer

**Validated functions:**
- Wazuh all-in-one deployment completed
- Wazuh manager active
- Wazuh indexer active
- Wazuh dashboard active
- HTTPS dashboard accessible
- agents from `dc01`, `app01`, and `file01` visible and active

**Operational objective:**
- provide centralized evidence-based security monitoring for the entire environment

---

## 4. Logical Architecture

The environment follows a simple and coherent service chain:

- **dc01** provides naming and identity foundations
- **app01** provides the web application service
- **file01** provides collaborative file-sharing capabilities
- **sec01** provides centralized monitoring across the infrastructure

This creates a realistic cyber-lab topology where infrastructure, services, and security controls are linked together rather than deployed as isolated components.

---

## 5. Network Logic

### 5.1 Internal Service Network
The internal host-only network is used for:
- DNS resolution
- service-to-service communication
- Wazuh agent-to-manager communication
- internal validation traffic

### 5.2 Administrative Network
The NAT network is used for:
- SSH administration from the host machine
- deployment operations
- maintenance access during build and validation phases

This separation improves clarity and supports a cleaner infrastructure narrative.

---

## 6. Monitoring Coverage

The final monitoring perimeter includes:

- **dc01** monitored by Wazuh agent
- **app01** monitored by Wazuh agent
- **file01** monitored by Wazuh agent
- **sec01** acting as centralized Wazuh server

This results in a monitored infrastructure with operational visibility on the three main service nodes.

---

## 7. Validation Status

The deployment reached a validated final state with the following results:

- all four VMs deployed successfully
- internal addressing finalized
- core services validated on each node
- application access validated
- Nextcloud access validated
- Wazuh dashboard access validated
- three Wazuh agents visible and active
- evidence package completed in `09_Appendices_Evidence`

The environment is therefore considered **deployed, operational, monitored, and evidence-backed**.

---

## 8. Snapshots and Recovery State

Stable snapshots were taken after successful deployment and validation phases in order to preserve rollback capability and demonstrate infrastructure maturity.

Examples include validated states for:
- `dc01`
- `file01`
- `sec01`

This snapshot strategy supports reproducibility and safer final presentation work.

---

## 9. Evidence References

Technical proof of deployment is available in:

- `09_Appendices_Evidence/02_Deployment_Screenshots`
- `09_Appendices_Evidence/03_Service_Status_Outputs`
- `09_Appendices_Evidence/04_Access_Control_Tests`
- `09_Appendices_Evidence/05_Firewall_Port_Proofs`
- `09_Appendices_Evidence/06_Monitoring_Backup_Proofs`

These appendices document:
- VMware state
- host identity and network information
- service status
- access validation
- listening ports
- monitoring state and active agents

---

## 10. Conclusion

The **CoreShield Infrastructure** deployment successfully demonstrates a compact but realistic cyber-oriented environment combining:

- identity and DNS services
- application hosting
- collaborative file-sharing
- centralized monitoring and detection

The project is not limited to theoretical design: the infrastructure was deployed, tested, monitored, and documented with real evidence.