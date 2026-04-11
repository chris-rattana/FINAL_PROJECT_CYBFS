# AD / IAM Installation and Configuration

## Purpose
This document records the installation and configuration logic of the AD / IAM component deployed in the project infrastructure.

Its purpose is to provide a clear and reproducible view of:
- the deployment objective
- the installation steps
- the configuration choices
- the security decisions
- the validation points
- the evidence expected

This document is part of the infrastructure deployment proof and complements the component description already provided in the deployment section.

## Selected Technology
Samba AD

## Deployment Objective
The objective of this deployment is to provide a centralized identity and access management service for the infrastructure.

This component is required in order to:
- manage users centrally
- organize permissions through groups
- support controlled access to services and shared resources
- reduce dependence on unmanaged local accounts
- strengthen administration and access governance

## Deployment Scope
The AD / IAM installation covers:
- service installation
- initial domain or directory setup
- creation of administrative access
- user and group structure preparation
- basic security-oriented configuration
- validation of service availability
- collection of deployment evidence

## Host Role
This host is dedicated to centralized identity and access management.

Its main responsibilities are:
- maintain the identity service
- store user and group directory information
- support authentication and access governance
- provide a structured administrative foundation for the rest of the infrastructure

## Prerequisites
Before installation, confirm the following:
- the host is installed and reachable
- network configuration is stable
- hostname is correctly defined
- time settings are correct
- package sources are available
- administrative access is available
- baseline firewall logic is planned

## Installation Logic
The installation is performed in a structured order to reduce configuration errors.

### Step 1 — Prepare the Host
Prepare the system before installing the directory service:
- update packages
- confirm hostname
- confirm network settings
- verify DNS assumptions
- ensure the host is ready for service installation

### Step 2 — Install Required Packages
Install the packages required for Samba AD and related administration tools.

Document:
- package names
- installation command used
- any version-specific notes if relevant

### Step 3 — Provision the Directory Service
Provision the Samba AD environment using the chosen domain configuration.

Document:
- domain name
- realm
- role of the server
- DNS mode used
- any key provisioning options

### Step 4 — Configure Service Startup
Ensure that the required services are enabled and start correctly after provisioning.

Document:
- services enabled
- services disabled if replaced
- startup verification logic

### Step 5 — Apply Initial Administrative Setup
Define the first administrative access path and confirm that directory administration is possible.

Document:
- administrative account logic
- password or credential policy note without exposing secrets
- basic administration validation

### Step 6 — Create Initial Structure
Prepare the first identity objects needed for the project:
- test user(s)
- test group(s)
- administrative separation logic
- resource access groups where relevant

### Step 7 — Validate Service Availability
Confirm that the identity service is operational and usable.

Document:
- service status
- user creation test
- group creation test
- basic access validation

## Suggested Configuration Notes
The following elements should be recorded clearly after deployment.

### Hostname
Record the hostname used for the AD / IAM server.

### Domain / Realm
Record the selected domain and realm naming.

### IP Address
Record the server IP address used in the lab environment.

### DNS Logic
Record how name resolution is handled for the identity service.

### Administrative Access Method
Record how administrators access and manage the service.

### Service Names
Record the main services enabled for the Samba AD deployment.

## Security Configuration Notes
The AD / IAM component must be deployed with baseline security considerations.

Record the following:

### Restricted Exposure
Document which ports are required and why.

### Firewall Logic
Document the firewall rules applied to the host.

### Administrative Access Restriction
Document how administrative access is limited.

### Privileged Account Separation
Document how standard and administrative identities are separated.

### Documentation of Groups and Permissions
Document the logic used for identity groups and access control.

## Example Sections to Complete During Deployment

### Installed Packages
- To complete

### Domain Name
- To complete

### Realm
- To complete

### Hostname
- To complete

### IP Address
- To complete

### DNS Configuration Notes
- To complete

### Main Commands Used
- To complete

### Services Enabled
- To complete

### Test Users Created
- To complete

### Test Groups Created
- To complete

### Access Logic Notes
- To complete

## Validation Checklist
Use this checklist after deployment:

- [ ] host prepared correctly
- [ ] required packages installed
- [ ] Samba AD provisioned successfully
- [ ] service starts correctly
- [ ] administrative access confirmed
- [ ] test user created
- [ ] test group created
- [ ] group membership validated
- [ ] firewall logic applied
- [ ] evidence captured

## Evidence to Collect
Store the following proof in the corresponding screenshots/evidence folder:
- screenshot of service status
- provisioning output
- hostname and IP proof
- screenshot or command output showing created users
- screenshot or command output showing created groups
- proof of group membership
- proof of applied firewall status where relevant

## Common Issues to Watch
During installation, pay attention to:
- hostname mismatch
- DNS inconsistency
- time synchronization issues
- incorrect provisioning parameters
- service startup failure
- permission confusion between standard and admin users
- missing firewall review after installation

## Known Limits
This installation remains project-scale and does not aim to reproduce a full enterprise identity platform with advanced federation, multi-site replication, or lifecycle automation.

The objective is to demonstrate:
- centralized identity management
- usable administration
- structured access governance
- coherent integration with the rest of the infrastructure

## Conclusion
This document records the installation and configuration logic of the AD / IAM component.

Once completed with actual commands, values, validation outputs, and screenshots, it will serve as a reproducible and defensible proof that the infrastructure includes a functional centralized identity and access management service.