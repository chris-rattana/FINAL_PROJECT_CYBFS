# Security Controls

## Purpose
This section defines the main security controls implemented or planned for the infrastructure designed for the remote-first startup scenario.

The objective is to show how the project addresses the main operational and cybersecurity risks identified in the risk analysis while remaining realistic, understandable, and appropriate for an SME-scale environment.

These controls are designed to support:
- confidentiality of data and resources
- integrity of services and configurations
- availability of critical systems
- secure administration
- controlled remote access
- improved detection and recovery readiness

## Security Strategy
The project follows a practical defense-in-depth approach.

The goal is not to implement a fully mature enterprise security architecture, but to combine several realistic and complementary controls that reduce the most relevant risks for the selected environment.

The strategy is based on the following principles:
- least privilege
- centralized identity control
- reduced attack surface
- controlled exposure of services
- separation between user-facing and internal services
- monitoring and traceability
- recoverability through backup logic
- documented remediation capability

## 1. Identity and Access Control

### Centralized Identity Management
A centralized directory service is used to manage:
- user identities
- groups
- permissions
- access to shared resources and services

This reduces the risk of unmanaged accounts, inconsistent permissions, and privilege sprawl.

### Group-Based Permissions
Access to resources is assigned through groups and roles rather than through uncontrolled individual permissions wherever possible.

This improves:
- consistency
- maintainability
- traceability
- access review capability

### Least Privilege
Users and services must only receive the permissions necessary for their role.

This principle applies to:
- standard user access
- administrative access
- shared resources
- service-to-service interactions
- database access where applicable

### Separation of Privileged and Standard Accounts
Administrative tasks should not be performed from standard user accounts. Privileged access must be limited to dedicated administrative paths where possible.

This reduces the impact of account misuse or credential compromise.

## 2. Remote Access Protection

### VPN-Based Remote Access
Because the company is remote-first, remote connectivity is a major part of the architecture. Access to internal resources must therefore be protected through a VPN-based access path.

This helps:
- avoid unnecessary direct exposure of internal services
- restrict remote access to authenticated users
- create a clearer boundary between external and internal access

### Restricted Administrative Access
Administrative services must not be widely exposed. Remote administration should be limited to controlled paths, specific users, and justified access methods.

### Authentication Visibility
Authentication events and suspicious access attempts should be logged or made visible through monitoring mechanisms.

This improves:
- accountability
- anomaly detection
- response capability

## 3. Network Security Controls

### Host Firewalling
Each critical Linux host should use firewall rules to limit inbound traffic to required services only.

Examples of authorized services may include:
- VPN access
- web access on expected ports
- restricted internal communication between services
- administration ports only when justified

All unnecessary inbound exposure must be denied by default.

### Exposure Limitation
Only services that need to be reachable should be exposed. Internal services such as the database or directory backend should remain behind controlled internal paths whenever possible.

### Segmentation and Trust Boundaries
The architecture follows a simplified trust-boundary model:
- user access zone
- exposed service zone
- internal data zone
- administration and monitoring zone

Even in a small-scale project, this logic helps justify where services should be placed and how they should communicate.

### Minimal Open Ports Policy
The project applies a minimal exposure logic:
- open only required ports
- document each exposed service
- remove or close unused services
- review service exposure regularly

## 4. Web Security Controls

### Controlled Front-End Exposure
The web server acts as the main user-facing service and must be configured to expose only the necessary access path.

### Reverse Proxy Logic
Where relevant, the web server can be used as a controlled front layer separating external access from backend services.

### Service Hardening
The web layer should be hardened through:
- reduced unnecessary modules or features
- controlled configuration
- minimal exposure
- restricted access to backend components

### Logging
Web access and error logs should be enabled and preserved for operational visibility and incident review.

## 5. Database Security Controls

### Restricted Database Exposure
The database must not be directly exposed unless there is a clear technical reason to do so.

It should be reachable only through:
- the application path
- restricted internal hosts
- controlled administration paths where necessary

### Access Restriction
Database access should be limited through:
- service-specific credentials where relevant
- firewall restrictions
- limited authorized source paths
- role-based permissions inside the database when appropriate

### Configuration Protection
Database configuration and access methods must be documented and protected to reduce the risk of accidental exposure or weak defaults.

### Data Integrity Support
The database is part of the critical data layer and must be included in backup and recovery logic.

## 6. File-Sharing Security Controls

### Authenticated Access
The file-sharing platform must require authenticated access and must not operate as an open or anonymous share.

### Permission Management
Access to shared folders, files, or collaboration spaces must be aligned with user roles and group permissions.

### Data Exposure Reduction
The sharing structure should avoid:
- overly broad shared spaces
- unnecessary public visibility
- uncontrolled access inheritance

### Visibility
Where possible, file access, changes, or key events should be visible through logs or platform monitoring.

## 7. Monitoring and Logging Controls

### Monitoring Coverage
The project includes monitoring or visibility over critical services such as:
- host state
- service availability
- security-relevant events
- authentication activity
- system alerts where applicable

### Log Collection
Relevant logs should be collected or at least preserved for:
- system administration
- service troubleshooting
- security review
- Blue Team analysis

### Detection Support
The monitoring stack should help identify:
- service failures
- suspicious logins
- notable host events
- visibility gaps

The goal is not full SOC maturity, but usable operational and defensive awareness.

## 8. Backup and Recovery Controls

### Backup Scope
Critical assets covered by backup logic should include:
- application data
- shared files
- selected configurations
- important service states where relevant

### Backup Protection
Backup data must be treated as sensitive and protected against unauthorized access or accidental deletion.

### Restore Validation
A backup strategy is not sufficient unless restore capability is also considered. At least one restore-oriented test or validation path should be documented.

### Operational Value
These controls reduce the impact of:
- accidental deletion
- service corruption
- configuration loss
- partial infrastructure failure

## 9. Hardening Controls

### Baseline Hardening
Each critical host should follow a basic hardening logic, including:
- disabling unnecessary services
- limiting open ports
- using controlled administrative access
- removing avoidable defaults
- documenting important configuration choices

### Configuration Review
Security-related configuration must be reviewed to avoid:
- weak defaults
- overexposure
- inconsistent access control
- avoidable trust relationships

### Documentation of Hardening Decisions
Hardening measures should be documented so that they can be:
- reviewed
- justified
- reproduced
- tested during assessment

## 10. Basic Intrusion Prevention / Defensive Readiness

### Baseline Intrusion Prevention Logic
The final project requires at least basic intrusion prevention.

In this project, this requirement is addressed through a combination of:
- firewall restrictions
- exposure reduction
- controlled remote access
- host hardening
- monitoring and log visibility
- administrative access control

### Optional Extended Detection
If additional tooling is available, the project may also include:
- host-based alerting
- suspicious activity review
- monitoring rules for notable events

The goal remains realistic prevention and defensive readiness rather than advanced enterprise detection engineering.

## 11. Administrative Security Controls

### Restricted Privileged Access
Administrative access must be limited to authorized personnel and justified technical paths only.

### Traceability
Administrative actions should be documented or logged where possible.

### Change Awareness
Configuration changes affecting security posture should be identified and tracked in project documentation.

## 12. Mapping Controls to Main Risks

| Main Risk | Main Control Response |
|----------|------------------------|
| Unauthorized remote access | VPN, centralized authentication, restricted admin access, logging |
| Identity and privilege mismanagement | Samba AD, group-based permissions, least privilege |
| Web service exposure | Nginx front layer, firewalling, hardening, limited public exposure |
| Unauthorized database access | internal-only access paths, firewall rules, limited credentials |
| File leakage | authenticated access, permission management, controlled sharing |
| Service unavailability | monitoring, backup logic, restore readiness |
| Backup failure | documented backup scope, restore validation, backup protection |
| Insufficient monitoring | Wazuh or equivalent visibility, log collection, service monitoring |
| Misconfiguration | baseline hardening, documented configuration review |
| Admin compromise | privileged account separation, limited admin paths, traceability |

## 13. Security Control Limits
This project intentionally remains within SME-scale scope.

It does not aim to implement:
- full enterprise SOC maturity
- large-scale zero-trust enforcement
- advanced multi-region resilience
- highly complex IDS/IPS engineering
- full compliance framework implementation in depth

Instead, it implements a coherent baseline security model that is realistic, documentable, and defensible for the final project.

## Conclusion
The security controls defined in this project are designed to directly address the main risks of a remote-first startup infrastructure.

They combine identity control, secure remote access, exposure reduction, firewalling, hardening, monitoring, backup logic, and basic defensive readiness into a consistent security posture.

This approach ensures that security is integrated into the architecture and not treated as a separate afterthought.