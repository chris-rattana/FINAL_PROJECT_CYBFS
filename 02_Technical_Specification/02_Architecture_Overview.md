# Architecture Overview

## Purpose
This section describes the high-level architecture of the infrastructure designed for the remote-first startup scenario.

The goal of the architecture is to provide secure access to core business services while keeping the environment understandable, manageable, and adapted to SME constraints.

## High-Level Design
The infrastructure is built around a set of integrated services that support business activity, user access, storage, administration, monitoring, and security.

The architecture includes:
- a centralized identity and access management component
- a web service layer
- a backend database
- a file-sharing service
- backup and monitoring capabilities
- network and host security controls

## Core Components

### 1. Identity and Access Management
A centralized directory service is used to manage:
- users
- groups
- permissions
- access to shared and administrative resources

This component acts as the foundation for access control and administration.

### 2. Web Service Layer
A web server or web application provides access to a business service used by the company.

Its role is to:
- expose the application to authorized users
- serve as the entry point for business usage
- interact with the backend database where required

### 3. Database Layer
A database service stores application-related data.

Its role is to:
- support the web service
- centralize data storage
- remain protected from unnecessary direct exposure
- enforce restricted access paths

### 4. File-Sharing Layer
A file server or collaborative drive provides shared access to business documents.

Its role is to:
- support collaboration between remote users
- centralize file storage
- enforce role-based or controlled access

### 5. Monitoring and Backup Layer
A monitoring component provides visibility on infrastructure health and basic events.

A backup component or workflow ensures that the environment includes data protection and recovery logic.

### 6. Security Layer
Security controls are applied across the environment through:
- firewalling
- controlled exposure of services
- host hardening
- access restrictions
- logging
- segmentation or isolation where relevant

## Logical Architecture
At a logical level, the infrastructure follows this flow:

1. users authenticate through the centralized identity layer
2. authorized users access the web service and file-sharing service
3. the web service communicates with the database through a controlled internal path
4. administrative visibility is provided through monitoring and logs
5. backup processes protect critical configuration and data assets
6. security controls reduce attack surface and support defensive review

## Trust Zones
The environment can be described through simplified trust zones:

### User Access Zone
This zone contains remote users and their access path to company services.

### Service Zone
This zone contains exposed or user-facing business services such as the web layer.

### Internal Data Zone
This zone contains protected resources such as the database and identity services.

### Administration and Visibility Zone
This zone contains monitoring, logging, and backup-related functions.

This trust-zone approach helps justify exposure rules and security boundaries.

## Main Data Flows
The main data flows of the architecture are:
- user authentication to centralized identity services
- user access to web and file services
- application communication with the database
- administrative access for maintenance and control
- monitoring and log collection
- backup and restore operations

Each of these flows must be justified and protected.

## Design Principles
The architecture is guided by the following principles:
- simplicity over unnecessary complexity
- centralized control where useful
- reduced exposure of critical services
- clear separation between user-facing and internal components
- maintainability and documentation
- SME-scale feasibility
- integration of security from the design stage

## Architectural Assumptions
The project assumes:
- a limited-size organization
- a moderate number of users
- a need for remote access
- a realistic but not enterprise-scale infrastructure
- a demonstrable environment suitable for final presentation and review

## Expected Outcome
The final architecture must support:
- operational continuity
- controlled user access
- secure service integration
- administrative visibility
- baseline cyber resilience

It must also provide enough structure to support Blue Team review, Red Team assessment, remediation planning, and final presentation.

## Conclusion
The proposed architecture is a realistic SME infrastructure model for a remote-first startup. It combines core services, identity management, storage, monitoring, and security controls into a coherent environment that can be deployed, documented, assessed, and presented.