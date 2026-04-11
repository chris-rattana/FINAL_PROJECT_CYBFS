# Network Security Installation and Configuration

## Purpose
This document records the installation and configuration logic of the network security component deployed in the project infrastructure.

Its purpose is to provide a clear and reproducible view of:
- the deployment objective
- the installation steps
- the configuration choices
- the security decisions
- the validation points
- the evidence expected

This document is part of the infrastructure deployment proof and complements the component description already provided in the deployment section.

## Selected Technologies
- UFW for host-based firewalling
- OpenVPN for controlled remote access
- exposure limitation and trust-boundary logic at architecture level

## Deployment Objective
The objective of this deployment is to provide:
- controlled remote access to internal resources
- reduced attack surface on exposed hosts
- restricted access to backend services
- protected administrative paths
- baseline intrusion prevention through filtering and access control
- documented and testable network security rules

This component is required in order to make the infrastructure not only reachable, but also properly protected and defensible.

## Deployment Scope
The network security installation covers:
- identification of exposed and internal services
- host-based firewall configuration
- definition of allowed and denied traffic paths
- VPN-based remote access setup where applicable
- protection of backend services
- restriction of administrative access
- validation of reachable and non-reachable ports
- collection of deployment evidence

## Component Role
This component supports the transversal protection layer of the infrastructure.

Its main responsibilities are:
- filter inbound traffic
- reduce unnecessary exposure
- protect internal-only services
- control remote access
- separate user-facing services from backend resources
- support monitoring, testing, Blue Team review, and Red Team assessment

## Prerequisites
Before installation, confirm the following:
- critical hosts are deployed and reachable
- expected service ports are known
- internal and external communication paths are identified
- remote access requirements are clear
- backend services that must remain protected are identified
- administrative access requirements are known
- hostnames and IP addresses are documented

## Installation Logic
The installation is performed in a structured order to reduce configuration mistakes and preserve service availability.

### Step 1 — Identify Required Flows
List the traffic that must be allowed for the project to function.

Document:
- web service ports
- VPN ports
- database access paths
- monitoring paths
- administrative service paths
- any file-sharing related access paths

### Step 2 — Define Trust Boundaries
Classify the main communication paths according to the architecture.

Document:
- user access zone
- exposed service zone
- internal data zone
- administration and visibility zone

### Step 3 — Configure Host Firewalls
Apply firewall rules on critical hosts using UFW.

Document:
- default policy
- allowed inbound rules
- denied or blocked paths
- per-host rule differences where relevant

### Step 4 — Configure Remote Access Logic
Prepare the remote access path for authorized users and administrators.

Document:
- VPN service assumptions
- remote access port used
- which services are accessible after connection
- what remains inaccessible directly from outside

### Step 5 — Protect Backend Services
Restrict direct access to backend services such as:
- database
- identity services
- sensitive administration paths

Document:
- source restrictions
- internal-only assumptions
- ports intentionally not exposed

### Step 6 — Restrict Administrative Paths
Limit administrative access to the smallest justified scope.

Document:
- administrative ports
- approved source paths
- relation with VPN or internal access
- separation between normal usage and admin access

### Step 7 — Validate Reachability and Denial Logic
Test that intended traffic is allowed and unintended traffic is denied.

Document:
- allowed service access tests
- denied access tests
- port visibility checks
- firewall status outputs

## Suggested Configuration Notes
The following elements should be recorded clearly after deployment.

### Firewall Default Policy
Record the default inbound and outbound policy used on each relevant host.

### Allowed Ports
Record each allowed port and why it is needed.

### Denied or Non-Exposed Ports
Record key services or paths intentionally not exposed.

### VPN Notes
Record:
- service used
- listening port
- expected client access logic
- internal services accessible through VPN

### Administrative Access Notes
Record how SSH or other administration paths are restricted.

### Backend Protection Notes
Record how the database and other internal services are protected from broad reachability.

## Security Configuration Notes
The network security component must be deployed with baseline security considerations.

Record the following:

### Minimal Exposure
Document that only required ports are open.

### Default Deny Logic
Document the deny-by-default approach where used.

### Backend Isolation
Document how internal services remain protected.

### Controlled Remote Access
Document how remote users reach internal resources through the approved path only.

### Administrative Restriction
Document how admin access remains limited.

### Evidence of Denied Paths
Document at least one example showing that an unintended path is blocked.

## Example Sections to Complete During Deployment

### Critical Hosts Protected
- To complete

### Firewall Default Policies
- To complete

### Allowed Ports by Host
- To complete

### Denied / Hidden Service Paths
- To complete

### VPN Port and Access Logic
- To complete

### Administrative Access Restrictions
- To complete

### Main Commands Used
- To complete

### Validation Notes
- To complete

## Validation Checklist
Use this checklist after deployment:

- [ ] required flows identified
- [ ] trust boundaries documented
- [ ] firewall rules applied on critical hosts
- [ ] only intended ports are reachable
- [ ] backend services are protected
- [ ] remote access path is controlled
- [ ] administrative access is restricted
- [ ] denied access tests performed
- [ ] evidence captured

## Evidence to Collect
Store the following proof in the corresponding screenshots/evidence folder:
- firewall status outputs
- screenshots or command outputs showing active rules
- proof of allowed access to the web service
- proof of denied direct access to the database
- proof of VPN-based or controlled remote access
- proof of restricted administrative access
- notes or screenshots showing blocked unauthorized paths

## Common Issues to Watch
During installation, pay attention to:
- allowing too many ports by convenience
- forgetting backend exposure checks
- leaving admin services broadly reachable
- firewall rules applied on one host but not another
- VPN configured but not aligned with allowed resource paths
- blocking intended traffic accidentally
- failing to document why a port is open

## Known Limits
This installation remains project-scale and does not aim to reproduce a full enterprise network security stack with advanced IDS/IPS orchestration, complex segmentation fabrics, or large-scale centralized firewall management.

The objective is to demonstrate:
- clear exposure control
- practical firewalling
- realistic remote access protection
- backend service protection
- understandable trust-boundary logic
- clear technical documentation

## Conclusion
This document records the installation and configuration logic of the network security component.

Once completed with actual commands, values, validation outputs, and screenshots, it will serve as a reproducible and defensible proof that the infrastructure includes controlled service exposure, protected internal paths, and realistic baseline network security.