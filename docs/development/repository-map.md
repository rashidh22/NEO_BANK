# Repository map

`frontend/web`: React SPA modules by product capability.
`backend/gateway`: ingress, auth context propagation, throttling and request correlation.
`backend/services/<domain>`: independently owned domain code, API, migrations, configuration and service-level documentation once approved.
`backend/platform`: cross-cutting libraries only; keep domain rules in owning services.
`contracts/openapi`: versioned REST specifications; `contracts/events` and `contracts/schemas`: event envelopes and schemas.
`infra/local`: developer dependencies; `infra/kubernetes`: environment overlays; `infra/terraform`: cloud modules; `infra/observability`: dashboards/alerts/telemetry configuration.
`tests`: contract, end-to-end, performance and security suites.
`docs`: product traceability, architecture decisions, runbooks and operational policy.

Scaffold only: implementation languages, build system, service boundaries, database topology, deployment platform and CI enforcement remain to be approved.
