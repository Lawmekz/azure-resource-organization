# RBAC Role Assignment Summary Report

## Overview
Role-Based Access Control (RBAC) was implemented across three Resource Groups
to simulate a multi-team Azure environment with least-privilege access.

## Role Assignments

| User | Role | Scope | Rationale |
|------|------|-------|-----------|
| Dev User TeamA | Contributor | rg-webapp-dev-eastus-001 | Developers need full access to create and manage resources in development |
| Prod User TeamB | Reader | rg-webapp-prod-eastus-001 | Operations team can monitor production but cannot make changes |
| Sec User TeamC | Reader | rg-shared-services-eastus-001 | Security team needs visibility into shared services for auditing |

## Rationale

### Principle of Least Privilege
Each team was granted only the minimum permissions required for their role.

### Environment Separation
- Development: Contributor access allows developers to iterate freely
- Production: Reader-only prevents accidental changes to live environment
- Shared Services: Reader access allows monitoring without modification rights
