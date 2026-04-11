# Web Server Screenshots and Proofs Index

## Purpose
This document indexes the screenshots, command outputs, and technical proofs collected for the Web Server component of the project infrastructure.

Its purpose is to:
- identify which proofs were collected
- explain what each proof demonstrates
- support deployment validation
- support Blue Team and Red Team review
- support final documentation and presentation

This folder should contain evidence showing that the web service is installed, configured, reachable through the intended path, integrated with the backend where relevant, and protected according to the project security model.

## Evidence Collection Rules
The evidence stored in this folder should be:
- clearly named
- easy to understand without extra context
- linked to a validation objective
- reusable in deployment documentation and final presentation

Recommended naming style:
- `WEB01_service_status.png`
- `WEB02_hostname_ip.png`
- `WEB03_nginx_config.png`
- `WEB04_listening_ports.png`
- `WEB05_homepage_loaded.png`
- `WEB06_expected_endpoint_ok.png`
- `WEB07_backend_connectivity.png`
- `WEB08_unintended_port_closed.png`
- `WEB09_firewall_status.png`
- `WEB10_access_log_excerpt.png`

## Expected Proof Categories

## 1. Service Availability Proof
This category proves that the web server is installed and running correctly.

### Examples
- service status screenshot
- command output showing the web service is active
- host status proof related to the web role

### Suggested Files
- `WEB01_service_status.png`
- `WEB01_service_status.txt`

## 2. Host and Web Service Context Proof
This category proves the web service is deployed on the intended host with the expected role.

### Examples
- hostname output
- IP address output
- server identification screenshot
- note showing the service role

### Suggested Files
- `WEB02_hostname_ip.png`

## 3. Configuration Proof
This category proves that the expected web configuration exists.

### Examples
- screenshot or excerpt of the active Nginx configuration
- site configuration proof
- document root or application path proof
- reverse proxy configuration excerpt where relevant

### Suggested Files
- `WEB03_nginx_config.png`
- `WEB03_nginx_config.txt`

## 4. Listening Port Proof
This category proves that the service listens on the intended port only.

### Examples
- command output showing the listening port
- proof that HTTP/HTTPS or expected service port is open
- comparison with the intended architecture

### Suggested Files
- `WEB04_listening_ports.png`
- `WEB04_listening_ports.txt`

## 5. Reachability Proof
This category proves that authorized access to the web service works.

### Examples
- browser screenshot of the homepage
- screenshot of the main application page
- curl output showing successful response
- screenshot of expected endpoint behavior

### Suggested Files
- `WEB05_homepage_loaded.png`
- `WEB06_expected_endpoint_ok.png`
- `WEB06_expected_endpoint_ok.txt`

## 6. Backend Integration Proof
This category proves that the web service correctly interacts with the backend where relevant.

### Examples
- screenshot or output showing application-to-database behavior
- proof of successful backend-driven page rendering
- log excerpt proving backend communication

### Suggested Files
- `WEB07_backend_connectivity.png`
- `WEB07_backend_connectivity.txt`

## 7. Exposure Control Proof
This category proves that unintended ports or paths are not exposed.

### Examples
- scan result showing only expected ports
- failed connection to a non-approved port
- comparison between intended and actual exposure

### Suggested Files
- `WEB08_unintended_port_closed.png`
- `WEB08_unintended_port_closed.txt`

## 8. Firewall / Security Proof
This category proves that the web host is protected and exposure is controlled.

### Examples
- firewall status screenshot
- active firewall rule output
- proof of service-specific access allowance

### Suggested Files
- `WEB09_firewall_status.png`
- `WEB09_firewall_status.txt`

## 9. Logging Proof
This category proves that the web service provides useful operational or security visibility.

### Examples
- access log excerpt
- error log excerpt
- screenshot showing request entries
- proof that logs are enabled and usable

### Suggested Files
- `WEB10_access_log_excerpt.png`
- `WEB10_access_log_excerpt.txt`

## Validation Mapping

| Proof ID | What It Demonstrates | Related Validation Area |
|----------|----------------------|-------------------------|
| WEB01 | web service is running | service availability |
| WEB02 | correct host context | deployment context |
| WEB03 | expected configuration exists | configuration validation |
| WEB04 | intended listening port is active | exposure validation |
| WEB05 | homepage or main page is reachable | functional validation |
| WEB06 | expected endpoint behavior works | service validation |
| WEB07 | backend integration works | integration validation |
| WEB08 | unintended exposure is reduced | security validation |
| WEB09 | firewall is active or exposure is controlled | security control validation |
| WEB10 | logging is enabled and usable | monitoring and review support |

## Evidence Register Template

| File Name | Type | Description | Validation Use | Notes |
|-----------|------|-------------|----------------|-------|
| WEB01_service_status.png | Screenshot | Shows the web service is active | service validation | To complete |
| WEB02_hostname_ip.png | Screenshot | Shows the host identity and addressing | deployment context | To complete |
| WEB03_nginx_config.png | Screenshot | Shows the active web configuration | configuration validation | To complete |
| WEB04_listening_ports.png | Screenshot | Shows intended listening port(s) | exposure validation | To complete |
| WEB05_homepage_loaded.png | Screenshot | Shows the homepage or main page loads | functional validation | To complete |
| WEB06_expected_endpoint_ok.png | Screenshot | Shows expected endpoint response | service validation | To complete |
| WEB07_backend_connectivity.png | Screenshot | Shows backend-driven application behavior | integration validation | To complete |
| WEB08_unintended_port_closed.png | Screenshot | Shows unintended port/path not exposed | security validation | To complete |
| WEB09_firewall_status.png | Screenshot | Shows firewall status or rules | security controls | To complete |
| WEB10_access_log_excerpt.png | Screenshot | Shows useful web logs | operational/security visibility | To complete |

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
- host or service context
- active configuration
- intended listening port
- successful page or endpoint access
- backend integration where relevant
- one reduced-exposure proof
- one firewall-related proof
- one logging-related proof

## Conclusion
This folder is intended to provide clear, structured, and reusable proof that the Web Server component is correctly deployed and operational.

Once populated, it will support technical validation, security review, and final presentation by showing that the web layer is not only documented, but actually implemented, reachable, controlled, and tested.