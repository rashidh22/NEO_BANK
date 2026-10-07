# Proposed architecture overview

## Status

Proposed engineering design based on product requirements and supplied high-level diagram. Not an approved service catalogue. Decide service boundaries, deployment model and data ownership before implementation.

## Context

Responsive React SPA → API gateway → domain services → service-owned PostgreSQL schemas/databases, Redis for cache/session/short-lived OTP state, document storage for KYC/statements, and an audit store. External capabilities are simulated: UPI, IFSC lookup and AI/ML. A scheduler executes due simulated schedules. Event streaming/outbox is proposed for reliable cross-service notifications/audit and schedule outcomes; select technology after architecture review.

## Proposed domain services

Identity; Customer; Account; Beneficiary; Transfer; Schedule; Statement; Loan; Risk/AI; Notification; Admin. A ledger boundary or account-owned transactional ledger is unresolved and must be decided before transfer implementation. The supplied diagram also presents a modular-monolith option; choose and document deployment topology in an ADR.

## Cross-cutting controls

JWT/RBAC, five-minute idle-session behavior, API rate limits, correlation IDs, structured logs, metrics/traces, immutable audit trail, idempotency for transfer/scheduler retries, transactional consistency and tested recovery. No real payment adapters.

## Design gates

Service catalogue/dependency matrix; ERD/data ownership; REST and event contracts; security LLD; transfer state machine and failure policy; schedule recurrence rules; retention/backup/recovery decisions. See `docs/decisions/open-decisions.md`.
