# Calee Issue Classification Benchmark

**Status:** Authoritative cross-repository standard  
**Owner:** Calee engineering and product triage  
**Adopted:** 6 August 2026  
**Applies to:** All issues created in repositories owned by `CaleeAdmin`

This document is the source of truth for classifying Calee issues. The machine-readable companion is [`issue-classification.yml`](issue-classification.yml).

## Purpose

Classification supports backlog decomposition, planning, review depth, regression expectations and release coordination.

- **Complexity** describes implementation structure, architectural reach and uncertainty.
- **Risk** describes the consequence and likelihood of failure.
- **Priority** describes delivery order and urgency.

Complexity does not estimate elapsed time and does not replace Risk or Priority.

## Complexity scale

| Code | Name | Definition | Typical characteristics |
|---|---|---|---|
| **C1** | **Trivial** | Mechanical change with virtually no design decision. | Typo, copy correction, obvious constant change, isolated asset replacement or another self-evident change with narrowly focused verification. |
| **C2** | **Small** | Localised implementation using an established pattern. | Normally one repository; limited files or one operational procedure; no persistent schema, security-boundary, migration or material compatibility change. |
| **C3** | **Medium** | Bounded feature, correction or regression suite with non-trivial implementation inside the existing architecture. | State, UI, API integration, fixtures, diagnostics and tests may be substantial, but the work has one coherent delivery boundary. |
| **C4** | **Complex** | Material architectural or operational boundary change. | Persistent data model, migration, authentication/authorisation, billing lifecycle, device-policy behaviour, compatibility rollout, distributed coordination or infrastructure subsystem. |
| **C5** | **Epic** | Programme containing several independently deliverable C3 or C4 workstreams. | Requires decomposition, sequencing, cross-repository coordination, separate child issues and programme-level release or acceptance gates. |

Use only these exact names. Do not use alternatives such as `C4 — Large`, `C5 — Very large`, `Major` or `XL`.

## Decision sequence

Apply these questions in order:

1. **Does the issue contain multiple independently deliverable workstreams?**  
   Yes: **C5 — Epic**.

2. **Does it introduce or materially change an architectural boundary, persistent data model, migration, security model, billing lifecycle, device-policy behaviour, infrastructure subsystem or compatibility rollout?**  
   Yes: **C4 — Complex**.

3. **Is it a bounded feature, correction or regression suite requiring non-trivial state, UI, API, fixtures, diagnostics or tests within an existing architecture?**  
   Yes: **C3 — Medium**.

4. **Is it a localised change following an established pattern, normally in one repository, with no schema, security, migration or material compatibility change?**  
   Yes: **C2 — Small**.

5. **Is it an obvious mechanical change with virtually no design decision?**  
   Yes: **C1 — Trivial**.

If none produces a defensible result, the issue is not sufficiently defined for implementation and must be clarified or decomposed before classification is confirmed.

## Interpretation rules

- Complexity measures implementation structure and uncertainty, not business importance.
- A long issue description is not automatically complex.
- Cross-repository work is not automatically C4.
- High-risk store configuration, release operations or privacy-sensitive work may remain C2 or C3 when they do not create new architecture.
- C4 requires a material architecture, migration, security, data, compatibility, billing, device-policy, distributed-systems or infrastructure concern.
- C5 is reserved for programmes that must be split into child issues. A large standalone implementation is C4, not C5.
- Child issues of a C5 epic receive independent classifications and do not inherit C5.
- Scope growth must trigger reassessment before implementation continues.
- Physical qualification alone does not force C4; classify the underlying system change and test architecture.

## Calibration examples

### C1 — Trivial

No open issue in the 6 August 2026 benchmark set met C1. Reserve it for genuinely mechanical work with virtually no design choice.

### C2 — Small

- `CaleeAdmin/Calee#989` — localised meal-row overflow interaction using existing actions and confirmation flows.
- `CaleeAdmin/CaleeMobile#512` — measurement-led Android bundle-size optimisation with focused release smoke testing.
- `CaleeAdmin/calee-hub-web#83` — focused single-page hero and responsive-layout refinement.
- `CaleeAdmin/calee-hub-core#371` — product decision record and machine-readable catalogue definition.

### C3 — Medium

- `CaleeAdmin/Calee#991` — bounded continuous-refresh and day-boundary behaviour within the existing tablet calendar architecture.
- `CaleeAdmin/CaleeMobile#505` — bounded shopping-list correctness and ingredient-coverage work using existing service architecture.
- `CaleeAdmin/CaleeMobile-Regression#53` — bounded attachment regression matrix across established API and device-test layers.
- `CaleeAdmin/calee-regression#54` — bounded calendar-correctness suite using deterministic fixtures across existing clients and embeds.

### C4 — Complex

- `CaleeAdmin/CaleeMobile#504` — retained multi-account isolation spanning sessions, storage, networking, caches and migration.
- `CaleeAdmin/calee-hub-core#363` — authoritative provisioning architecture and reconciliation.
- `CaleeAdmin/calee-hub-core#370` — Apple and Google subscription verification and lifecycle reconciliation.
- `CaleeAdmin/CaleeShell#209` — kiosk-safe Wi-Fi implementation requiring Android platform work and hardware qualification.
- `CaleeAdmin/calee-regression#77` — deterministic fixture, reset, snapshot and distributed lease-control subsystem.

### C5 — Epic

- `CaleeAdmin/CaleeMobile#503` — Meals and Shopping programme containing multiple independently deliverable product workstreams.
- `CaleeAdmin/calee-hub-core#367` — server-side notification and device-delivery platform with scheduling, outbox, registration and delivery phases.
- `CaleeAdmin/calee-regression#61` — organisation-wide system-integration programme coordinating many child suites.
- `CaleeAdmin/calee-regression#73` — single-VM appliance programme coordinating several infrastructure workstreams.

## Required issue block

Every implementation, product, operational or regression issue should begin with:

```markdown
## Classification

- **Complexity:** C3 — Medium
- **Risk:** R3 — Moderate
- **Priority:** P2 — Planned
- **Classification status:** Proposed

### Rationale

- **Complexity:** Bounded feature using the existing architecture, with non-trivial state, integration and regression work.
- **Risk:** Incorrect behaviour could cause a material but bounded regression.
- **Priority:** Approved planned work, but not an immediate incident or release blocker.
```

Use **Proposed** when created and **Confirmed** after triage.

The rationale must explain why the issue falls on one side of a benchmark boundary. Statements such as “a lot of work”, “large change” or “important issue” are insufficient.

## Risk scale

| Code | Name | Meaning |
|---|---|---|
| **R1** | Minimal | Failure is easy to detect and reverse, with negligible customer or operational impact. |
| **R2** | Low | Limited impact and straightforward recovery. |
| **R3** | Moderate | Material regression or operational disruption is possible, but the impact is bounded. |
| **R4** | High | Failure could affect core customer journeys, data integrity, release readiness or significant operations. |
| **R5** | Critical | Failure could expose credentials or private data, charge customers incorrectly, cross account or household boundaries, cause severe lockout or create major compliance exposure. |

## Priority scale

| Code | Name | Meaning |
|---|---|---|
| **P0** | Emergency | Active incident, security emergency or immediate release blocker requiring interruption of planned work. |
| **P1** | High | Near-term product, reliability, commercial or release requirement. |
| **P2** | Planned | Approved work to schedule in normal delivery planning. |
| **P3** | Backlog | Valuable work that should not displace higher-priority delivery. |

## Triage and change control

1. The issue creator proposes Complexity, Risk and Priority.
2. The product or technical owner confirms them during triage.
3. C5 issues must identify independently deliverable child workstreams before implementation starts.
4. The implementer requests reassessment when scope materially changes.
5. The reviewer verifies the classification remains accurate before closure.
6. Reopened issues retain classification history and are reassessed against current scope.
7. The issue body and any classification labels must agree.

## Initial benchmark snapshot

The initial audit completed on 6 August 2026 covered **85 open issues** across 12 repositories:

- **C1 — Trivial:** 0
- **C2 — Small:** 9
- **C3 — Medium:** 44
- **C4 — Complex:** 23
- **C5 — Epic:** 9

This is a calibration snapshot, not a target quota.

## Governance

Changes to this standard must update this document and `issue-classification.yml` together, increment the policy version, record the effective date and explain any changed boundary.