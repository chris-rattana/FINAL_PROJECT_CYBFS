# AD / IAM Screenshots and Proofs Index

## Purpose
This document indexes the screenshots, command outputs, and technical proofs collected for the AD / IAM component of the project infrastructure.

Its purpose is to:
- identify which proofs were collected
- explain what each proof demonstrates
- support deployment validation
- support Blue Team and Red Team review
- support final documentation and presentation

This folder should contain evidence showing that the centralized identity and access management component is installed, configured, operational, and aligned with the security model of the project.

## Evidence Collection Rules
The evidence stored in this folder should be:
- clearly named
- easy to understand without extra context
- linked to a validation objective
- reusable in the deployment documentation and final presentation

Recommended naming style:
- `AD01_service_status.png`
- `AD02_domain_info.png`
- `AD03_test_user_created.png`
- `AD04_test_group_created.png`
- `AD05_group_membership.png`
- `AD06_access_success.png`
- `AD07_access_denied.png`
- `AD08_firewall_status.png`

## Expected Proof Categories

## 1. Service Availability Proof
This category proves that the AD / IAM service is installed and running correctly.

### Examples
- service status screenshot
- command output showing the directory service is active
- host status proof related to the AD / IAM role

### Suggested Files
- `AD01_service_status.png`
- `AD01_service_status.txt`

## 2. Host and Identity Service Context Proof
This category proves the identity service is deployed on the intended host with the expected role.

### Examples
- hostname output
- IP address output
- domain or realm information
- basic server identification screenshot

### Suggested Files
- `AD02_hostname_ip.png`
- `AD03_domain_realm_info.png`

## 3. User Creation Proof
This category proves that user administration works.

### Examples
- screenshot of a created test user
- command output confirming user existence
- directory administration proof showing user creation success

### Suggested Files
- `AD04_test_user_created.png`
- `AD04_test_user_created.txt`

## 4. Group Creation Proof
This category proves that group-based administration works.

### Examples
- screenshot of a created test group
- command output confirming group existence
- directory administration proof showing group creation success

### Suggested Files
- `AD05_test_group_created.png`
- `AD05_test_group_created.txt`

## 5. Group Membership Proof
This category proves that group-based access logic is usable.

### Examples
- screenshot of user membership in a test group
- command output showing group membership
- proof of role-based assignment logic

### Suggested Files
- `AD06_group_membership.png`
- `AD06_group_membership.txt`

## 6. Access Control Proof
This category proves that identity and group logic have an actual effect on access to a protected resource.

### Examples
- screenshot showing successful access by an authorized user
- screenshot showing denied access by an unrelated user
- resource permission proof linked to group membership

### Suggested Files
- `AD07_access_success.png`
- `AD08_access_denied.png`

## 7. Firewall / Security Proof
This category proves that the AD / IAM host is not left unmanaged from a network security perspective.

### Examples
- firewall status screenshot
- command output showing active rules
- proof of restricted exposure where relevant

### Suggested Files
- `AD09_firewall_status.png`
- `AD09_firewall_status.txt`

## 8. Administrative Access Proof
This category proves that the component can be administered through the intended path.

### Examples
- screenshot of administration session
- command output from an administrative action
- proof of successful management operation

### Suggested Files
- `AD10_admin_action.png`
- `AD10_admin_action.txt`

## Validation Mapping

| Proof ID | What It Demonstrates | Related Validation Area |
|----------|----------------------|-------------------------|
| AD01 | identity service is running | service availability |
| AD02 | correct host context | deployment context |
| AD03 | domain / realm information | configuration proof |
| AD04 | test user creation works | user management |
| AD05 | test group creation works | group management |
| AD06 | user-group assignment works | access governance |
| AD07 | authorized access works | access control validation |
| AD08 | unauthorized access is denied | access control validation |
| AD09 | firewall is active or exposure is controlled | security control validation |
| AD10 | administrative management is functional | admin validation |

## Evidence Register Template

| File Name | Type | Description | Validation Use | Notes |
|-----------|------|-------------|----------------|-------|
| AD01_service_status.png | Screenshot | Shows the AD / IAM service is active | service validation | To complete |
| AD02_hostname_ip.png | Screenshot | Shows the host identity and addressing | deployment context | To complete |
| AD03_domain_realm_info.png | Screenshot | Shows domain or realm information | configuration validation | To complete |
| AD04_test_user_created.png | Screenshot | Shows successful user creation | IAM validation | To complete |
| AD05_test_group_created.png | Screenshot | Shows successful group creation | IAM validation | To complete |
| AD06_group_membership.png | Screenshot | Shows user assignment to group | access governance | To complete |
| AD07_access_success.png | Screenshot | Shows authorized access to protected resource | access control | To complete |
| AD08_access_denied.png | Screenshot | Shows denied access for unrelated user | access control | To complete |
| AD09_firewall_status.png | Screenshot | Shows firewall status or rule set | security controls | To complete |
| AD10_admin_action.png | Screenshot | Shows an administrative operation | admin validation | To complete |

## Quality Rules for Screenshots and Proofs
Each proof should:
- show the relevant part clearly
- avoid unnecessary personal or sensitive data
- be readable without zooming excessively
- have a meaningful file name
- correspond to an actual validation point
- be referenced in deployment or test documentation where needed

## Notes on Sensitive Information
Before storing screenshots or outputs:
- avoid exposing real passwords
- avoid exposing sensitive secrets
- avoid storing unnecessary credential details
- mask confidential values if needed
- keep only the technical evidence necessary for validation

## Minimum Expected Evidence Set
At minimum, this folder should contain proof of:
- service running
- domain or identity configuration
- test user creation
- test group creation
- group membership
- one successful authorized access
- one denied unauthorized access
- one security-related proof such as firewall status

## Conclusion
This folder is intended to provide clear, structured, and reusable proof that the AD / IAM component is correctly deployed and operational.

Once populated, it will support technical validation, security review, and final presentation by showing that centralized identity and access management is not only documented, but actually implemented and tested.