# Web Server Installation and Configuration

## Purpose
This document records the installation and configuration logic of the web server component deployed in the project infrastructure.

Its purpose is to provide a clear and reproducible view of:
- the deployment objective
- the installation steps
- the configuration choices
- the security decisions
- the validation points
- the evidence expected

This document is part of the infrastructure deployment proof and complements the component description already provided in the deployment section.

## Selected Technology
Nginx

## Deployment Objective
The objective of this deployment is to provide the main user-facing web service of the infrastructure.

This component is required in order to:
- expose the application or service to authorized users
- provide a controlled entry point to the business service
- separate the user-facing layer from backend components
- support secure communication with the database layer
- contribute to the operational and demonstrable value of the final project

## Deployment Scope
The web server installation covers:
- package installation
- service activation
- basic site or application configuration
- controlled port exposure
- reverse proxy or frontend logic where relevant
- basic hardening and logging
- validation of service availability
- collection of deployment evidence

## Host Role
This host is dedicated to the web service layer of the infrastructure.

Its main responsibilities are:
- run the web server
- expose the application through the intended access path
- forward or serve requests according to the chosen architecture
- interact with backend services in a controlled way
- provide logs and service-level visibility

## Prerequisites
Before installation, confirm the following:
- the host is installed and reachable
- network configuration is stable
- hostname is correctly defined
- package sources are available
- administrative access is available
- firewall logic is planned
- backend dependency assumptions are known
- the application or site deployment path is identified

## Installation Logic
The installation is performed in a structured order to reduce configuration errors and unnecessary exposure.

### Step 1 — Prepare the Host
Prepare the system before installing the web service:
- update packages
- confirm hostname
- confirm IP addressing assumptions
- verify network reachability
- confirm the host is ready for service deployment

### Step 2 — Install Nginx
Install the required web server package.

Document:
- package name
- installation command used
- version notes if relevant

### Step 3 — Enable and Start the Service
Ensure that Nginx starts correctly and is enabled after installation.

Document:
- service name
- enable/start commands
- startup verification logic

### Step 4 — Configure the Web Service
Create the service configuration needed for the project.

Document:
- listening port
- server name or hostname if used
- document root or application path
- reverse proxy logic if applicable
- default site handling
- configuration file location

### Step 5 — Configure Backend Connectivity
If the web layer forwards traffic to an application backend or relies on a database-supported application, document the intended integration path.

Document:
- which backend service is used
- which internal port or service path is used
- how direct backend exposure is avoided

### Step 6 — Apply Logging and Basic Hardening
Enable useful logging and keep the service minimal.

Document:
- access log configuration
- error log configuration
- unnecessary defaults disabled or removed
- service exposure reduced to required paths only

### Step 7 — Apply Firewall Rules
Restrict exposure to only the intended service ports.

Document:
- allowed ports
- blocked or denied paths where relevant
- justification for each exposed service port

### Step 8 — Validate Service Availability
Confirm that the web service is operational and reachable through the intended path.

Document:
- service status
- listening port
- browser or curl-based validation
- application response proof

## Suggested Configuration Notes
The following elements should be recorded clearly after deployment.

### Hostname
Record the hostname used for the web server.

### IP Address
Record the server IP address used in the lab environment.

### Listening Port
Record the service port used by Nginx.

### Site or Application Path
Record the deployed site path, document root, or application path.

### Configuration File
Record the active Nginx configuration file used for the project.

### Backend Integration Notes
Record whether the web service is:
- static only
- frontend only
- reverse proxy to another service
- connected indirectly to the database through an application layer

## Security Configuration Notes
The web server must be deployed with baseline security considerations.

Record the following:

### Restricted Exposure
Document which service ports are open and why.

### Firewall Logic
Document the firewall rules applied to the host.

### Minimal Service Scope
Document what has been intentionally removed, disabled, or left unexposed.

### Logging
Document where access and error logs are stored.

### Backend Separation
Document how the backend path is protected from unnecessary direct exposure.

## Example Sections to Complete During Deployment

### Installed Packages
- To complete

### Hostname
- To complete

### IP Address
- To complete

### Listening Port
- To complete

### Site Root or Application Path
- To complete

### Configuration File Path
- To complete

### Main Commands Used
- To complete

### Service Status Notes
- To complete

### Backend Connectivity Notes
- To complete

### Firewall Rules Notes
- To complete

## Validation Checklist
Use this checklist after deployment:

- [ ] host prepared correctly
- [ ] Nginx installed successfully
- [ ] service enabled and started
- [ ] configuration file created or updated
- [ ] intended listening port confirmed
- [ ] browser or curl validation successful
- [ ] backend integration documented
- [ ] firewall logic applied
- [ ] logs confirmed
- [ ] evidence captured

## Evidence to Collect
Store the following proof in the corresponding screenshots/evidence folder:
- screenshot of service status
- screenshot of the running web page or endpoint
- command output showing listening ports
- configuration excerpt
- firewall status output
- access or error log excerpt where relevant
- screenshot or output proving expected service behavior

## Common Issues to Watch
During installation, pay attention to:
- incorrect port binding
- default site conflicts
- wrong document root or application path
- reverse proxy misconfiguration
- firewall blocking the intended service
- unintended port exposure
- service startup failure due to syntax errors
- backend path not working as expected

## Known Limits
This installation remains project-scale and does not aim to reproduce a full enterprise web hosting platform with advanced load balancing, autoscaling, CDN integration, or complex multi-instance failover.

The objective is to demonstrate:
- a working web service
- controlled exposure
- coherent backend integration
- baseline logging and hardening
- clear technical documentation

## Conclusion
This document records the installation and configuration logic of the web server component.

Once completed with actual commands, values, validation outputs, and screenshots, it will serve as a reproducible and defensible proof that the infrastructure includes a functional and controlled web service layer.