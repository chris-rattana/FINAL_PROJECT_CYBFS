# File Server Installation and Configuration

## Purpose
This document records the installation and configuration logic of the file-sharing component deployed in the project infrastructure.

Its purpose is to provide a clear and reproducible view of:
- the deployment objective
- the installation steps
- the configuration choices
- the security decisions
- the validation points
- the evidence expected

This document is part of the infrastructure deployment proof and complements the component description already provided in the deployment section.

## Selected Technology
Nextcloud

## Deployment Objective
The objective of this deployment is to provide the centralized file-sharing and collaboration service of the infrastructure.

This component is required in order to:
- centralize shared business documents
- support remote collaboration
- provide authenticated and controlled access to files
- reduce unmanaged file exchange practices
- integrate shared data into backup and recovery logic
- contribute to the operational credibility of the final project

## Deployment Scope
The file-sharing installation covers:
- service installation
- initial platform configuration
- storage setup
- user and access preparation
- controlled exposure of the service
- basic hardening and security-oriented settings
- validation of service availability
- collection of deployment evidence

## Host Role
This host is dedicated to the file-sharing layer of the infrastructure.

Its main responsibilities are:
- run the collaborative file-sharing platform
- provide centralized shared storage
- support access for authorized remote users
- enforce permission-based access
- support backup and recovery workflows

## Prerequisites
Before installation, confirm the following:
- the host is installed and reachable
- network configuration is stable
- hostname is correctly defined
- package sources are available
- administrative access is available
- firewall logic is planned
- storage location assumptions are known
- integration with identity or user-access logic is identified

## Installation Logic
The installation is performed in a structured order to reduce configuration errors and unnecessary exposure.

### Step 1 — Prepare the Host
Prepare the system before installing the file-sharing platform:
- update packages
- confirm hostname
- confirm IP addressing assumptions
- verify network reachability
- confirm the host is ready for service deployment

### Step 2 — Install the Required Components
Install the packages or software components required for Nextcloud and its dependencies.

Document:
- package names
- installation command used
- dependency notes if relevant
- version notes if relevant

### Step 3 — Configure the Web Access Layer
If the file-sharing platform relies on a web access path, configure the required service path and supporting components.

Document:
- listening port or URL path
- site or platform root
- host/service configuration used for access
- configuration files modified

### Step 4 — Configure Storage
Prepare the storage location used by the platform.

Document:
- storage path
- permissions applied
- ownership or service user notes
- expected data location

### Step 5 — Perform Initial Platform Setup
Complete the initial file-sharing platform setup.

Document:
- platform administrator account creation
- application data path
- integration notes with the rest of the infrastructure
- initial platform access validation

### Step 6 — Configure Access Logic
Prepare the first access structure needed for the project.

Document:
- test user logic
- group-based access notes if used
- shared folder or space structure
- permission model assumptions

### Step 7 — Apply Basic Hardening and Exposure Control
Keep the service protected and limited to project needs.

Document:
- exposed ports
- administrative access restrictions
- disabled defaults where relevant
- platform exposure limitations
- firewall rules

### Step 8 — Validate Service Availability
Confirm that the file-sharing service is operational and usable.

Document:
- service status
- browser access proof
- login test
- authorized file access proof
- restricted access proof where applicable

## Suggested Configuration Notes
The following elements should be recorded clearly after deployment.

### Hostname
Record the hostname used for the file-sharing host.

### IP Address
Record the server IP address used in the lab environment.

### Access URL or Port
Record the URL path, hostname, or service port used for access.

### Data Storage Path
Record the storage path used by the platform.

### Platform Administrator Account
Record the admin account name without exposing credentials.

### Configuration Files
Record the main configuration files modified for the deployment.

### User / Group Access Notes
Record how access is organized for users, groups, or shared spaces.

## Security Configuration Notes
The file-sharing service must be deployed with baseline security considerations.

Record the following:

### Authenticated Access
Document how unauthenticated or open access is avoided.

### Permission Logic
Document how access is restricted according to intended user or group logic.

### Firewall Logic
Document the firewall rules applied to the host.

### Exposure Control
Document which ports or access paths are exposed and why.

### Backup Inclusion
Document how shared files and platform data are included in backup scope.

### Logging or Monitoring Notes
Document what visibility exists for service access or platform state.

## Example Sections to Complete During Deployment

### Installed Packages
- To complete

### Hostname
- To complete

### IP Address
- To complete

### Access URL or Port
- To complete

### Data Storage Path
- To complete

### Platform Administrator Account
- To complete

### Configuration File Paths
- To complete

### Main Commands Used
- To complete

### Service Status Notes
- To complete

### Access Structure Notes
- To complete

### Firewall Rules Notes
- To complete

## Validation Checklist
Use this checklist after deployment:

- [ ] host prepared correctly
- [ ] required components installed successfully
- [ ] service enabled and started
- [ ] storage path configured
- [ ] platform setup completed
- [ ] admin access confirmed
- [ ] authorized user access validated
- [ ] unauthorized or unrelated access restricted
- [ ] firewall logic applied
- [ ] backup inclusion documented
- [ ] evidence captured

## Evidence to Collect
Store the following proof in the corresponding screenshots/evidence folder:
- screenshot or output of service status
- screenshot of the login page or platform home page
- screenshot proving administrator access
- screenshot proving authorized user access to shared files
- screenshot proving denied or restricted access for an unrelated user
- configuration excerpt if relevant
- firewall status output
- backup-related proof where relevant

## Common Issues to Watch
During installation, pay attention to:
- incorrect storage path permissions
- service not starting correctly
- web access path misconfiguration
- platform setup errors
- admin account confusion
- overexposed service ports
- missing permission separation between users
- forgetting to include the shared data path in backup logic

## Known Limits
This installation remains project-scale and does not aim to reproduce a full enterprise collaboration suite with advanced workflow automation, DLP, multi-tenant governance, or enterprise content lifecycle management.

The objective is to demonstrate:
- a working file-sharing platform
- authenticated and controlled access
- support for remote collaboration
- integration with the rest of the infrastructure
- backup awareness
- clear technical documentation

## Conclusion
This document records the installation and configuration logic of the file-sharing component.

Once completed with actual commands, values, validation outputs, and screenshots, it will serve as a reproducible and defensible proof that the infrastructure includes a functional and controlled file-sharing service adapted to a remote-first startup scenario.