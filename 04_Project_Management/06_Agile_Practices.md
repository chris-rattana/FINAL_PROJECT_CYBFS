# Agile Practices

## Purpose
This document explains how Agile practices were applied to the final CYBFS project.

Its purpose is to:
- show that the project was managed with a structured and adaptive delivery approach
- demonstrate the use of Agile-minded work organization
- explain how scope, priorities, and progress were managed
- support the Project Management File required by the final project

The project does not claim to implement a full enterprise Agile framework. Instead, it applies realistic Agile practices adapted to a short infrastructure and cybersecurity project.

## Why Agile Was Used
The project management materials highlight Agile as a flexible and iterative approach that is particularly useful for technical teams when the final product is not completely fixed at the beginning. Agile emphasizes adaptation, frequent delivery of useful results, collaboration, and continuous improvement. :contentReference[oaicite:4]{index=4} :contentReference[oaicite:5]{index=5}

This logic fits the final project well because the project required:
- progressive design decisions
- iterative infrastructure deployment
- continuous validation
- adjustment of priorities during implementation
- alignment between build, security, documentation, and presentation

## Agile Positioning in This Project
The project used a practical Agile approach combining:
- MVP-first thinking
- Kanban-based workflow tracking
- iterative delivery of components
- continuous documentation
- regular review and reprioritization

This means that the project was not managed as a rigid linear sequence from start to finish. Instead, it was built progressively, with frequent adjustment based on actual progress, technical blockers, and validation results. This is consistent with the course material, which stresses responsiveness to change, working output over excessive formality, and regular reflection on how to improve. :contentReference[oaicite:6]{index=6}

## Agile Principles Applied

### 1. MVP-First Delivery
The project was managed around a minimum viable project scope rather than around a maximal feature set.

This means the team prioritized:
- the required core infrastructure components
- basic integration between services
- minimum viable security controls
- usable monitoring and backup logic
- enough evidence and documentation to support final review

This approach is aligned with the guide, which recommends keeping scope small, making something work first, and avoiding over-engineering. :contentReference[oaicite:7]{index=7} :contentReference[oaicite:8]{index=8}

### 2. Iterative Progression
The project was advanced through progressive iterations instead of trying to finalize everything at once.

Typical iteration logic was:
- define context and architecture
- deploy one component
- validate it
- document it
- connect it to the rest of the environment
- move to the next component
- revisit weak points later

This reduced the risk of creating a large undocumented or unvalidated environment.

### 3. Visual Workflow Management
The project used a Kanban-style workflow to visualize tasks and move work from planning to completion.

This is directly consistent with the course guidance that recommends Kanban to visualize work, limit work in progress, and improve flow from backlog to done. :contentReference[oaicite:9]{index=9} :contentReference[oaicite:10]{index=10}

### 4. Small Work Items
Tasks were broken down into manageable work items so they could move through the workflow in a reasonable amount of time.

This follows the guidance that Kanban cards should not be so large that they remain blocked for too long, and not so small that the board becomes chaotic. 

### 5. Continuous Validation
Progress was not measured only by writing documentation. It was also measured by:
- deployed services
- successful tests
- screenshots and command outputs
- usable integration between components
- visible improvements in project completeness

This aligns with the Agile idea that working output is a primary measure of progress. 

### 6. Adaptation to Change
The project approach allowed reprioritization when necessary.

Examples of possible adjustments include:
- simplifying architecture choices
- delaying non-critical enhancements
- focusing first on required services
- adjusting documentation order
- postponing advanced hardening until the core environment worked correctly

This matches the Agile emphasis on responding to change over rigidly following an initial plan. :contentReference[oaicite:13]{index=13}

### 7. Continuous Improvement
The project included regular reassessment of:
- what was completed
- what remained blocked
- what needed simplification
- what could be improved in the next pass
- what should be deferred outside the MVP

This is coherent with the Agile principle of reflecting regularly and tuning the team’s behavior to become more effective. 

## Agile Practices Used in Concrete Terms

## 1. Backlog Management
A list of project tasks was maintained and progressively refined.

The backlog included work items such as:
- define business context
- complete PRD
- complete technical specification
- deploy AD / IAM
- deploy web server
- deploy database
- deploy file-sharing service
- configure backup and monitoring
- configure firewall and remote access
- complete Blue Team and Red Team documentation
- prepare final presentation

## 2. Kanban Workflow
A Kanban board was used to track the movement of tasks through a simple workflow.

Typical columns used:
- Backlog
- To Do
- Doing
- Review / Validate
- Done

This structure made it easier to:
- see what remained to do
- identify active work
- validate completed work
- track delivery progress

## 3. Work-in-Progress Discipline
Only a limited number of tasks should remain active at the same time.

The objective of this practice is to:
- avoid spreading effort too thin
- reduce unfinished work
- improve focus
- make progress visible more quickly

This is coherent with Kanban’s focus on limiting work in progress and improving flow. 

## 4. Incremental Documentation
Documentation was produced progressively rather than postponed to the very end.

This practice helped:
- preserve technical details while still fresh
- reduce missing evidence
- keep deployment and documentation aligned
- improve final review readiness

## 5. Review and Reprioritization
At regular moments, the project work was reviewed in order to:
- confirm what was done
- identify blockers
- reclassify priorities
- reduce unnecessary scope
- decide what belonged to the MVP and what did not

## 6. Evidence-Driven Completion
A task was considered meaningfully advanced only when it had at least some combination of:
- implementation
- validation
- documentation
- evidence

This helped reduce the gap between “configured” and “actually ready for final review.”

## Agile Roles in Practice
Even in a small-team or single-main-contributor context, Agile-minded role separation remained useful.

The project kept practical distinction between:
- project coordination
- architecture and build
- security review
- documentation
- presentation preparation

This improved clarity of ownership without requiring a large formal team structure.

## How Agile Helped This Project
Using Agile practices improved the project in the following ways:
- the scope remained manageable
- priorities stayed visible
- core requirements were handled first
- the team avoided waiting for “perfect” completeness before validating
- documentation kept pace with implementation
- the final deliverables became easier to assemble progressively

## Practical Limits of the Agile Approach Used
This project did not implement:
- formal Scrum ceremonies with strict sprint structures
- large-team Agile governance
- enterprise-scale reporting
- advanced velocity tracking
- formal product management processes

This is acceptable because the final project only requires realistic Agile practices and documented progress, not a full scaled Agile organization. :contentReference[oaicite:16]{index=16}

## Example Agile Rhythm Used
A simple and realistic rhythm for the project is:

### Daily or Frequent Check
- review active tasks
- identify blockers
- move cards on the Kanban board
- decide immediate priorities

### End-of-Component Review
- confirm service works
- collect evidence
- complete documentation
- decide whether to move forward or fix issues first

### End-of-Phase Review
- confirm whether the MVP remains realistic
- review missing deliverables
- re-evaluate next priorities
- update board and planning

## Indicators of Agile Progress
The following indicators can be used to show documented progress:
- number of cards moved to Done
- number of core services deployed
- number of validated integrations
- number of completed documentation sections
- amount of evidence collected
- reduction of remaining blockers

## Conclusion
Agile practices were applied to this project in a practical and realistic way.

Rather than using a rigid delivery model, the project relied on MVP-first thinking, Kanban visualization, iterative progression, continuous validation, and regular reprioritization. This approach helped keep the project coherent, manageable, and aligned with the final CYBFS expectations for documented progress, realistic planning, and professional project management.