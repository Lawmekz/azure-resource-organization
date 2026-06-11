# Azure Resource Organization Project

## Author
- **Name:** [Ajagu]
- **Date:** June 2026

---

## Naming Convention Strategy

### Format
{resourcetype}-{appname}-{environment}-{region}-{instance}

### Component Key

| Component | Code | Meaning |
|-----------|------|---------|
| Environment | dev | Development |
| Environment | prod | Production |
| Environment | shared | Shared Services |
| Region | eastus | East US |
| Instance | 001 | First instance |

---

## Resource Naming Table

| Resource Type | Format | Example |
|---------------|--------|---------|
| Subscription | sub-{app}-{env}-{instance} | sub-learning-dev-001 |
| Resource Group | rg-{app}-{env}-{region}-{instance} | rg-webapp-dev-eastus-001 |
| Virtual Machine | vm-{app}-{env}-{region}-{instance} | vm-webapp-dev-eastus-001 |
| Storage Account | st{app}{env}{region}{instance} | stwebappdeveastus001 |
| Database | db-{app}-{env}-{region}-{instance} | db-webapp-prod-eastus-001 |

> Note: Storage accounts do NOT allow hyphens — use lowercase alphanumeric only.

---

## Resource Organization Strategy

Resources are grouped by **environment** and **lifecycle**:

- `rg-webapp-dev-eastus-001` — Development environment (temporary, deletable)
- `rg-webapp-prod-eastus-001` — Production environment (protected, stable)
- `rg-shared-services-eastus-001` — Shared resources used across environments

---

## Tagging Strategy

| Tag Key | Example Value | Purpose |
|---------|--------------|---------|
| environment | development / production | Identify environment |
| owner | teamA / teamB | Track ownership |
| project | azure-learning | Group by project |
| costcenter | cc-001 | Cost allocation |
| createdby | [your name] | Audit trail |

---

## RBAC Strategy (Summary)

| Team | Scope | Role |
|------|-------|------|
| Team A (Developers) | Dev Resource Group | Contributor |
| Team B (Operations) | Prod Resource Group | Reader |
| Team C (Security) | Subscription | Security Reader |

---

## Project Tasks Progress

- [x] Task 1 - Naming Convention Designed
- [ ] Task 2 - Resource Groups Created
- [ ] Task 3 - Resources Deployed
- [ ] Task 4 - Tagging Applied
- [ ] Task 5 - RBAC Configured
- [ ] Task 6 - Lifecycle Management Tested
- [ ] Task 7 - IaC Automation (Optional)
