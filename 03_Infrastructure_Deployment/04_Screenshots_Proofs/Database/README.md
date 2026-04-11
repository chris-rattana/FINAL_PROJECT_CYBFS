# Database Screenshots and Proofs Index

## Purpose
This document indexes the screenshots, command outputs, and technical proofs collected for the Database component of the project infrastructure.

Its purpose is to:
- identify which proofs were collected
- explain what each proof demonstrates
- support deployment validation
- support Blue Team and Red Team review
- support final documentation and presentation

This folder should contain evidence showing that the database service is installed, configured, reachable only through intended paths, integrated with the web layer, and protected according to the project security model.

## Evidence Collection Rules
The evidence stored in this folder should be:
- clearly named
- easy to understand without extra context
- linked to a validation objective
- reusable in deployment documentation and final presentation

Recommended naming style:
- `DB01_service_status.png`
- `DB02_hostname_ip.png`
- `DB03_database_created.png`
- `DB04_app_user_created.png`
- `DB05_db_config.png`
- `DB06_internal_connectivity.png`
- `DB07_app_to_db_success.png`
- `DB08_unauthorized_access_denied.png`
- `DB09_firewall_status.png`
- `DB10_backup_scope_db.png`

## Expected Proof Categories

## 1. Service Availability Proof
This category proves that the database service is installed and running correctly.

### Examples
- service status screenshot
- command output showing PostgreSQL is active
- readiness check output

### Suggested Files
- `DB01_service_status.png`
- `DB01_service_status.txt`

## 2. Host and Database Context Proof
This category proves the database is deployed on the intended host with the expected role.

### Examples
- hostname output
- IP address output
- server identification screenshot

### Suggested Files
- `DB02_hostname_ip.png`

## 3. Database Creation Proof
This category proves that the required database exists.

### Examples
- command output listing the created database
- screenshot of database creation result
- management output confirming the database exists

### Suggested Files
- `DB03_database_created.png`
- `DB03_database_created.txt`

## 4. Service Account / Application User Proof
This category proves that the application-side database account exists.

### Examples
- command output showing the service account
- screenshot of role or user creation
- proof of intended privilege logic

### Suggested Files
- `DB04_app_user_created.png`
- `DB04_app_user_created.txt`

## 5. Configuration Proof
This category proves that the expected database configuration exists.

### Examples
- excerpt of relevant PostgreSQL configuration files
- listening configuration proof
- host-based access configuration proof
- configuration showing restricted connectivity

### Suggested Files
- `DB05_db_config.png`
- `DB05_db_config.txt`

## 6. Internal Connectivity Proof
This category proves that intended internal connectivity works.

### Examples
- successful local or internal connection test
- database readiness test
- proof that the intended internal host can reach the service

### Suggested Files
- `DB06_internal_connectivity.png`
- `DB06_internal_connectivity.txt`

## 7. Application-to-Database Integration Proof
This category proves that the web or application layer can interact with the database correctly.

### Examples
- screenshot of successful application behavior relying on the database
- command or log output showing successful backend connection
- proof of data read/write through the intended path

### Suggested Files
- `DB07_app_to_db_success.png`
- `DB07_app_to_db_success.txt`

## 8. Exposure Restriction Proof
This category proves that the database is not broadly exposed.

### Examples
- failed connection from a non-approved path
- scan result showing the database port is not broadly reachable
- comparison between intended and actual exposure

### Suggested Files
- `DB08_unauthorized_access_denied.png`
- `DB08_unauthorized_access_denied.txt`

## 9. Firewall / Security Proof
This category proves that the database host is protected and that access is filtered.

### Examples
- firewall status screenshot
- active firewall rules
- rule allowing only intended access paths

### Suggested Files
- `DB09_firewall_status.png`
- `DB09_firewall_status.txt`

## 10. Backup Inclusion Proof
This category proves that the database is included in the backup and recovery logic.

### Examples
- backup file or export proof
- snapshot evidence
- backup command output
- note showing restore-oriented validation for database data

### Suggested Files
- `DB10_backup_scope_db.png`
- `DB10_backup_scope_db.txt`

## Validation Mapping

| Proof ID | What It Demonstrates | Related Validation Area |
|----------|----------------------|-------------------------|
| DB01 | database service is running | service availability |
| DB02 | correct host context | deployment context |
| DB03 | required database exists | configuration validation |
| DB04 | application/service account exists | access control validation |
| DB05 | expected configuration exists | configuration validation |
| DB06 | intended internal connectivity works | backend validation |
| DB07 | web/application integration works | integration validation |
| DB08 | unauthorized path is denied or unavailable | exposure validation |
| DB09 | firewall is active or access is filtered | security control validation |
| DB10 | database is included in backup logic | resilience validation |

## Evidence Register Template

| File Name | Type | Description | Validation Use | Notes |
|-----------|------|-------------|----------------|-------|
| DB01_service_status.png | Screenshot | Shows the database service is active | service validation | To complete |
| DB02_hostname_ip.png | Screenshot | Shows the host identity and addressing | deployment context | To complete |
| DB03_database_created.png | Screenshot | Shows the project database exists | configuration validation | To complete |
| DB04_app_user_created.png | Screenshot | Shows the application user/role exists | access validation | To complete |
| DB05_db_config.png | Screenshot | Shows relevant DB configuration | configuration validation | To complete |
| DB06_internal_connectivity.png | Screenshot | Shows intended internal DB connectivity | backend validation | To complete |
| DB07_app_to_db_success.png | Screenshot | Shows successful app-to-DB behavior | integration validation | To complete |
| DB08_unauthorized_access_denied.png | Screenshot | Shows denied or unavailable unauthorized access | exposure validation | To complete |
| DB09_firewall_status.png | Screenshot | Shows firewall status or rules | security controls | To complete |
| DB10_backup_scope_db.png | Screenshot | Shows DB backup evidence | resilience validation | To complete |

## Quality Rules for Screenshots and Proofs
Each proof should:
- show the relevant part clearly
- avoid unnecessary personal or sensitive data
- be readable without excessive zoom
- have a meaningful file name
- correspond to an actual validation point
- be referenced in deployment or test documentation where needed

## Notes on Sensitive Information
Before storing screenshots or outputs:
- avoid exposing real passwords
- avoid exposing secrets or tokens
- avoid storing full credential details
- mask confidential values if needed
- keep only the technical evidence necessary for validation

## Minimum Expected Evidence Set
At minimum, this folder should contain proof of:
- service running
- host or database context
- created database
- created application/service account
- active configuration
- successful internal or application connectivity
- one proof of restricted exposure
- one firewall-related proof
- one database-backup-related proof

## Conclusion
This folder is intended to provide clear, structured, and reusable proof that the Database component is correctly deployed and operational.

Once populated, it will support technical validation, security review, and final presentation by showing that the database layer is not only documented, but actually implemented, integrated, protected, and included in the resilience logic of the project.