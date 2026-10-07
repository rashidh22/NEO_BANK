# NeoBank Platform

Enterprise-oriented monorepo scaffold for NeoBank, a simulated retail internet banking application. This repository is derived from the submitted PRD, project design baseline, sprint backlog and high-level architecture diagram.

> **Product safety boundary:** all money movement is simulated. This project must never connect to a real payment rail, banking core, UPI network or execute real financial transactions. AI capabilities are advisory; they cannot approve loans or execute transfers. The banking assistant is read-only.

## Repository approach

This is a proposed modular monorepo for a multi-team delivery. The design baseline describes independently owned services; service boundaries and deployment topology remain engineering proposals pending the service catalogue and architecture decisions. The folders are foundations, not implemented services. The submitted final project document explicitly places service catalogue, ERD, API contracts and event catalogue ahead of coding.

## Top-level map

- `frontend/web/` — React responsive customer and staff portal.
- `backend/gateway/` — API gateway, routing, rate limits and edge observability.
- `backend/services/` — identity, customer, account, beneficiary, transfer, schedule, statement, loan, risk/AI, notification and admin domains.
- `backend/platform/` — cross-cutting audit/configuration/testing support; avoid shared domain logic.
- `contracts/` — versioned REST/event schemas and compatibility guidance.
- `infra/` — local development, containers, Kubernetes, Terraform and observability foundations.
- `tests/` — contract, end-to-end, performance and security test suites.
- `docs/` — product traceability, proposed architecture, API/data/event/security designs and runbooks.

See [repository map](docs/development/repository-map.md), [product constraints](docs/product/product-baseline.md), [open decisions](docs/decisions/open-decisions.md), and [architecture proposal](docs/architecture/overview.md).

## Build sequence

1. Resolve product TBDs and approve MVP/release scope.
2. Approve service catalogue and service dependency matrix.
3. Approve ERD and database ownership per service.
4. Approve API and event contracts, security model and transfer lifecycle.
5. Add implementation and CI gates only after the above design baseline is agreed.

## Getting started

This repository is currently a structure and design baseline; runnable application code and setup commands will be added after the design artifacts are approved. Start with `docs/development/`.

## Governance

Use feature branches and pull requests; require domain owner review, security review for auth/authorization/data handling changes, contract compatibility review for API/event changes, and an auditable decision record for architecture changes. Never commit credentials, real customer data, production secrets or financial information.
