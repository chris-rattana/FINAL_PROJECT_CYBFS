# Blue Team Appendices README

## Purpose
This folder contains the appendices for the Blue Team workstream of the final CYBFS project.

Its purpose is to:
- store supporting material that is useful for the Blue Team case
- preserve complementary technical proof
- avoid overloading the main case documents
- improve traceability and review readability
- support final presentation and project defense

The appendices are not the main analytical output of the Blue Team case. They are supporting materials referenced when useful from the case files.

## Role of the Appendices in the Blue Team Workflow
The Blue Team case is primarily documented through:
- scope and rules
- timeline
- terrain card
- evidence index
- findings
- risk register
- remediation plan
- retest results
- executive summary

The appendices are used to store additional supporting material that helps justify, clarify, or preserve context for those documents.

## What Should Be Stored Here
This folder can contain:
- additional screenshots not placed directly in the evidence index
- raw command outputs
- longer log excerpts
- configuration excerpts
- firewall rule dumps
- backup notes or restore notes
- monitoring exports
- temporary mapping notes that remain useful for case review
- reference tables used during Blue Team analysis

The appendices should remain useful and relevant. This folder should not become a dump of unrelated files.

## What Should Not Be Stored Here
This folder should not be used for:
- duplicate copies of the main Blue Team case files
- unrelated drafts with no case value
- sensitive secrets or passwords
- raw material that has no clear relation to the review
- unnecessary clutter that makes review harder

Only supporting material with a clear review value should be kept.

## Recommended Subcategories
If the appendices become large, you can organize them into simple subfolders such as:
- `logs/`
- `configs/`
- `raw_outputs/`
- `monitoring_exports/`
- `backup_notes/`
- `mapping_notes/`

This is optional, but useful if the folder grows.

## Typical Appendix Content by Theme

### 1. Logs
Examples:
- authentication-related logs
- web access logs
- service error logs
- system event excerpts
- monitoring-related log samples

### 2. Configuration Excerpts
Examples:
- firewall excerpts
- service configuration notes
- permission-related extracts
- access-related settings
- deployment values useful for review

### 3. Raw Command Outputs
Examples:
- service status outputs
- port visibility outputs
- firewall status outputs
- connectivity test outputs
- backup command results

### 4. Monitoring and Visibility Notes
Examples:
- host visibility captures
- service monitoring exports
- dashboard snapshots
- alert notes
- operational visibility comments

### 5. Backup and Recovery Notes
Examples:
- backup scope notes
- backup execution traces
- restore-oriented notes
- storage path notes
- backup validation comments

## Relationship with the Evidence Index
The appendices are complementary to the evidence index.

### Evidence Index
The evidence index should contain:
- structured evidence IDs
- short reusable proof references
- the main proof backbone of the case

### Appendices
The appendices may contain:
- larger supporting material
- raw supporting context
- longer technical extracts
- background notes linked to evidence IDs

If appendix material is important to a finding, it should be referenced clearly from:
- `04_Evidence_Index.md`
- `05_Findings.md`
- `07_Remediation_Plan.md`
- `08_Retest_Results.md`

## Referencing Rules
When using appendix material:
- give the file a clear name
- make the relation to the case obvious
- mention it in the relevant case document if useful
- avoid keeping anonymous files with no explanation

Recommended naming style:
- `APP01_auth_log_excerpt.txt`
- `APP02_firewall_rules_web.txt`
- `APP03_db_connectivity_raw.txt`
- `APP04_backup_notes.txt`
- `APP05_monitoring_event_excerpt.png`

## Appendix Register Template

| Appendix ID | File Name | Type | Description | Related Document | Notes |
|-------------|-----------|------|-------------|------------------|-------|
| APP01 | APP01_auth_log_excerpt.txt | Text Output | Authentication-related log excerpt | Evidence Index / Findings | To complete |
| APP02 | APP02_firewall_rules_web.txt | Text Output | Web host firewall rules | Evidence Index / Findings | To complete |
| APP03 | APP03_db_connectivity_raw.txt | Text Output | Raw DB connectivity output | Evidence Index / Findings | To complete |
| APP04 | APP04_backup_notes.txt | Text Note | Backup scope and validation notes | Remediation / Retest | To complete |
| APP05 | APP05_monitoring_event_excerpt.png | Screenshot | Monitoring event visibility proof | Evidence Index / Findings | To complete |

## Quality Rules
Appendix material should:
- remain readable
- have a clear purpose
- support the case directly
- be named consistently
- avoid duplication when possible
- stay aligned with the actual environment and review

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
- one or more supporting notes for monitoring, firewalling, or backup
- one or more configuration or log excerpts useful for explaining a finding

## Known Limits
This appendix folder is a support area for a project-scale Blue Team case.

It is not intended to become:
- a full forensic archive
- a full SOC evidence repository
- a complete enterprise log storage location
- a general-purpose dump folder

Its role is to improve clarity and traceability of the Blue Team case.

## Conclusion
This folder provides supporting material for the Blue Team workstream.

Once populated with relevant logs, raw outputs, configuration excerpts, and technical notes, it will strengthen the Blue Team case by preserving useful context without overloading the main case documents.