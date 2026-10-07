# Open product and architecture decisions

Preserve these as unresolved until their owners decide; do not infer rules from the architecture picture or sprint examples.

## Product decisions

- Product Owner: MVP/release scope and priorities for BNK-FR-01..08 and BNK-AI-01..05.
- Product/business: beneficiary cooling duration, edit/delete lifecycle, activation and notifications.
- Product/security: confirmation requirements, OTP expiry/retry limits, transfer limits, fraud thresholds/order, high-risk override and risk-service outage fallback.
- Product: recurrence options, end-date requirement, cancellation/modification rules and execution calendar/time zone.
- Credit/business: eligibility rules, loan amount/tenure/rate source, KYC document types and human approval boundaries.
- Operations: Teller permissions, exact staff scopes, admin authentication and audit retention.
- Product: account detail fields, balance semantics, masking standard, statement range/size rules and empty/error behavior details.

## Architecture decisions

- Microservices vs modular monolith deployment; service catalogue and team ownership.
- Ledger/account database ownership, transaction consistency boundary and locking strategy.
- API contracts, versioning, idempotency key semantics and error envelope.
- Event broker, event catalogue, schema evolution, outbox/inbox and retry/DLQ policy.
- Scheduler coordination, duplicate prevention, retry/backoff and recovery policy.
- Identity provider, token/session design, secret/key rotation and authorization model.
- Storage providers, data retention, encryption, backup, disaster recovery and deployment target.
- Monitoring stack and SLOs.

Record resolved architecture choices as numbered ADRs under `docs/architecture/adr/`; preserve product rules in the approved PRD/decision record.
