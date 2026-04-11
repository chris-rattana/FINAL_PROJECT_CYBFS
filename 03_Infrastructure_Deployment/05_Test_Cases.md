# Test Cases

## Purpose
This document defines the main deployment validation tests for the project infrastructure.

The objective of these tests is to demonstrate that the environment is:
- functional
- integrated
- secure
- coherent with the selected architecture
- supported by usable evidence for final review and presentation

These tests are intentionally practical and focused on the core services required by the project.

## Test Strategy
The validation approach is based on:
- service availability testing
- integration testing
- access control testing
- exposure and firewall testing
- backup and monitoring testing
- evidence collection

The goal is not to create a full enterprise QA framework, but to prove that the deployed infrastructure works correctly and that key security controls behave as expected.

## Test Execution Rules
For each test case, the following elements should be recorded:
- test ID
- test objective
- component concerned
- preconditions
- test steps
- expected result
- actual result
- status: Pass / Fail / Partial
- evidence reference
- notes or follow-up actions

## Environment Scope
The following components are covered by this validation plan:
- AD / IAM
- Web Server
- Database
- File Server
- Backup and Monitoring
- Network Security

## Test Case Format
Each test case below follows a simple structure:
- ID
- Objective
- Preconditions
- Steps
- Expected Result
- Evidence

---

## IAM TESTS

### TC-IAM-01 — Directory Service Running
**Objective**  
Verify that the centralized identity service is installed and operational.

**Preconditions**  
The AD / IAM component has been deployed.

**Steps**
1. Connect to the identity service host.
2. Check service status.
3. Confirm that the directory service starts correctly.

**Expected Result**  
The service is active and available for administration.

**Evidence**
- service status output
- screenshot of running service
- command output reference

---

### TC-IAM-02 — Create Test User
**Objective**  
Verify that a new user can be created in the centralized identity system.

**Preconditions**  
Administrative access to the identity service is available.

**Steps**
1. Open the administration interface or use administrative commands.
2. Create a test user.
3. Save and verify the user exists.

**Expected Result**  
The test user is successfully created and visible in the directory.

**Evidence**
- screenshot of created user
- command output or administration proof

---

### TC-IAM-03 — Create Test Group and Assign User
**Objective**  
Verify that group-based access logic can be used.

**Preconditions**  
At least one test user exists.

**Steps**
1. Create a test group.
2. Assign the test user to the group.
3. Verify that membership is correctly applied.

**Expected Result**  
The group exists and the user is correctly assigned.

**Evidence**
- screenshot of group membership
- command output reference

---

### TC-IAM-04 — Permission-Based Access Check
**Objective**  
Verify that group membership affects access to a protected resource.

**Preconditions**  
A protected file-sharing resource or service exists.

**Steps**
1. Log in as the authorized test user.
2. Access the protected resource.
3. Log in as a non-authorized user.
4. Repeat the access attempt.

**Expected Result**  
The authorized user obtains access. The unrelated user is denied.

**Evidence**
- screenshots of successful and denied access
- access logs if available

---

## WEB SERVER TESTS

### TC-WEB-01 — Web Service Running
**Objective**  
Verify that the web service is installed and running.

**Preconditions**  
The web server has been deployed.

**Steps**
1. Connect to the web host.
2. Check service status.
3. Confirm that the service is listening on the expected port.

**Expected Result**  
The web service is active and listening on the intended port.

**Evidence**
- service status output
- listening port output
- screenshot or command result

---

### TC-WEB-02 — Web Application Reachable
**Objective**  
Verify that the web service is reachable through the expected access path.

**Preconditions**  
The web service is running and network access is configured.

**Steps**
1. Open the application URL or IP/port from an authorized client.
2. Confirm the page or endpoint loads successfully.

**Expected Result**  
The application or web page is reachable and returns the expected content.

**Evidence**
- browser screenshot
- curl output if relevant

---

### TC-WEB-03 — Unintended Ports Not Exposed
**Objective**  
Verify that only expected web-related ports are exposed.

**Preconditions**  
Firewall rules and service configuration are active.

**Steps**
1. Check open ports on the host.
2. Compare exposed ports with expected service design.

**Expected Result**  
Only intended service ports are reachable.

**Evidence**
- port scan result
- firewall status output
- notes on allowed ports

---

## DATABASE TESTS

### TC-DB-01 — Database Service Running
**Objective**  
Verify that the database service is installed and active.

**Preconditions**  
The database has been deployed.

**Steps**
1. Connect to the database host.
2. Check service status.
3. Confirm readiness.

**Expected Result**  
The database service is active and operational.

**Evidence**
- service status output
- database readiness output

---

### TC-DB-02 — Application-to-Database Connectivity
**Objective**  
Verify that the web application can communicate with the database.

**Preconditions**  
The web server and database are running.

**Steps**
1. Trigger an application action requiring database access.
2. Confirm successful response.
3. Review application or database logs if needed.

**Expected Result**  
The application communicates successfully with the database.

**Evidence**
- application screenshot or output
- logs showing successful backend connectivity

---

### TC-DB-03 — Database Not Broadly Exposed
**Objective**  
Verify that the database is not unnecessarily reachable from unauthorized paths.

**Preconditions**  
Firewall rules and network restrictions are active.

**Steps**
1. Attempt to reach the database port from an unauthorized or non-approved path.
2. Observe the result.

**Expected Result**  
Unauthorized access to the database is denied or unreachable.

**Evidence**
- failed connection attempt
- firewall output
- scan result

---

## FILE SERVER TESTS

### TC-FS-01 — File Service Running
**Objective**  
Verify that the file-sharing service is active.

**Preconditions**  
The file-sharing platform has been deployed.

**Steps**
1. Check service state.
2. Confirm that the platform is reachable.

**Expected Result**  
The file-sharing platform is installed, running, and accessible.

**Evidence**
- service status output
- platform screenshot

---

### TC-FS-02 — Authorized User File Access
**Objective**  
Verify that an authorized user can access shared files.

**Preconditions**  
At least one authorized user exists.

**Steps**
1. Log in as the authorized user.
2. Access a shared file or folder.
3. Perform a permitted action such as open, upload, or download.

**Expected Result**  
The authorized user can access and use the shared resource as intended.

**Evidence**
- login screenshot
- shared folder screenshot
- upload/download proof

---

### TC-FS-03 — Unauthorized User Restricted
**Objective**  
Verify that a non-authorized user cannot access the same protected shared resource.

**Preconditions**  
At least one unrelated user exists.

**Steps**
1. Log in as the unrelated user.
2. Attempt access to the protected shared resource.

**Expected Result**  
Access is denied or not granted.

**Evidence**
- denied access screenshot
- audit or access log if available

---

## BACKUP AND MONITORING TESTS

### TC-BM-01 — Monitoring Visibility Available
**Objective**  
Verify that critical services or hosts are visible through the monitoring solution.

**Preconditions**  
Monitoring has been deployed.

**Steps**
1. Open the monitoring interface or monitoring outputs.
2. Check visibility of critical hosts or services.

**Expected Result**  
Critical components appear in monitoring and are identifiable.

**Evidence**
- monitoring dashboard screenshot
- host/service visibility capture

---

### TC-BM-02 — Service State Observable
**Objective**  
Verify that service status or relevant operational information can be observed.

**Preconditions**  
Monitoring or log collection is active.

**Steps**
1. Review one or more critical services in the monitoring layer.
2. Confirm that useful status information is visible.

**Expected Result**  
The monitoring setup provides usable operational visibility.

**Evidence**
- dashboard screenshot
- service state screenshot
- event screenshot if available

---

### TC-BM-03 — Backup Artifact Exists
**Objective**  
Verify that a backup file, snapshot, export, or equivalent artifact exists.

**Preconditions**  
Backup logic has been configured.

**Steps**
1. Check the backup location or backup workflow output.
2. Confirm that a valid backup artifact is present.

**Expected Result**  
Backup evidence exists and is identifiable.

**Evidence**
- screenshot of backup artifact
- command output showing backup file or snapshot

---

### TC-BM-04 — Restore-Oriented Validation
**Objective**  
Verify that at least one restore-oriented scenario is documented or tested.

**Preconditions**  
A backup artifact exists.

**Steps**
1. Review the restore workflow or perform a limited restore test.
2. Confirm that the restore path is understood and documented.

**Expected Result**  
A recovery path exists and is documented or partially validated.

**Evidence**
- restore notes
- screenshot or output of restore-oriented validation

---

## NETWORK SECURITY TESTS

### TC-NET-01 — Firewall Active on Critical Hosts
**Objective**  
Verify that firewalling is active on relevant hosts.

**Preconditions**  
Firewall configuration has been applied.

**Steps**
1. Check firewall status on each critical host.
2. Review active rules.

**Expected Result**  
Firewall protection is active and consistent with the intended design.

**Evidence**
- firewall status output
- screenshot of active rules

---

### TC-NET-02 — Only Intended Ports Reachable
**Objective**  
Verify that service exposure is limited to required ports.

**Preconditions**  
Service and firewall configuration are finalized.

**Steps**
1. Scan or check accessible ports from the relevant path.
2. Compare results with expected architecture.

**Expected Result**  
Only intended ports are reachable.

**Evidence**
- port scan result
- architecture comparison notes

---

### TC-NET-03 — Controlled Remote Access Path
**Objective**  
Verify that internal access follows the intended controlled remote access path.

**Preconditions**  
VPN or controlled remote access method is configured.

**Steps**
1. Attempt access to an internal resource using the approved method.
2. Attempt unauthorized direct access where relevant.

**Expected Result**  
The approved path works. Unapproved direct access is denied or unavailable.

**Evidence**
- VPN connection proof
- successful internal access proof
- failed unauthorized path proof

---

### TC-NET-04 — Administrative Access Restricted
**Objective**  
Verify that administrative services are not broadly exposed.

**Preconditions**  
Administrative access paths are configured.

**Steps**
1. Check access to admin services from approved paths.
2. Attempt access from non-approved paths.

**Expected Result**  
Administrative access is available only through intended and restricted paths.

**Evidence**
- access attempt proof
- firewall rule output
- notes on admin restriction

---

## CROSS-COMPONENT INTEGRATION TESTS

### TC-INT-01 — End-to-End User Access Flow
**Objective**  
Verify the overall user flow through identity, service access, and business usage.

**Preconditions**  
IAM, web service, and required backend components are operational.

**Steps**
1. Authenticate as an authorized user.
2. Access the web service.
3. Trigger an action that depends on backend services.

**Expected Result**  
The full user flow works correctly end-to-end.

**Evidence**
- login proof
- application screenshot
- backend confirmation if applicable

---

### TC-INT-02 — File Collaboration Linked to Identity
**Objective**  
Verify that file-sharing access is consistent with the centralized identity model.

**Preconditions**  
IAM and file-sharing components are deployed.

**Steps**
1. Log in with a user linked to the correct access group.
2. Access the intended shared resource.
3. Repeat with another user lacking the required group membership.

**Expected Result**  
Access behavior matches the intended permission model.

**Evidence**
- user access screenshots
- group membership proof
- denied access proof

---

### TC-INT-03 — Monitoring Supports Operational Review
**Objective**  
Verify that the infrastructure provides enough visibility for operational and defensive review.

**Preconditions**  
Monitoring is active.

**Steps**
1. Review monitored components.
2. Identify whether critical services are visible.
3. Confirm that collected evidence can support Blue Team analysis.

**Expected Result**  
The monitoring layer supports operational understanding and defensive reasoning.

**Evidence**
- dashboard screenshot
- monitored services list
- event or status capture

---

## Test Result Summary Template

| Test ID | Component | Objective | Expected Result | Actual Result | Status | Evidence Ref | Notes |
|--------|-----------|-----------|----------------|---------------|--------|--------------|------|
| TC-IAM-01 | AD / IAM | Verify service availability | IAM service active | To complete | To complete | To complete | To complete |
| TC-WEB-01 | Web Server | Verify web service status | Service active | To complete | To complete | To complete | To complete |
| TC-DB-01 | Database | Verify DB service status | Service active | To complete | To complete | To complete | To complete |
| TC-FS-01 | File Server | Verify file-sharing service | Service active | To complete | To complete | To complete | To complete |
| TC-BM-01 | Backup / Monitoring | Verify monitoring visibility | Critical services visible | To complete | To complete | To complete | To complete |
| TC-NET-01 | Network Security | Verify firewall status | Firewall active | To complete | To complete | To complete | To complete |

## Acceptance Logic
The deployment validation will be considered satisfactory if:
- all critical services are tested
- major integration paths are validated
- access control behavior is confirmed
- service exposure is documented and limited
- backup and monitoring evidence exists
- the results are recorded clearly enough to support review, Blue Team analysis, and final presentation

## Conclusion
These test cases provide a practical validation framework for the deployed infrastructure.

They are designed to prove that the project is not only documented, but actually functional, integrated, and aligned with the security and resilience expectations of the final CYBFS project.