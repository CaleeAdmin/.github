# Calee Issue Classification Benchmark

**Status:** Authoritative cross-repository standard  
**Policy version:** 2  
**Owner:** Calee engineering and product triage  
**Adopted:** 6 August 2026  
**Risk and Priority benchmark revised:** 6 August 2026  
**Applies to:** All issues created in repositories owned by `CaleeAdmin`

This document is the source of truth for classifying Calee issues. The machine-readable companion is [`issue-classification.yml`](issue-classification.yml).

## Purpose

Classification supports backlog decomposition, planning, review depth, regression expectations and release coordination.

- **Complexity** describes implementation structure, architectural reach and uncertainty.
- **Risk** describes credible production harm if the problem remains or the change fails.
- **Priority** describes delivery urgency and sequencing based on current evidence.

These dimensions are independent:

- A C2 issue can be R5 when a small configuration mistake could expose secrets or charge customers incorrectly.
- A C5 epic can be R3 when it coordinates broad but safely isolated internal improvements.
- An R5 issue can be P2 when strong controls exist and no current incident or committed milestone is affected.
- An R2 issue can be P1 when it is a simple requirement blocking an imminent release.

Complexity does not estimate elapsed time. Risk is not a proxy for Complexity. Priority is not a proxy for either Complexity or Risk.

# Complexity benchmark

## Complexity scale

| Code | Name | Definition | Typical characteristics |
|---|---|---|---|
| **C1** | **Trivial** | Mechanical change with virtually no design decision. | Typo, copy correction, obvious constant change, isolated asset replacement or another self-evident change with narrowly focused verification. |
| **C2** | **Small** | Localised implementation using an established pattern. | Normally one repository; limited files or one operational procedure; no persistent schema, security-boundary, migration or material compatibility change. |
| **C3** | **Medium** | Bounded feature, correction or regression suite with non-trivial implementation inside the existing architecture. | State, UI, API integration, fixtures, diagnostics and tests may be substantial, but the work has one coherent delivery boundary. |
| **C4** | **Complex** | Material architectural or operational boundary change. | Persistent data model, migration, authentication/authorisation, billing lifecycle, device-policy behaviour, compatibility rollout, distributed coordination or infrastructure subsystem. |
| **C5** | **Epic** | Programme containing several independently deliverable C3 or C4 workstreams. | Requires decomposition, sequencing, cross-repository coordination, separate child issues and programme-level release or acceptance gates. |

Use only these exact names. Do not use alternatives such as `C4 — Large`, `C5 — Very large`, `Major` or `XL`.

## Complexity decision sequence

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

## Complexity interpretation rules

- Complexity measures implementation structure and uncertainty, not business importance.
- A long issue description is not automatically complex.
- Cross-repository work is not automatically C4.
- High-risk store configuration, release operations or privacy-sensitive work may remain C2 or C3 when they do not create new architecture.
- C4 requires a material architecture, migration, security, data, compatibility, billing, device-policy, distributed-systems or infrastructure concern.
- C5 is reserved for programmes that must be split into child issues. A large standalone implementation is C4, not C5.
- Child issues of a C5 epic receive independent classifications and do not inherit C5.
- Scope growth must trigger reassessment before implementation continues.
- Physical qualification alone does not force C4; classify the underlying system change and test architecture.

## Complexity calibration examples

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

# Risk benchmark

## What Risk measures

Risk records the **credible harm** associated with the issue, considering both the current problem and failure modes introduced by the proposed change. Assess the highest credible production consequence after considering existing controls, not an imaginary worst case with no plausible path.

Every risk rationale must address four factors:

1. **Impact** — what can go wrong for customers, data, money, privacy, security, operations or release safety.
2. **Exposure and blast radius** — which accounts, households, devices, services or environments can be affected and how often the path is exercised.
3. **Detectability** — whether failure is obvious and promptly observable or silent and likely to persist.
4. **Recoverability** — whether rollback, repair or data reconciliation is simple, bounded and proven.

Likelihood matters, but severe trust-boundary, billing, privacy and irreversible-loss consequences must not be downgraded merely because they are expected to be uncommon.

## Risk scale

| Code | Name | Benchmark |
|---|---|---|
| **R1** | **Minimal** | Negligible harm. Failure is cosmetic, documentation-only or confined to a non-production test aid; it is immediately visible and safely reversible. No persistent data, security, privacy, billing or core-workflow consequence. |
| **R2** | **Low** | Limited, localised harm with an obvious failure signal and a simple workaround, revert or retry. No credible cross-account exposure, irreversible data loss, incorrect charge or sustained core-service outage. |
| **R3** | **Moderate** | Material but bounded regression or operational disruption. Some users or one subsystem may be affected; a workaround or controlled recovery exists; persistent harm is limited and failures are reasonably detectable. |
| **R4** | **High** | Core customer journeys, data integrity, release readiness or significant operations can be materially affected. Failure may be silent, broad or difficult to repair, but does not credibly meet an R5 trust-boundary, financial, compliance or catastrophic-loss trigger. |
| **R5** | **Critical** | A credible failure can expose credentials or private data, cross account/household/tenant boundaries, charge or refund customers incorrectly, grant or revoke entitlement incorrectly at material scale, cause irreversible or widespread data loss, create severe lockout, compromise trusted device identity or create major legal/compliance exposure. |

## R5 hard triggers

Classify as R5 when the issue contains a credible path to one or more of these outcomes:

- cross-account, cross-household, cross-organisation or cross-service private-data exposure;
- password, access token, refresh token, provider token, app password, signing key or equivalent credential exposure;
- incorrect customer charging, duplicate subscription, invalid refund/revocation or material entitlement leakage;
- bypass of authentication, authorisation, device identity or administrator boundaries;
- collection or disclosure of children's information, calendar contents, attachments or other private content outside the approved privacy contract;
- irreversible or widespread customer-data loss or corruption without reliable reconciliation;
- mass account or device lockout with no safe recovery path;
- a credible major regulatory, contractual or compliance breach.

The presence of security- or privacy-related code does not automatically make an issue R5. The failure consequence must meet a hard trigger credibly.

## Risk decision sequence

1. **Does a credible failure meet an R5 hard trigger?**  
   Yes: **R5 — Critical**.

2. **Can failure materially damage a core customer journey, silently corrupt important data, block a release, or cause significant and difficult operational recovery?**  
   Yes: **R4 — High**.

3. **Can failure cause a material but bounded regression with a known workaround or controlled recovery?**  
   Yes: **R3 — Moderate**.

4. **Is the impact localised, obvious and straightforward to reverse, retry or work around?**  
   Yes: **R2 — Low**.

5. **Is the effect negligible, cosmetic or confined to non-production support material?**  
   Yes: **R1 — Minimal**.

If the rationale cannot identify a concrete consequence, affected scope, detection path and recovery approach, the risk classification is not ready to confirm.

## Risk interpretation rules

- Do not raise Risk because the issue is large, complex or urgent.
- Do not lower Risk because the implementation is small.
- Score credible production impact, not developer inconvenience.
- Silent incorrect data is generally riskier than an obvious failed request with no commit.
- A tested rollback lowers recoverability concerns but does not erase privacy, billing or trust-boundary consequences.
- Epics receive programme-level Risk; child issues receive independent Risk based on their own credible failure modes.
- Regression-only issues score the harm caused by missing or ineffective coverage, not the number of test cases.
- Risk may change when architecture, controls, rollout scope or evidence changes. Record the reason for reassessment.

## Risk calibration examples

### R1 — Minimal

- Copy-only, documentation-only or isolated non-production test-harness corrections with no effect on product decisions, credentials, customer data or release gates.
- No issue in the reviewed open set is used as an R1 anchor.

### R2 — Low

- `CaleeAdmin/CaleeMobile#512` — bundle-size optimisation where a poor change is detectable through build and smoke testing and can be reverted without persistent customer-data impact.

### R3 — Moderate

- `CaleeAdmin/CaleeMobile#507` — bounded Meals UI redesign that could regress meal actions or usability but remains visible and recoverable.
- `CaleeAdmin/CaleeMobile#514` — CI trigger and retention changes that could disrupt checks but have bounded repository-level recovery.
- `CaleeAdmin/CaleeMobile#509` — selected-week and copy behaviour that could place meals incorrectly but remains limited to a bounded product workflow.

### R4 — High

- `CaleeAdmin/calee-hub-core#362` — false-ready service states can block core Portal or Business access while reporting success.
- `CaleeAdmin/CaleeMobile#505` — shopping-list generation can silently omit planned meals or preserve stale generated data.
- `CaleeAdmin/Calee#991` — continuously running household displays can silently show stale or wrong-day calendar information.
- `CaleeAdmin/CaleeMobile#513` — weak store-release operations can publish the wrong build, expose operational credentials or leave no safe rollback path; it is high operational risk even though the implementation is C2.

### R5 — Critical

- `CaleeAdmin/CaleeMobile#504` — account-isolation failure can leak data or credentials across unrelated accounts.
- `CaleeAdmin/CaleeMobile#519` — in-app purchase or entitlement failure can charge incorrectly, unlock access improperly or create duplicate subscriptions.
- `CaleeAdmin/CaleeMobile#521` — analytics failure can collect private schedule or children's information outside the approved privacy contract.
- `CaleeAdmin/CaleeMobile#522` — store configuration can mix production and sandbox billing or break verified subscription lifecycle handling.

# Priority benchmark

## What Priority measures

Priority records **why this issue should be delivered now relative to other work**. It is a current sequencing decision and is expected to change more frequently than Complexity or Risk.

Every priority rationale must identify the evidence supporting urgency:

- current production state or customer impact;
- named deadline, release, commercial launch, contractual commitment or external review date;
- workstreams or people blocked by the issue;
- availability and quality of a workaround;
- cost of delay, including repeated support effort or compounding technical/operational exposure;
- whether the issue must interrupt already planned work.

Risk informs Priority but does not determine it. Priority must include a clear **why now** statement.

## Priority scale

| Code | Name | Benchmark |
|---|---|---|
| **P0** | **Emergency** | Active production, security, privacy, billing or data-integrity incident, or an immediate no-workaround release blocker. Requires interruption of planned work, an active owner and incident-style coordination. P0 is temporary and must be downgraded when the emergency condition ends. |
| **P1** | **High** | Must be delivered in the near term because it protects a core journey, satisfies a committed release/commercial milestone, resolves a recurring material production defect, or unblocks several planned workstreams. Work should be explicitly scheduled and owned. |
| **P2** | **Planned** | Approved and valuable work to schedule through normal planning. Delay is acceptable for a planning cycle; a workaround or sequencing dependency exists; it is not currently blocking a committed milestone or active incident response. |
| **P3** | **Backlog** | Uncommitted optimisation, polish, research, future architecture or operational improvement that should not displace scheduled correctness, safety, release or commercial work. |

## Priority decision sequence

1. **Is there an active incident or immediate no-workaround release/security/privacy/billing/data-integrity blocker requiring interruption of planned work?**  
   Yes: **P0 — Emergency**.

2. **Is the issue required for a committed near-term milestone, a core journey currently failing materially, a recurring production/support burden, or a dependency blocking multiple scheduled workstreams?**  
   Yes: **P1 — High**.

3. **Is the work approved for normal delivery, with delay acceptable for a planning cycle and no active blocker?**  
   Yes: **P2 — Planned**.

4. **Is the work useful but uncommitted, optional, exploratory or lower-value than scheduled work?**  
   Yes: **P3 — Backlog**.

If the rationale contains only “important”, “strategic” or a Complexity/Risk code, the priority is not ready to confirm.

## Priority interpretation rules

- P0 does not mean “very important”. It means active interruption and immediate coordination.
- P1 requires explicit near-term evidence: current impact, committed milestone, recurring support burden or blocking dependency.
- A due date supports P1 only when it is a genuine delivery commitment or external constraint, not an aspirational target.
- R5 issues may remain P2 when strong controls exist, the affected capability is not live and no committed milestone is blocked.
- R2 issues may be P1 when a simple change is the last blocker for a committed release.
- C5 epics do not automatically receive P1. Programme priority must be justified separately, and child issues may have different priorities.
- Priority should be reassessed when incidents close, deadlines move, blockers are removed, workarounds improve, customer exposure changes or dependencies are completed.
- P3 work may be promoted when evidence changes; do not keep a historical priority merely because it was once recorded.

## Priority calibration examples

### P0 — Emergency

No issue in the reviewed open set is used as a P0 anchor. Use P0 only for an active incident or immediate no-workaround blocker, and include the incident, release or security reference in the rationale.

### P1 — High

- `CaleeAdmin/calee-hub-core#362` — minimal truthful service-readiness repair that should precede broader provisioning work.
- `CaleeAdmin/CaleeMobile#505` — shopping-list trust and correctness foundation that should precede broader Meals UX work.
- `CaleeAdmin/CaleeMobile#513` — near-term store-release operational readiness.
- `CaleeAdmin/CaleeMobile#518` — foundation for the approved Guest acquisition and pricing model.
- `CaleeAdmin/CaleeMobile#519` and `#522` — required commercial subscription capability and store configuration before Calee AI can be sold safely.
- `CaleeAdmin/CaleeMobile#523` and `#524` — production-facing attachment reliability and release-gate work.
- `CaleeAdmin/Calee#991` — core continuous-display calendar freshness.

### P2 — Planned

- `CaleeAdmin/CaleeMobile#506` — valuable custom-meal workflow sequenced after shopping-list correctness foundations.
- `CaleeAdmin/CaleeMobile#507` — important usability redesign that follows correctness work.
- `CaleeAdmin/CaleeMobile#509` and `#511` — approved Meals and Shopping correctness work with explicit sequencing dependencies.
- `CaleeAdmin/CaleeMobile#521` — privacy-safe analytics is important but follows approved privacy design and core product implementation.

### P3 — Backlog

- `CaleeAdmin/CaleeMobile#512` — useful bundle-size optimisation that should not displace correctness or release-readiness work unless a store or delivery threshold is breached.

# Required issue classification block

Every implementation, product, operational or regression issue should begin with:

```markdown
## Classification

- **Complexity:** C3 — Medium
- **Risk:** R3 — Moderate
- **Priority:** P2 — Planned
- **Classification status:** Proposed

### Rationale

- **Complexity:** Bounded feature using the existing architecture, with non-trivial state, integration and regression work.
- **Risk:** Failure could cause a material but bounded regression affecting one workflow; it is visible, has a workaround and is recoverable without cross-account or irreversible impact.
- **Priority:** Approved planned work; no active incident or committed near-term milestone is blocked, and the work is sequenced after the current correctness foundation.
```

Use **Proposed** when created and **Confirmed** after triage.

The rationale must explain why the issue falls on one side of each benchmark boundary. Statements such as “a lot of work”, “large change”, “high risk”, “important issue” or “ASAP” are insufficient.

# Triage and change control

1. The issue creator proposes Complexity, Risk and Priority independently.
2. The product or technical owner confirms them during triage.
3. Risk confirmation must identify impact, exposure, detectability and recoverability.
4. Priority confirmation must identify why now, any deadline or blocker, the workaround and the cost of delay.
5. C5 issues must identify independently deliverable child workstreams before implementation starts.
6. The implementer requests reassessment when scope, controls, rollout or credible failure modes materially change.
7. Priority is reassessed when incidents close, milestones move, dependencies change or workarounds become available.
8. The reviewer verifies the classification remains accurate before closure.
9. Reopened issues retain classification history and are reassessed against current conditions.
10. The issue body and any classification labels must agree.

# Initial benchmark snapshot

The initial Complexity audit completed on 6 August 2026 covered **85 open issues** across 12 repositories:

- **C1 — Trivial:** 0
- **C2 — Small:** 9
- **C3 — Medium:** 44
- **C4 — Complex:** 23
- **C5 — Epic:** 9

This is a calibration snapshot, not a target quota.

A complete Risk and Priority distribution is not recorded yet because many pre-existing open issues did not contain those fields. The examples above are calibration anchors, not a claim that the full 85-issue backlog has been audited for Risk and Priority.

# Governance

Changes to this standard must update this document and `issue-classification.yml` together, increment the policy version, record the effective date and explain any changed boundary. Changes to Risk or Priority must also update both default issue forms so the required evidence remains aligned with the policy.