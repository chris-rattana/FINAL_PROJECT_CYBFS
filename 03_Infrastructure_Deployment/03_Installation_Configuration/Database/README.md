# Database Installation and Configuration

## Purpose
This document records the installation and configuration logic of the database component deployed in the project infrastructure.

Its purpose is to provide a clear and reproducible view of:
- the deployment objective
- the installation steps
- the configuration choices
- the security decisions
- the validation points
- the evidence expected

This document is part of the infrastructure deployment proof and complements the component description already provided in the deployment section.

## Selected Technology
PostgreSQL

## Deployment Objective
The objective of this deployment is to provide the backend data service of the infrastructure.

This component is required in order to:
- store structured application data
- support the business logic of the web service
- provide persistent backend storage
- remain securely connected to the web server
- support backup and recovery logic
- contribute to the operational credibility of the final project

## Deployment Scope
The database installation covers:
- package installation
- service activation
- initial database configuration
- network access restriction
- application connectivity preparation
- basic hardening and service protection
- validation of service availability
- collection of deployment evidence

## Host Role
This host is dedicated to the database layer of the infrastructure.

Its main responsibilities are:
- run the database service
- store backend application data
- support controlled connectivity from the web or application layer
- remain protected from unnecessary direct exposure
- support backup and recovery workflows

## Prerequisites
Before installation, confirm the following:
- the host is installed and reachable
- network configuration is stable
- hostname is correctly defined
- package sources are available
- administrative access is available
- firewall logic is planned
- backend integration assumptions are known
- the application-side connection requirements are identified

## Installation Logic
The installation is performed in a structured order to reduce configuration errors and unnecessary exposure.

### Step 1 — Prepare the Host
Prepare the system before installing the database:
- update packages
- confirm hostname
- confirm IP addressing assumptions
- verify network reachability
- confirm the host is ready for service deployment

### Step 2 — Install PostgreSQL
Install the required database packages.

Document:
- package names
- installation command used
- version notes if relevant

### Step 3 — Enable and Start the Service
Ensure that PostgreSQL starts correctly and is enabled after installation.

Document:
- service name
- enable/start commands
- startup verification logic

### Step 4 — Create the Initial Database Structure
Create the initial elements needed for the project.

Document:
- database name
- application user or service account
- basic privilege logic
- ownership or access notes

### Step 5 — Configure Network Access
Configure the service so that only intended paths can reach the database.

Document:
- listening configuration
- allowed source hosts or networks
- internal-only or restricted reachability assumptions
- configuration files modified

### Step 6 — Apply Basic Hardening
Keep the service protected and limited to project needs.

Document:
- unused exposure removed
- restricted connectivity
- minimal required access only
- separation between administrative and service usage where relevant

### Step 7 — Prepare Application Connectivity
Configure the database so that the web or application layer can connect through the intended backend path.

Document:
- host used by the application
- target port
- database name
- user used for service connection
- any secure configuration notes without exposing secrets

### Step 8 — Validate Service Availability
Confirm that the database service is operational and usable.

Document:
- service status
- local connection proof
- application-to-database connectivity proof
- restricted exposure proof

## Suggested Configuration Notes
The following elements should be recorded clearly after deployment.

### Hostname
Record the hostname used for the database host.

### IP Address
Record the server IP address used in the lab environment.

### Service Port
Record the PostgreSQL service port used by the deployment.

### Database Name
Record the name of the application database.

### Application User
Record the service account name used by the application.

### Configuration Files
Record the main PostgreSQL configuration files modified for the deployment.

### Allowed Connectivity Notes
Record which host or service is allowed to connect and why.

## Security Configuration Notes
The database must be deployed with baseline security considerations.

Record the following:

### Restricted Exposure
Document which ports are open and why.

### Firewall Logic
Document the firewall rules applied to the database host.

### Backend-Only Access Logic
Document how direct user or public access is avoided.

### Limited Accounts and Privileges
Document how the database user model follows least-privilege logic.

### Backup Inclusion
Document how database content is included in backup scope.

### Logging or Monitoring Notes
Document what service visibility exists for the database.

## Example Sections to Complete During Deployment

### Installed Packages
- To complete

### Hostname
- To complete

### IP Address
- To complete

### Service Port
- To complete

### Database Name
- To complete

### Application User
- To complete

### Configuration File Paths
- To complete

### Main Commands Used
- To complete

### Service Status Notes
- To complete

### Connectivity Notes
- To complete

### Firewall Rules Notes
- To complete

## Validation Checklist
Use this checklist after deployment:

- [ ] host prepared correctly
- [ ] PostgreSQL installed successfully
- [ ] service enabled and started
- [ ] application database created
- [ ] service account created
- [ ] intended connectivity configured
- [ ] application connectivity confirmed
- [ ] direct unnecessary exposure restricted
- [ ] firewall logic applied
- [ ] backup inclusion documented
- [ ] evidence captured

## Evidence to Collect
Store the following proof in the corresponding screenshots/evidence folder:
- screenshot or output of service status
- command output showing database existence
- command output showing application user existence
- configuration excerpt showing intended connectivity
- screenshot or output proving application-to-database connection
- firewall status output
- proof that the database is not broadly exposed
- backup-related proof where relevant

## Common Issues to Watch
During installation, pay attention to:
- service not starting correctly
- incorrect bind or listen configuration
- wrong host-based access configuration
- application credentials mismatch
- firewall blocking intended backend connectivity
- database port being more exposed than intended
- permission misconfiguration
- forgetting to include the database in backup logic

## Known Limits
This installation remains project-scale and does not aim to reproduce a full enterprise database platform with clustering, replication, advanced tuning, or high-availability orchestration.

The objective is to demonstrate:
- a working backend database
- secure integration with the web service
- restricted exposure
- basic hardening
- backup awareness
- clear technical documentation

## Conclusion
This document records the installation and configuration logic of the database component.

Once completed with actual commands, values, validation outputs, and screenshots, it will serve as a reproducible and defensible proof that the infrastructure includes a functional and protected backend data service securely connected to the web layer.