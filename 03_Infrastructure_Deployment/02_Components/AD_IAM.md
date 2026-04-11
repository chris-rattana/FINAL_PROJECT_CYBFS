# AD / IAM Component

## Purpose
This document describes the deployment role, function, and validation expectations of the centralized identity and access management component used in the project infrastructure.

This component is one of the core foundations of the environment because it provides centralized control over:
- users
- groups
- permissions
- authentication logic
- access to shared resources and services

In a remote-first startup scenario, centralized identity and access management is essential to avoid fragmented local account management and to support controlled remote access.

## Selected Technology
Samba AD

## Business Role
The AD / IAM component supports the following business needs:
- centralized user administration
- controlled access to internal services
- structured permission management
- role-based access to shared resources
- easier onboarding and offboarding
- reduced operational risk linked to unmanaged accounts

This component helps transform the infrastructure from a set of isolated machines into a centrally governed environment.

## Security Role
The AD / IAM component supports the security model of the project by:
- centralizing authentication
- limiting privilege sprawl
- enabling group-based authorization
- improving account governance
- supporting least-privilege logic
- reducing the use of unmanaged local identities

This component is directly linked to the project’s main security priorities:
- secure remote access
- controlled service usage
- traceable account management
- reduced administrative risk

## Main Functions
The AD / IAM component is expected to provide the following main functions:

### 1. User Management
The service must allow the creation and administration of user accounts used within the infrastructure.

### 2. Group Management
The service must support the definition of groups used to organize permissions and access logic.

### 3. Authentication Support
The component must act as a centralized identity reference for authentication-related workflows where applicable.

### 4. Access Governance
The service must support controlled assignment of access rights to services and shared resources.

### 5. Administrative Control
The component must support secure and structured administration of identities and privileges.

## Deployment Position in the Architecture
The AD / IAM service belongs to the protected internal service layer of the infrastructure.

It should not be treated as a broadly exposed public component. It is instead part of the trusted administrative and identity backbone of the environment.

It interacts with:
- administrative accounts and workflows
- file-sharing permissions
- user access logic
- potentially other services using centralized identity references

## Expected Configuration Logic
The following configuration principles apply to this component:

### Centralized Administration
Identity data must be maintained centrally rather than through scattered local accounts whenever possible.

### Group-Based Access
Access to services or shared resources should rely on structured groups instead of ad hoc per-user permissions wherever possible.

### Privileged Access Separation
Administrative and standard access should remain clearly separated.

### Documentation
The identity structure should be documented clearly enough to support:
- administration
- testing
- security review
- final presentation

## Suggested Logical Structure
A simple logical identity structure may include:
- administrative accounts
- standard user accounts
- service-related groups
- shared-resource groups
- access groups for collaboration spaces or file-sharing areas

The exact naming scheme may vary depending on deployment choices, but the logic must remain understandable and defensible.

## Example Functional Scope
The component may be used to support:
- login management for users
- assignment of users to groups
- controlled file-sharing access
- identity-linked administrative workflows
- separation of access according to role

## Security Controls Applied to This Component
The AD / IAM component must be protected through the following controls:

### Restricted Exposure
The service must not be unnecessarily exposed to broad external access.

### Controlled Administrative Access
Administrative operations must be limited to authorized personnel and controlled paths.

### Least Privilege
Only the required privileges should be assigned to users and groups.

### Traceability
Identity-related administration should be documented and, where possible, observable through logs or monitoring.

### Configuration Protection
Important configuration choices and account structures must be preserved and documented.

## Dependencies
The AD / IAM component supports or influences the following other components:
- file-sharing permissions
- administrative access logic
- potentially remote access control
- user-to-service access consistency
- Blue Team review of access governance
- Red Team assessment of identity-related exposure

## Deployment Evidence Expected
The deployment of this component should be supported by evidence such as:
- screenshots of domain or directory configuration
- user and group examples
- access assignment examples
- authentication-related proof where applicable
- command outputs showing service status
- configuration excerpts if relevant

These proofs should be stored in the dedicated screenshots and evidence folders.

## Validation Criteria
The AD / IAM component will be considered correctly deployed if:
- the identity service is installed and operational
- users can be created and managed
- groups can be created and used logically
- access control logic is centralized
- administrative access is structured
- documentation and evidence are available

## Test Examples
Typical validation tests may include:
- creating a test user
- creating a test group
- assigning a user to a group
- verifying that a user gains intended access to a shared resource
- verifying that an unrelated user does not receive the same access
- checking service status and basic administration functionality

## Risks if Poorly Implemented
If this component is weakly implemented, the project may be exposed to:
- privilege sprawl
- inconsistent permissions
- unmanaged user accounts
- excessive administrative access
- weak traceability of identity changes
- higher operational risk during account lifecycle events

## Known Limits
At project scale, the identity environment remains limited compared with a full enterprise directory deployment.

The objective is not to reproduce every advanced AD feature, but to demonstrate:
- centralized access governance
- structured identity management
- realistic administrative logic
- integration with the rest of the infrastructure

## Conclusion
The AD / IAM component is one of the most important building blocks of the infrastructure.

It provides centralized control over identities and permissions, supports secure remote operations, strengthens governance, and improves the coherence of the whole environment. Its successful deployment is critical for both the operational credibility and the security credibility of the final project.