# Red Team Appendices README

## Purpose
This folder contains the appendices for the Red Team workstream of the final CYBFS project.

Its purpose is to:
- store supporting material useful for the Red Team engagement
- preserve complementary offensive review evidence
- avoid overloading the main engagement documents
- improve traceability and review readability
- support final reporting and presentation

The appendices are not the main analytical output of the Red Team engagement. They are supporting materials referenced when useful from the main Red Team files.

## Role of the Appendices in the Red Team Workflow
The Red Team engagement is primarily documented through:
- methodology
- engagement letter
- rules of engagement
- emulation plan
- target surface worksheet
- evidence index
- findings
- pentest report
- remediation tracker
- retest report

The appendices are used to store additional supporting material that helps justify, clarify, or preserve context for those documents.

## What Should Be Stored Here
This folder can contain:
- additional screenshots not placed directly in the evidence index
- raw reachability outputs
- scan excerpts
- port visibility outputs
- denied-path outputs
- firewall observation dumps
- raw service response captures
- offensive review notes
- comparison notes between expected and observed exposure
- retest raw outputs

The appendices should remain useful and relevant. This folder should not become a dump of unrelated files.

## What Should Not Be Stored Here
This folder should not be used for:
- duplicate copies of the main Red Team engagement files
- unrelated drafts with no engagement value
- secrets, passwords, tokens, or sensitive credentials
- raw material with no clear relation to the offensive review
- unnecessary clutter that makes review harder

Only supporting material with a clear assessment value should be kept.

## Recommended Subcategories
If the appendices become large, you can organize them into simple subfolders such as:
- `scans/`
- `raw_outputs/`
- `firewall_notes/`
- `reachability_tests/`
- `retest_outputs/`
- `mapping_notes/`

This is optional, but useful if the folder grows.

## Typical Appendix Content by Theme

### 1. Scan and Reachability Outputs
Examples:
- port scan results
- listening service comparisons
- raw connection attempt outputs
- denied-path command outputs
- quick target reachability notes

### 2. Firewall and Filtering Notes
Examples:
- firewall rule dumps
- filtered-path observations
- before/after exposure notes
- backend filtering comparisons

### 3. Service Response Captures
Examples:
- web response observations
- endpoint response captures
- admin-path behavior notes
- file-service entry observations

### 4. Remote Access Notes
Examples:
- VPN path notes
- internal reachability through approved remote access
- unexpected reachability after remote access
- path restriction comparison notes

### 5. Retest Raw Material
Examples:
- repeated scan outputs
- before/after blocked-path proof
- retest reachability comparisons
- residual exposure notes

## Relationship with the Evidence Index
The appendices are complementary to the Red Team evidence index.

### Evidence Index
The evidence index should contain:
- structured evidence IDs
- short reusable proof references
- the main proof backbone of the engagement

### Appendices
The appendices may contain:
- larger supporting material
- raw offensive outputs
- longer technical extracts
- background notes linked to evidence IDs

If appendix material is important to a finding, it should be referenced clearly from:
- `05_Evidence_Index.md`
- `06_Findings.md`
- `07_Pentest_Report.md`
- `08_Remediation_Tracker.md`
- `09_Retest_Report.md`

## Referencing Rules
When using appendix material:
- give the file a clear name
- make the relation to the engagement obvious
- mention it in the relevant Red Team document if useful
- avoid keeping anonymous files with no explanation

Recommended naming style:
- `RAPP01_port_scan_raw.txt`
- `RAPP02_db_reachability_test.txt`
- `RAPP03_admin_path_test.txt`
- `RAPP04_firewall_observation_web.txt`
- `RAPP05_remote_access_notes.txt`
- `RAPP06_retest_scan_comparison.txt`

## Appendix Register Template

| Appendix ID | File Name | Type | Description | Related Document | Notes |
|-------------|-----------|------|-------------|------------------|-------|
| RAPP01 | RAPP01_port_scan_raw.txt | Text Output | Raw port visibility output | Evidence Index / Findings | To complete |
| RAPP02 | RAPP02_db_reachability_test.txt | Text Output | Raw backend reachability test | Evidence Index / Findings | To complete |
| RAPP03 | RAPP03_admin_path_test.txt | Text Output | Raw admin-path reachability test | Evidence Index / Findings | To complete |
| RAPP04 | RAPP04_firewall_observation_web.txt | Text Output | Web-host filtering notes | Evidence Index / Pentest Report | To complete |
| RAPP05 | RAPP05_remote_access_notes.txt | Text Note | Remote access reachability notes | Evidence Index / Findings | To complete |
| RAPP06 | RAPP06_retest_scan_comparison.txt | Text Output | Before/after retest comparison | Retest Report | To complete |

## Quality Rules
Appendix material should:
- remain readable
- have a clear purpose
- support the engagement directly
- be named consistently
- avoid duplication when possible
- stay aligned with the actual environment and offensive review

## Sensitive Information Handling
Before storing appendix material:
- remove or mask passwords
- remove or mask tokens and secrets
- avoid unnecessary confidential values
- keep only what is useful for review
- preserve technical meaning without exposing sensitive content

## Minimum Good Practice
At minimum, this folder should be able to store:
- one or more raw outputs too long for the main evidence index
- one or more supporting notes for exposure, firewalling, or remote access
- one or more retest comparison outputs
- one or more raw reachability tests useful for explaining a finding

## Known Limits
This appendix folder is a support area for a project-scale Red Team engagement.

It is not intended to become:
- a full offensive operations archive
- a large penetration-testing data vault
- a general-purpose dump folder
- a store of unnecessary raw material with no review value

Its role is to improve clarity and traceability of the Red Team engagement.

## Conclusion
This folder provides supporting material for the Red Team workstream.

Once populated with relevant raw outputs, reachability notes, scan excerpts, filtering observations, and retest comparisons, it will strengthen the Red Team engagement by preserving useful offensive context without overloading the main engagement documents.