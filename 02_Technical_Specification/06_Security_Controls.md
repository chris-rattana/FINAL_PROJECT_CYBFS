# Security Controls — CoreShield Infrastructure

## 1. Security Objective

The security model of the **CYBFS — CoreShield Infrastructure** project is based on a simple principle: build a compact environment in which each virtual machine has a distinct role, while ensuring that the overall platform remains observable, controlled, and technically defensible.

The implemented controls were selected to support a realistic final project scope without unnecessary complexity. The goal was not to simulate an enterprise-scale SOC, but to deploy a coherent infrastructure with real security visibility and validated service boundaries.

---

## 2. High-Level Security Approach

The environment was designed around four complementary security ideas:

- **role separation**
- **controlled service exposure**
- **centralized monitoring**
- **evidence-based validation**

Instead of concentrating every function on a single host, the project distributes responsibilities across dedicated nodes:

- `dc01` for identity and naming
- `app01` for application delivery
- `file01` for collaborative services
- `sec01` for monitoring and detection

This separation reduces confusion, improves readability, and creates a stronger security narrative than a monolithic deployment.

---

## 3. Identity and Naming Control

### 3.1 Centralized Domain Logic on `dc01`

The `dc01` node acts as the infrastructure backbone for identity and internal naming.  
It provides:

- domain-controller functionality
- Samba-based directory services
- internal DNS service on port 53
- name resolution for the other infrastructure nodes

This control improves operational consistency by ensuring that internal services can rely on stable hostnames instead of ad hoc addressing.

### 3.2 Security Benefit

Centralized naming and identity reduce operational ambiguity and support:

- cleaner internal communication
- easier service administration
- more reliable infrastructure validation
- stronger traceability of system roles

---

## 4. Service Separation and Exposure Control

### 4.1 Application Node Isolation (`app01`)

The application stack is isolated on `app01`.  
Validated components include:

- Nginx as front-end
- Gunicorn as application backend
- Flask as the application layer
- local PostgreSQL support

This separation ensures that the application logic is not mixed with monitoring or directory services.

### 4.2 Collaboration Node Isolation (`file01`)

The file-sharing and collaboration service is isolated on `file01`.  
Validated components include:

- Apache2
- PHP-FPM
- MariaDB
- Nextcloud

This design keeps collaborative services logically separated from the application node and from the monitoring node.

### 4.3 Security Benefit

By assigning different workloads to separate machines, the platform improves:

- service clarity
- troubleshooting simplicity
- exposure control
- monitoring readability

It also makes compromise scenarios easier to reason about, because each host has a clearly defined operational purpose.

---

## 5. Network Segmentation Logic

The project uses two network scopes:

### 5.1 NAT Network
Used for:
- administration from the host
- SSH access
- deployment and maintenance operations

### 5.2 Host-only Internal Network
Used for:
- internal service communication
- DNS resolution
- inter-node validation
- Wazuh agent-to-manager communication

### 5.3 Security Benefit

This structure provides a basic but meaningful distinction between:

- administrative access paths
- internal infrastructure traffic

Even in a compact lab, this separation improves control and makes the deployment more realistic than a flat single-network setup.

---

## 6. Monitoring and Detection Controls

### 6.1 Central Monitoring Node (`sec01`)

The `sec01` node hosts a Wazuh all-in-one deployment including:

- Wazuh manager
- Wazuh indexer
- Wazuh dashboard

This provides centralized monitoring, service visibility, and security event aggregation.

### 6.2 Agent Coverage

Wazuh agents were successfully deployed on:

- `dc01`
- `app01`
- `file01`

The agents are visible and active in the Wazuh dashboard, providing an operational monitoring perimeter across the three main service nodes.

### 6.3 Security Benefit

This control is one of the strongest elements of the project because it transforms the infrastructure from a set of functional VMs into a monitored environment with centralized visibility.

It supports:
- host visibility
- service monitoring
- event aggregation
- alerting capability
- evidence-backed validation

---

## 7. Access Validation as a Security Control

Validated access checks were performed for:

- the application hosted on `app01`
- the Nextcloud platform on `file01`
- the Wazuh dashboard on `sec01`

These checks confirm that the expected services are reachable while preserving the intended architecture.

### Security Benefit

A deployed service is not automatically a validated service.  
By explicitly confirming service accessibility and status, the project adds a practical control layer that reduces uncertainty and improves final deliverable credibility.

---

## 8. Port and Listening-Service Verification

The project includes explicit verification of critical listening ports, including:

- DNS on `dc01` (port 53)
- web exposure on `app01`
- web exposure on `file01`
- Wazuh ports on `sec01`
- agent communication from `app01` and `file01` to `sec01`

### Security Benefit

Port verification provides a simple but effective assurance that:
- expected services are listening
- unexpected listening states can be noticed
- monitoring connectivity is technically demonstrated

This strengthens the practical dimension of the security controls section.

---

## 9. Snapshot Strategy and Recovery Readiness

Stable snapshots were taken after validated deployment phases for key nodes.

This is not a replacement for enterprise backup strategy, but it remains a relevant operational safeguard for the scope of this project because it supports:

- rollback capability
- reproducibility
- safer demonstration handling
- controlled recovery points during finalization

---

## 10. Evidence-Backed Security Posture

The security posture of the project is not presented as theoretical.  
It is supported by real evidence available in `09_Appendices_Evidence`, including:

- VMware deployment screenshots
- service status outputs
- access validation captures
- listening-port proofs
- Wazuh dashboard and agent monitoring screenshots

This evidence-backed approach is important because it allows each declared security control to be tied to a visible technical proof.

---

## 11. Security Limitations

The project remains a compact lab deployment and therefore has deliberate limitations:

- no enterprise-grade redundancy
- no full SIEM engineering beyond the Wazuh scope
- no dedicated reverse proxy hardening beyond the implemented service stack
- no advanced network segmentation appliance layer
- no formal high-availability design

These limitations are acceptable within the educational and demonstrative scope of the project. The focus was placed on coherence, technical correctness, visibility, and proof.

---

## 12. Conclusion

The **CoreShield Infrastructure** implements a coherent set of practical security controls based on:

- centralized identity and naming
- role separation
- controlled service deployment
- internal network logic
- centralized monitoring and agent coverage
- explicit validation and technical evidence

The result is a small but credible cyber-oriented infrastructure that goes beyond simple service deployment by demonstrating observability, structure, and defensible system organization.
