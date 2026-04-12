# Oral Notes

## Presentation Title
Secure Infrastructure Design, Deployment, Defense and Assessment for a Remote-first Startup

## Presentation Goal
The goal of this presentation is to explain the final CYBFS project clearly and professionally by showing:
- the business context
- the architecture and technical choices
- the deployed core services
- the main security controls
- the Blue Team and Red Team perspectives
- the main remediation priorities
- the lessons learned

The presentation is designed for a short final review format and focuses on clarity, coherence, and relevance.

## Speaking Strategy
The presentation should:
- start with the strongest points first
- stay simple and structured
- avoid overly dense slides
- present one main idea per slide
- keep a clear link between business needs, infrastructure, security, and findings
- finish with a strong synthesis

## Suggested Slide Flow

### Slide 1 — Title
**Main message:**  
This project delivers a realistic and secure SME infrastructure for a remote-first startup.

**Oral notes:**  
Introduce the project in one sentence.  
State that the work combines infrastructure design, deployment, security controls, Blue Team review, Red Team review, and final documentation.

---

### Slide 2 — Business Context
**Main message:**  
The company profile is a remote-first startup that needs secure remote access, centralized administration, file sharing, application hosting, and resilience.

**Oral notes:**  
Explain why this scenario was selected.  
Highlight that this context naturally creates needs in identity management, web access, monitoring, backup, and network security.

---

### Slide 3 — Project Objectives
**Main message:**  
The objective was to build a functional, secure, integrated, and documented infrastructure at SME scale.

**Oral notes:**  
State the main goals:
- deploy core services
- secure the environment
- document everything clearly
- review the infrastructure from defensive and offensive perspectives

---

### Slide 4 — Global Architecture
**Main message:**  
The infrastructure is built around six main layers:
- AD / IAM
- Web Server
- Database
- File Server
- Backup / Monitoring
- Network Security

**Oral notes:**  
Explain the architecture at high level.  
Emphasize that the system is integrated and not a set of disconnected technical components.

---

### Slide 5 — Technology Choices
**Main message:**  
The stack was chosen to stay realistic, demonstrable, and security-oriented.

**Oral notes:**  
Mention the chosen stack:
- Samba AD
- Nginx
- PostgreSQL
- Nextcloud
- Wazuh
- OpenVPN
- UFW

Explain that these choices were made for coherence, SME realism, and documentation clarity.

---

### Slide 6 — Core Deployment
**Main message:**  
The project includes all required infrastructure blocks:
- centralized identity
- web service
- backend database
- file sharing
- monitoring and backup
- firewall and exposure control

**Oral notes:**  
Explain that the deployment documentation proves not only installation, but also integration and validation.

---

### Slide 7 — Security Controls
**Main message:**  
Security was integrated into the design from the start.

**Oral notes:**  
Explain the main controls:
- least privilege
- centralized access control
- restricted admin paths
- backend isolation
- firewalling
- monitoring
- backup logic

State that the objective was realistic defense, not enterprise over-engineering.

---

### Slide 8 — Blue Team View
**Main message:**  
The Blue Team work focused on defensive review, evidence, findings, remediation, and retest logic.

**Oral notes:**  
Summarize the Blue Team perspective:
- review of access control
- monitoring usefulness
- backup credibility
- exposure control
- documentation and evidence maturity

Highlight that one of the main strengths is the strong structure of the defensive documentation.

---

### Slide 9 — Red Team View
**Main message:**  
The Red Team work focused on attack surface, offensive exposure, backend reachability, remote access boundaries, and admin path restriction.

**Oral notes:**  
Explain that the Red Team contribution was non-destructive and improvement-oriented.  
Mention the main offensive review themes:
- web exposure
- backend isolation
- admin path exposure
- remote access boundary
- unexpected ports

---

### Slide 10 — Main Findings and Priorities
**Main message:**  
The main remaining priorities are:
- collect real proof
- validate access control in practice
- validate restricted exposure
- validate backup and restore logic
- confirm monitoring coverage

**Oral notes:**  
Explain that the project’s main remaining risk is not conceptual weakness, but final proof and completion maturity.

---

### Slide 11 — Project Management and Delivery
**Main message:**  
The project was managed with a structured delivery logic including charter, roles, Agile practices, Kanban, roadmap, and budget.

**Oral notes:**  
Explain that the project is not only technical.  
It also includes planning, task ownership, scope control, and retrospective thinking.

---

### Slide 12 — Lessons Learned
**Main message:**  
The project showed that strong structure, scope discipline, and evidence collection are as important as technical build quality.

**Oral notes:**  
Highlight the main lessons:
- structure matters
- working services need proof
- security must be built into the design
- scope must stay controlled
- documentation quality changes the final result

---

### Slide 13 — Conclusion
**Main message:**  
The project delivers a strong, realistic, and defensible final infrastructure project, with clear next steps for final proof completion and remediation validation.

**Oral notes:**  
Close with confidence.  
State that the infrastructure is coherent, secure by design, well documented, and strengthened by both Blue Team and Red Team perspectives.

## Delivery Advice
During the presentation:
- do not read the slides
- use the slides as anchors
- keep transitions short and clear
- insist on coherence between business needs, architecture, and security
- put the strongest visuals on architecture, controls, and findings
- finish with a strong synthesis

## Final Reminder
The slides should remain:
- visually simple
- low in text
- high in clarity
- strongly aligned with the oral explanation