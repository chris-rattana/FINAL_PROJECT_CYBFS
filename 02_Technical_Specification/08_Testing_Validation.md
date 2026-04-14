# Testing and Validation — CoreShield Infrastructure

## 1. Validation Objective

This document summarizes the testing and validation activities performed for the **CYBFS — CoreShield Infrastructure** project.

The goal of this phase was to confirm that the deployed environment was not only built successfully, but also **functionally operational, internally coherent, reachable, monitored, and supported by real technical evidence**.

The validation process focused on practical checks rather than theoretical assumptions. Each critical role of the infrastructure was verified through commands, service checks, browser access, port inspection, or monitoring visibility.

---

## 2. Validation Scope

The testing phase covered the following areas:

- virtual machine deployment consistency
- host identity and addressing validation
- service availability on each node
- DNS and internal resolution checks
- local web and application checks
- collaborative service validation
- Wazuh deployment and centralized monitoring validation
- port listening and inter-node communication checks
- evidence capture and appendix organization

The final objective was to ensure that the platform could be presented as a **deployed, tested, monitored, and documented cyber-oriented infrastructure**.

---

## 3. Final Validation Status

The final validation status of the infrastructure is:

**Validated**

The following conditions were confirmed:

- all four VMs were deployed successfully
- internal addressing was configured and validated
- the identity and DNS node was operational
- the application node was operational
- the collaborative file-sharing node was operational
- the centralized monitoring node was operational
- Wazuh agents were active on all three main service nodes
- access tests succeeded for the main exposed services
- an evidence package was created and organized in `09_Appendices_Evidence`

---

## 4. Test Matrix

| Test ID | Component | Validation Target | Expected Result | Result |
|---|---|---|---|---|
| T01 | VMware | All four VMs visible and operational | VMs deployed and available in VMware | Passed |
| T02 | dc01 | Host identity and addressing | Hostname and IP configuration visible and coherent | Passed |
| T03 | dc01 | DNS service exposure | Internal DNS reachable on port 53 | Passed |
| T04 | dc01 | Internal name resolution | `app01`, `file01`, and `sec01` resolved internally | Passed |
| T05 | app01 | Host identity and addressing | Hostname and IP configuration visible and coherent | Passed |
| T06 | app01 | Web front-end service | Web service listening and active | Passed |
| T07 | app01 | Local application response | HTTP response returned locally | Passed |
| T08 | app01 | Wazuh agent | Agent installed, active, and connected | Passed |
| T09 | file01 | Host identity and addressing | Hostname and IP configuration visible and coherent | Passed |
| T10 | file01 | Web service stack | Apache2 / PHP-FPM / MariaDB active | Passed |
| T11 | file01 | Nextcloud service state | Nextcloud installed and validated | Passed |
| T12 | file01 | Wazuh agent | Agent installed, active, and connected | Passed |
| T13 | sec01 | Host identity and addressing | Hostname and IP configuration visible and coherent | Passed |
| T14 | sec01 | Wazuh manager | Service active | Passed |
| T15 | sec01 | Wazuh indexer | Service active | Passed |
| T16 | sec01 | Wazuh dashboard | Service active and reachable in browser | Passed |
| T17 | sec01 | Monitoring coverage | `dc01`, `app01`, and `file01` visible as active agents | Passed |
| T18 | app01 → sec01 | Agent communication on 1514 | Connection succeeds | Passed |
| T19 | app01 → sec01 | Enrollment communication on 1515 | Connection succeeds | Passed |
| T20 | file01 → sec01 | Agent communication on 1514 | Connection succeeds | Passed |
| T21 | file01 → sec01 | Enrollment communication on 1515 | Connection succeeds | Passed |
| T22 | User validation | Browser access to application | `app01` page accessible | Passed |
| T23 | User validation | Browser access to Nextcloud | `file01` login page accessible | Passed |
| T24 | User validation | Browser access to Wazuh | `sec01` dashboard accessible | Passed |

---

## 5. Node-by-Node Validation Summary

### 5.1 dc01 — Identity and DNS Node

The `dc01` node was validated through:
- hostname and addressing checks
- route verification
- Samba AD/DC service validation
- DNS listening verification on port 53
- successful internal name resolution

**Validation conclusion:**  
`dc01` is operational as the identity and internal naming backbone of the environment.

---

### 5.2 app01 — Application Node

The `app01` node was validated through:
- hostname and IP verification
- Nginx service validation
- local HTTP response check
- browser access validation
- Wazuh agent validation
- communication validation to the monitoring server

**Validation conclusion:**  
`app01` is operational as a monitored web application node.

---

### 5.3 file01 — Collaboration Node

The `file01` node was validated through:
- hostname and IP verification
- Apache2 service validation
- PHP-FPM validation
- MariaDB validation
- Nextcloud validation via `occ status`
- browser access validation
- Wazuh agent validation
- communication validation to the monitoring server

**Validation conclusion:**  
`file01` is operational as a monitored collaborative file-sharing node.

---

### 5.4 sec01 — Monitoring Node

The `sec01` node was validated through:
- hostname and IP verification
- Wazuh manager status
- Wazuh indexer status
- Wazuh dashboard status
- HTTPS local status check
- browser login and dashboard access
- agent visibility confirmation for the three monitored service nodes

**Validation conclusion:**  
`sec01` is operational as the centralized monitoring and detection node of the environment.

---

## 6. Monitoring Validation

Monitoring validation is a central part of the project because it demonstrates that the environment is not merely functional, but also observable.

The following points were confirmed:

- Wazuh all-in-one deployment completed successfully on `sec01`
- Wazuh dashboard accessible in browser
- Wazuh agents installed on `dc01`, `app01`, and `file01`
- all three agents visible as active in the dashboard
- overview and endpoint monitoring captures collected in the evidence package

**Validation conclusion:**  
The infrastructure is centrally monitored and provides a real detection and visibility layer.

---

## 7. Access Validation

The following access tests were completed successfully:

- application access on `app01`
- Nextcloud login page access on `file01`
- successful Nextcloud dashboard access validation
- Wazuh login page access on `sec01`
- Wazuh dashboard access after authentication

These checks confirm that the core business and security interfaces are accessible and usable.

---

## 8. Port and Communication Validation

The project includes technical verification of listening services and communication paths.

Validated checks include:

- DNS listening on `dc01` port 53
- web listening on `app01` port 80
- web listening on `file01` port 80
- Wazuh listening ports on `sec01`
- successful communication from `app01` to `sec01` on 1514 and 1515
- successful communication from `file01` to `sec01` on 1514 and 1515

**Validation conclusion:**  
Expected exposure and communication flows were confirmed.

---

## 9. Evidence Package Validation

All major validation steps were documented with screenshots and organized into the appendix structure:

- `02_Deployment_Screenshots`
- `03_Service_Status_Outputs`
- `04_Access_Control_Tests`
- `05_Firewall_Port_Proofs`
- `06_Monitoring_Backup_Proofs`

This evidence package supports the credibility of the project by linking validation claims to visible technical proof.

---

## 10. Limitations of the Validation Phase

The validation phase was designed for a compact final project scope and therefore has known limitations:

- no automated test suite
- no continuous integration validation pipeline
- no formal load testing
- no redundancy or failover testing
- no enterprise-scale hardening audit
- no advanced penetration scenario documented in this section

These limitations are acceptable within the educational and demonstrative scope of the project.

---

## 11. Overall Conclusion

The **CoreShield Infrastructure** reached a validated final state.

The testing phase confirmed that the environment is:

- deployed
- reachable
- operational
- internally coherent
- centrally monitored
- documented with real evidence

This makes the platform suitable for final presentation as a compact but credible cyber-oriented infrastructure project.