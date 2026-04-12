# Access Control Tests README

## Purpose
This folder stores proof related to identity, permissions, and access-control behavior.

Its purpose is to centralize evidence showing:
- authorized access works
- unauthorized access is denied or limited
- group-based access behaves as intended
- permission logic is effectively enforced

These proofs are especially important for IAM validation, file-sharing validation, and Blue Team review.

## Expected Content
This folder may contain:
- authorized user access screenshots
- denied access screenshots
- group membership proof
- role-based access test outputs
- shared-resource access comparison
- admin-versus-standard access proof

## Recommended File Types
Typical file formats may include:
- `.png`
- `.jpg`
- `.txt`

## Recommended Naming Convention
Use clear filenames such as:
- `ACC01_authorized_file_access.png`
- `ACC02_denied_file_access.png`
- `ACC03_group_membership.txt`
- `ACC04_admin_access_success.png`
- `ACC05_unapproved_admin_access_denied.txt`

## Quality Rules
Each proof should:
- clearly show who is allowed and who is denied
- stay linked to a real resource or service
- avoid exposing real passwords or secrets
- be easy to map to test cases and findings
- remain consistent with the intended permission model

## Notes
This folder is one of the most important proof areas for demonstrating least privilege and centralized access governance.