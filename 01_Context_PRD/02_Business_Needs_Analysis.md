# Business Needs Analysis

## Overview
The project is built for a remote-first startup that requires a secure, reliable, and manageable infrastructure adapted to distributed work. The company depends on digital access to internal resources, shared files, business applications, and administrative services.

Because employees operate remotely, the infrastructure must support secure access, centralized control, service availability, and clear operational visibility.

## Core Problem
The company needs to operate efficiently with remote users while controlling common infrastructure and cybersecurity risks. Without a structured environment, the organization is exposed to:
- uncontrolled access to internal resources
- inconsistent user and privilege management
- weak visibility over events and incidents
- poor resilience in case of service failure or data loss
- fragmented collaboration practices
- increased attack surface due to remote exposure

## Business Needs
### 1. Secure Access for Remote Users
Remote employees must be able to access company resources in a secure and controlled way. The infrastructure must prevent informal or excessive access and support authenticated, managed usage.

### 2. Centralized Identity and Access Management
The organization needs a central point to manage users, permissions, groups, and access rights. This is necessary to simplify administration, reduce errors, and support least-privilege access control.

### 3. Web Application Availability
The company requires a web service or internal business application accessible to authorized users. This service must remain available, stable, and properly connected to backend data.

### 4. Secure Database Usage
The database must support the application while remaining protected from unauthorized access. It must not be directly exposed without justification and must follow basic hardening and access restriction principles.

### 5. File Sharing and Collaboration
Remote users need a central file-sharing solution to exchange, store, and access working documents. Access must be managed according to user roles and operational needs.

### 6. Backup and Recovery Readiness
The company needs the ability to preserve critical data and restore services or files in case of incident, corruption, or accidental deletion.

### 7. Monitoring and Visibility
Administrators need visibility over the state of services, basic security events, and infrastructure health. Without monitoring, failures or suspicious activity may remain unnoticed.

### 8. Baseline Security Controls
The infrastructure must include practical and realistic protections such as:
- access control
- service hardening
- firewall rules
- segmentation or exposure limitation
- logging
- basic incident-readiness

## User Needs
### Administrators
- manage users and permissions
- monitor services
- maintain infrastructure
- respond to issues
- verify backup status

### Remote Employees
- authenticate securely
- access business services
- use shared files
- work reliably from different locations

### Management
- ensure continuity of activity
- reduce operational and security risk
- justify infrastructure choices
- maintain a realistic cost/complexity balance

## Security Needs
The project must protect confidentiality, integrity, and availability at an SME scale.

### Confidentiality
Sensitive data and internal resources must only be accessible to authorized users.

### Integrity
System configurations, database content, and shared files must be protected against unauthorized modification.

### Availability
Core services must remain operational and recoverable in case of incident.

## Operational Constraints
- limited project duration
- SME-level budget assumptions
- realistic deployment scope
- need for clear documentation
- limited complexity compared with enterprise-grade environments

## Technical Constraints
- the infrastructure must remain demonstrable
- all core services must be documented
- the environment must be testable from both operational and security perspectives
- security measures must remain realistic and explainable

## Success Criteria
The project will be considered successful if:
- all core infrastructure services are deployed or clearly demonstrated
- access is controlled through centralized identity management
- the web service, database, and file-sharing service are integrated
- backup and monitoring are documented and demonstrated
- security controls are implemented and justified
- Blue Team and Red Team outputs are coherent with the infrastructure
- the full project is clearly documented and presentable

## Conclusion
The company’s main need is not only to deploy technical services, but to build a coherent, secure, and manageable infrastructure adapted to remote work. The project must therefore combine operational usefulness, security controls, administration simplicity, and clear documentation.