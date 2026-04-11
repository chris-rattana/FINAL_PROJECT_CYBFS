# Timeline

## Purpose
This document records the chronology of the Blue Team case `HOME_Run01`.

Its purpose is to:
- track the sequence of defensive review activities
- show how observations, findings, and remediation evolved over time
- provide traceability between analysis steps and case outputs
- support final review, retest, and presentation

This timeline is not only a date log. It is also a structured record of how the Blue Team work progressed from initial review to defensive conclusions.

## Case Identification
- Case ID: HOME_Run01
- Workstream: Blue Team
- Review Type: Defensive review of the deployed infrastructure
- Environment Type: SME-scale remote-first startup lab environment
- Status: In progress

## Timeline Use Rules
Each timeline entry should capture:
- date or sequence reference
- activity performed
- component concerned
- main observation
- related evidence if available
- consequence for the case
- follow-up action if needed

The timeline should remain factual and concise.

## Recommended Entry Format
Use the following structure for each event:

- **Date / Step:**  
- **Activity:**  
- **Component:**  
- **Observation:**  
- **Evidence Reference:**  
- **Case Impact:**  
- **Next Action:**  

## Timeline Entries

---

### Entry 01
- **Date / Step:** Initial case setup
- **Activity:** Define Blue Team review perimeter and operating rules
- **Component:** Entire infrastructure
- **Observation:** Review scope established for AD / IAM, Web Server, Database, File Server, Backup and Monitoring, and Network Security
- **Evidence Reference:** `01_Scope_Rules.md`
- **Case Impact:** Defensive review can proceed with clear boundaries
- **Next Action:** Begin environment review and collect baseline observations

---

### Entry 02
- **Date / Step:** Baseline environment review
- **Activity:** Review deployed infrastructure state and identify major components available for validation
- **Component:** Entire infrastructure
- **Observation:** Core services identified as review targets; documentation structure available for defensive analysis
- **Evidence Reference:** deployment documentation, screenshots folders, technical specification
- **Case Impact:** Case linked to real project environment
- **Next Action:** Record infrastructure snapshot in terrain card

---

### Entry 03
- **Date / Step:** Initial terrain recording
- **Activity:** Summarize the environment under review and defensive context
- **Component:** Entire infrastructure
- **Observation:** Environment characterized as SME-scale remote-first startup lab infrastructure with centralized IAM, web, database, file sharing, monitoring/backup, and network security
- **Evidence Reference:** `03_Terrain_Card.md`
- **Case Impact:** Review context formalized
- **Next Action:** Start evidence indexing by component

---

### Entry 04
- **Date / Step:** Evidence collection phase started
- **Activity:** Collect first technical proofs from deployment and validation materials
- **Component:** Entire infrastructure
- **Observation:** Service status, screenshots, configuration excerpts, firewall outputs, and access results identified as usable evidence sources
- **Evidence Reference:** `04_Evidence_Index.md`
- **Case Impact:** Findings can be tied to verifiable proof
- **Next Action:** Review IAM and access governance

---

### Entry 05
- **Date / Step:** IAM defensive review
- **Activity:** Review centralized identity and access management posture
- **Component:** AD / IAM
- **Observation:** To complete
- **Evidence Reference:** To complete
- **Case Impact:** To complete
- **Next Action:** To complete

---

### Entry 06
- **Date / Step:** Web service defensive review
- **Activity:** Review web server exposure, service availability, and backend separation
- **Component:** Web Server
- **Observation:** To complete
- **Evidence Reference:** To complete
- **Case Impact:** To complete
- **Next Action:** To complete

---

### Entry 07
- **Date / Step:** Database defensive review
- **Activity:** Review database exposure, service state, and backend connectivity logic
- **Component:** Database
- **Observation:** To complete
- **Evidence Reference:** To complete
- **Case Impact:** To complete
- **Next Action:** To complete

---

### Entry 08
- **Date / Step:** File-sharing defensive review
- **Activity:** Review authenticated access, permissions, and collaborative data exposure
- **Component:** File Server
- **Observation:** To complete
- **Evidence Reference:** To complete
- **Case Impact:** To complete
- **Next Action:** To complete

---

### Entry 09
- **Date / Step:** Monitoring and backup defensive review
- **Activity:** Review operational visibility, backup existence, and restore-oriented readiness
- **Component:** Backup and Monitoring
- **Observation:** To complete
- **Evidence Reference:** To complete
- **Case Impact:** To complete
- **Next Action:** To complete

---

### Entry 10
- **Date / Step:** Network security defensive review
- **Activity:** Review firewall posture, intended exposure, backend isolation, and admin path restriction
- **Component:** Network Security
- **Observation:** To complete
- **Evidence Reference:** To complete
- **Case Impact:** To complete
- **Next Action:** To complete

---

### Entry 11
- **Date / Step:** First findings consolidation
- **Activity:** Convert reviewed observations into formal findings
- **Component:** Entire infrastructure
- **Observation:** Meaningful defensive issues selected and documented based on actual evidence
- **Evidence Reference:** `05_Findings.md`
- **Case Impact:** Risk reasoning and prioritization become possible
- **Next Action:** Populate risk register

---

### Entry 12
- **Date / Step:** Risk evaluation phase
- **Activity:** Assign qualitative risk level and treatment priority to findings
- **Component:** Entire infrastructure
- **Observation:** Risks classified according to project-scale impact and urgency
- **Evidence Reference:** `06_Risk_Register.xlsx`
- **Case Impact:** Remediation can be prioritized
- **Next Action:** Build remediation plan

---

### Entry 13
- **Date / Step:** Remediation planning phase
- **Activity:** Define corrective actions linked to documented findings
- **Component:** Entire infrastructure
- **Observation:** Practical remediation actions identified for key defensive issues
- **Evidence Reference:** `07_Remediation_Plan.md`
- **Case Impact:** Case becomes improvement-oriented and not only descriptive
- **Next Action:** Perform or document retest logic

---

### Entry 14
- **Date / Step:** Retest phase
- **Activity:** Verify whether corrective actions reduced or removed identified weaknesses
- **Component:** Entire infrastructure
- **Observation:** To complete
- **Evidence Reference:** `08_Retest_Results.md`
- **Case Impact:** Confirms whether defensive posture improved
- **Next Action:** Prepare executive summary

---

### Entry 15
- **Date / Step:** Case closure summary
- **Activity:** Summarize overall Blue Team conclusions
- **Component:** Entire infrastructure
- **Observation:** Final defensive posture summarized with major findings, priorities, and residual issues
- **Evidence Reference:** `09_Executive_Summary.md`
- **Case Impact:** Case ready for review and presentation use
- **Next Action:** Integrate with final project narrative

## Condensed Timeline Table

| Step | Activity | Component | Output |
|------|----------|-----------|--------|
| 01 | Scope definition | Entire infrastructure | `01_Scope_Rules.md` |
| 02 | Baseline environment review | Entire infrastructure | review notes |
| 03 | Terrain recording | Entire infrastructure | `03_Terrain_Card.md` |
| 04 | Evidence collection start | Entire infrastructure | `04_Evidence_Index.md` |
| 05 | IAM review | AD / IAM | findings input |
| 06 | Web review | Web Server | findings input |
| 07 | Database review | Database | findings input |
| 08 | File-sharing review | File Server | findings input |
| 09 | Monitoring / backup review | Backup and Monitoring | findings input |
| 10 | Network security review | Network Security | findings input |
| 11 | Findings consolidation | Entire infrastructure | `05_Findings.md` |
| 12 | Risk evaluation | Entire infrastructure | `06_Risk_Register.xlsx` |
| 13 | Remediation planning | Entire infrastructure | `07_Remediation_Plan.md` |
| 14 | Retest | Entire infrastructure | `08_Retest_Results.md` |
| 15 | Executive summary | Entire infrastructure | `09_Executive_Summary.md` |

## Notes for Real Case Completion
When converting this timeline into the final case record:
- replace “To complete” entries with actual review facts
- add exact dates if available
- reference actual evidence IDs from `04_Evidence_Index.md`
- note major remediation milestones
- mention any delayed, partial, or blocked actions
- keep the chronology aligned with the actual case progression

## Timeline Quality Criteria
A good timeline should:
- be chronological
- remain factual
- link activities to outputs
- show progression from review to improvement
- support the credibility of the case
- remain consistent with findings, remediation, and retest documents

## Conclusion
This timeline provides the chronological backbone of the Blue Team case `HOME_Run01`.

Once completed with actual dates, observations, and evidence references, it will show how the defensive review progressed from scoped analysis to findings, remediation planning, and case closure.